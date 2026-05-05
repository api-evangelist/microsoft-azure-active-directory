---
title: "Announcing the General Availability of Managed Identities as Federated Identity Credentials in your Entra apps"
url: "https://devblogs.microsoft.com/identity/access-cloud-resources-across-tenants-without-secrets-ga/"
date: "Thu, 08 May 2025 13:23:06 +0000"
author: "Hosam Shahin"
feed_url: "https://devblogs.microsoft.com/identity/feed/"
---
<p><img alt="Entra apps now support managed identity to replace app secrets" src="https://devblogs.microsoft.com/identity/wp-content/uploads/sites/74/2025/04/appmsi.png" /></p>
<p>We&#8217;re excited to announce the general availability of using managed identities as federated credentials for Entra apps! With this feature, Entra apps can securely access Azure and other Entra-protected resources, whether in single-tenant or multi-tenant scenarios, without relying on secrets or certificates. Previously, Entra apps used for user authentication or accessing resources like Microsoft Graph or Azure in multi-tenant scenarios required credentials such as secrets or certificates. Managed identities provide the most secure, secret-free alternative for workloads hosted on Azure, but they&#8217;re traditionally limited to the security boundaries of their tenants. Today&#8217;s announcement makes it possible to use managed identities as a credential that Entra Apps can use to access resources across tenants. Today&#8217;s announcement is a major step to protect application workload identities and eliminate secrets, as outlined in Microsoft&#8217;s Secure Future Initiative, a multiyear commitment to enhance security across our products and help customers better secure their environments.</p>
<h4>Why does this matter?</h4>
<p>Leveraging managed identities eliminates the need for managing secrets or certificates. This significantly reduces potential security vulnerabilities that can result from accidental exposure and unauthorized access to sensitive resources. It also removes the operational overhead associated with storing, rotating, and distributing secrets and certificates.</p>
<h4>How it works</h4>
<p>Think of this feature as allowing your Entra app to directly trust a managed identity assigned to Azure resources (e.g., Virtual Machines, App Services) hosting your workload, instead of relying on traditional secrets or certificates. This works both in single and multitenant setups. <img alt="Example showing secret/cert credentials vs. managed identity config using Microsoft.Identity.Web" src="https://devblogs.microsoft.com/identity/wp-content/uploads/sites/74/2025/04/mi-as-cred.png" /></p>
<p>In a multi-tenant setup: 1) Your workload runs in the tenant hosting your multi-tenant Entra app. 2) You assign a user-assigned managed identity to the Azure compute resource that hosts your workload. 3) You configure a federated identity credential to establish trust between your Entra app and the managed identity. 4) You ask the admins of the target tenant to provision your Entra app in their tenant. 5) At runtime, use the managed identity as an assertion that you exchange for an app token.</p>
<p>The process to acquire app access tokens is composed of two steps: 1) construct a client assertion using the managed identity token, and 2) use that to obtain the app access token. This process is fully supported by Identity SDKs across languages. Here is an example using <a href="https://www.nuget.org/packages/Azure.Identity/">Azure.Identity for .Net</a></p>
<pre><code class="csharp">using Azure.Identity;
using Azure.Storage.Blobs;

internal class Program
{
  // This example demonstrates how to access an Azure blob storage account by utilizing the managed identity credential.
  static void Main(string[] args)
  {      
    // The application must be granted access on the target resource.
    // The app and managed identity have to be in the same tenant.
    string appClientId = "YOUR_APP_CLIENT_ID";
    // The managed identity which you configured as a Federated Identity Credential (FIC)
    string managedIdentityClientId = "YOUR_MANAGED_IDENTITY_CLIENT_ID";        
    // Audience value must be one of the below values depending on the target cloud.
    // Entra ID Global cloud: api://AzureADTokenExchange
    // Entra ID US Government: api://AzureADTokenExchangeUSGov
    // Entra ID China operated by 21Vianet: api://AzureADTokenExchangeChina
    string audience = "api://AzureADTokenExchange";
    // The tenant where the target resource is created, in this example, the storage account tenant.
    string resourceTenantId = "YOUR_RESOURCE_TENANT_ID";
    string storageAccountName = "YOUR_STORAGE_ACCOUNT_NAME";
    string containerName = "CONTAINER_NAME";

    // 1. Create an assertion with the managed identity access token, so that it can be exchanged for an app token
    var miCredential = new ManagedIdentityCredential(managedIdentityClientId);
    ClientAssertionCredential assertion = new(
        tenantId,
        appClientId,
        async (token) =&gt;
        {
            // fetch Managed Identity token for the specified audience
            var tokenRequestContext = new Azure.Core.TokenRequestContext(new[] { $"{audience}/.default" });
            var accessToken = await miCredential.GetTokenAsync(tokenRequestContext).ConfigureAwait(false);
            return accessToken.Token;
        });

      // 2. The assertion can be used to obtain an App token (taken care of by the SDK)
      var containerClient  = new BlobContainerClient(new Uri($"https://{storageAccountName}.blob.core.windows.net/{containerName}"), assertion);

      await foreach (BlobItem blob in containerClient.GetBlobsAsync())
      {
          // TODO: perform operations with the blobs
          BlobClient blobClient = containerClient.GetBlobClient(blob.Name);
          Console.WriteLine($"Blob name: {blobClent.Name}, uri: {blobClient.Uri}");            
      }
  }
}
</code></pre>
<p>Here&#8217;s a similar example in Python, using the <code>azure-identity</code> library, available on <a href="https://pypi.org/project/azure-identity/">pip</a> or <a href="https://anaconda.org/microsoft/azure-identity/">conda</a></p>
<pre><code class="python">from azure.identity import ManagedIdentityCredential, ClientAssertionCredential
from azure.storage.blob import BlobServiceClient

# Configurable values
APP_CLIENT_ID      = "YOUR_APP_CLIENT_ID"
MI_CLIENT_ID       = "YOUR_MANAGED_IDENTITY_CLIENT_ID"
AUDIENCE           = "api://AzureADTokenExchange"
RESOURCE_TENANT_ID = "YOUR_RESOURCE_TENANT_ID"
STORAGE_ACCOUNT    = "YOUR_STORAGE_ACCOUNT_NAME"
CONTAINER_NAME     = "YOUR_CONTAINER_NAME"

# 1. Get a managed identity token for the token exchange audience
mi_credential = ManagedIdentityCredential(client_id=MI_CLIENT_ID)
def get_mi_token():
    token = mi_credential.get_token(f"{AUDIENCE}/.default")
    return token.token

# 2. Create a client assertion credential using the managed identity token
credential = ClientAssertionCredential(
    tenant_id=RESOURCE_TENANT_ID,
    client_id=APP_CLIENT_ID,
    client_assertion_callback=get_mi_token
)

# 3. Use the credential to access Blob Storage
blob_service_client = BlobServiceClient(
    account_url=f"https://{STORAGE_ACCOUNT}.blob.core.windows.net",
    credential=credential
)
container_client = blob_service_client.get_container_client(CONTAINER_NAME)

# 4. List blobs in the container
print(f"Blobs in container '{CONTAINER_NAME}':")
for blob in container_client.list_blobs():
    print(f"- {blob.name}")
</code></pre>
<h4>Learn more</h4>
<p>This GA milestone makes it easier, and more secure than ever, to build secretless apps. To get started, check out these resources:</p>
<ul>
<li><a href="https://learn.microsoft.com/en-us/entra/workload-id/workload-identity-federation-config-app-trust-managed-identity">Official documentation</a> </li>
<li><a href="https://github.com/Azure-Samples/managed-identity/tree/main/ms-identity-aspnet-mi-as-fic">.NET sample</a> </li>
<li><a href="https://github.com/microsoftgraph/msgraph-bicep-types/tree/main/quickstart-templates/msi-as-a-fic-secretless">Configure a secret-less application to call Microsoft Graph: Bicep sample</a> </li>
<li><a href="https://learn.microsoft.com/en-us/azure/app-service/configure-authentication-provider-aad?tabs=workforce-configuration#use-a-managed-identity-instead-of-a-secret-preview">Configure App Service&#8217;s built-in auth (easy auth) to use managed identity (preview)</a> </li>
<li><a href="https://techcommunity.microsoft.com/blog/azuredevcommunityblog/easily-add-login-to-your-azure-app-with-bicep/4386493">Sample configuring built-in auth for Container Apps with no secrets (Bicep)</a> </li>
<li><a href="https://github.com/Azure-Samples/managed-identity/blob/main/ms-identity-aspnet-mi-as-fic/guide-and-snippets.md">Code snippets in Nodejs, Java, Go, Python</a></li>
</ul>
<p>Happy building, the secretless way!</p>
<h2>Stay connected and informed</h2>
<p>To learn more or test out other features in the Microsoft Entra portfolio, visit our <a href="https://aka.ms/dev/ms-entra">developer center</a>. Make sure you subscribe to the <a href="https://aka.ms/devblog/ms-entra">Identity developer blog</a> for more insights and to keep up with the latest on all things Identity. And, follow us on <a href="https://www.youtube.com/@MicrosoftSecurity/playlists">YouTube</a> for video overviews, tutorials, and deep dives. </p>
<p>The post <a href="https://devblogs.microsoft.com/identity/access-cloud-resources-across-tenants-without-secrets-ga/">Announcing the General Availability of Managed Identities as Federated Identity Credentials in your Entra apps</a> appeared first on <a href="https://devblogs.microsoft.com/identity">Microsoft Entra Identity Platform</a>.</p>
