---
title: "Announcing GA of Bicep templates support for Microsoft Entra ID resources"
url: "https://devblogs.microsoft.com/identity/bicep-templates-for-microsoft-entra-id-resources-is-ga/"
date: "Mon, 11 Aug 2025 16:08:26 +0000"
author: "Dan Kershaw"
feed_url: "https://devblogs.microsoft.com/identity/feed/"
---
<p>We’re thrilled to announce that Bicep templates for Microsoft Entra ID resources is generally available from July 29th, 2025. Bicep templates bring declarative infrastructure as code (IaC) capabilities to Microsoft Graph resources. This new capability will initially be available for core Microsoft Entra ID resources.</p>
<p>Bicep templates for Microsoft Graph resources allow you to define the tenant infrastructure you want to deploy, such as Microsoft Entra ID groups or applications, in a file, then use the file throughout the development lifecycle to repeatedly deploy your infrastructure. The file uses the <a href="https://learn.microsoft.com/azure/azure-resource-manager/bicep/overview">Bicep language</a>, a domain-specific language (DSL), that uses declarative syntax to deploy resources typically used in DevOps and <a href="https://learn.microsoft.com/en-us/devops/deliver/what-is-infrastructure-as-code">infrastructure as code</a> solutions.</p>
<h2>What problems does this solve?</h2>
<p>IaC avoids manual configuration and enforces consistency by representing desired environment states. Infrastructure deployments with IaC are repeatable and prevent runtime issues caused by configuration drift or missing dependencies. Release pipelines execute the environment descriptions and version configuration models to configure target environments. To make changes, the team edits the source, not the target.</p>
<p>With Bicep templates for Microsoft Graph resources, we are bringing these IaC benefits to key Microsoft Entra ID resources like applications and service principals. This allows you to deliver stable test environments rapidly and at scale as part of your development cycles, that can be integrated into your continuous delivery pipelines.</p>
<p>Let&#8217;s look at how this works and then we&#8217;ll run through an example.</p>
<h2>The Microsoft Graph Bicep extension</h2>
<p>To provide support for Bicep templates for Microsoft Graph resources, we have released the new Microsoft Graph Bicep extension that allows you to author, deploy, and manage supported Microsoft Graph resources (initially Microsoft Entra ID resources) in Bicep template files either on their own, or alongside Azure resources.</p>
<h2>Authoring experience</h2>
<p>You get the familiar, first-class authoring experience of the <a href="https://marketplace.visualstudio.com/items?itemName=ms-azuretools.vscode-bicep">Bicep Extension for VS Code</a> when you use it to create your Microsoft Graph resource types in Bicep files. The editor provides rich type-safety, IntelliSense, and syntax validation.</p>
<p>You can also create Bicep files in Visual Studio with the <a href="https://marketplace.visualstudio.com/items?itemName=ms-azuretools.visualstudiobicep">Bicep extension for Visual Studio</a>.</p>
<p><img alt="Editing a Bicep file containing Microsoft Graph resources" src="https://devblogs.microsoft.com/identity/wp-content/uploads/sites/74/2024/05/graphBicep.gif" /> <em>Editing a Bicep file containing Microsoft Graph resources</em></p>
<p>Let&#8217;s look at how this works and then we’ll run through an example.</p>
<h2>Deploying Bicep files</h2>
<p>Once you have authored your Bicep file, you can deploy it using familiar tools such as Azure PowerShell and Azure CLI. When the deployment request is made to the Azure Resource Manager, the deployments engine orchestrates the deployment of interdependent resources so they&#8217;re created in the correct order, including the Microsoft Graph resources.</p>
<p>The following image shows a Bicep template file where the Microsoft Graph group creation is dependent on the managed identity resource, as it is being added as a group member. The deployments engine first sends the managed identity request to the Resource Manager, which routes it to the <code>Microsoft.ManagedIdentity</code> resource provider. Next, the deployments engine sees that <code>Microsoft.Graph/groups</code> is an extensible resource, so it knows to route this resource request to the Microsoft Graph Bicep extension. The Microsoft Graph Bicep extension then translates the groups resource request into a request to Microsoft Graph.</p>
<p><img alt="" src="https://devblogs.microsoft.com/identity/wp-content/uploads/sites/74/2024/05/Deploying-a-Bicep-file-containing-Microsoft-Graph-resources-.png" /> <em>Deploying a Bicep file containing Microsoft Graph resources</em></p>
<h2>Scenario: Managing your team’s application registrations</h2>
<p>Ever feel like your team or organization’s internal applications are hard to manage or getting out of control? Are you spending time fixing broken applications because someone manually updated an application configuration without any oversight or testing? Unsure of what is deployed in your production tenants?</p>
<p>By adopting Bicep templates for Microsoft Graph, you can use DevOps practices to declare all your Microsoft Entra ID application registrations as declarative code. This enables you to have one path where your team members can create or update application configurations, using Bicep files, that get reviewed, deployed to a test environment (or tenant) for automated testing, before being checked-in and rolled out to a production tenant.</p>
<p>Let’s see what an application registration looks like in Bicep.</p>
<pre><code>resource clientApp 'Microsoft.Graph/applications@v1.0' = {
  uniqueName: clientAppName
  displayName: clientAppDisplayName
  signInAudience: 'AzureADMyOrg'
  web: {
    redirectUris: ['${webAppEndpoint}/.auth/login/aad/callback']
    implicitGrantSettings: {enableIdTokenIssuance: true}
  }
  requiredResourceAccess: [
    {
     resourceAppId: '00000003-0000-0000-c000-000000000000'
     resourceAccess: [
       // User.Read
       {id: 'e1fe6dd8-ba31-4d61-89e7-88639da4683d', type: 'Scope'}
       // offline_access
       {id: '7427e0e9-2fba-42fe-b0c0-848c9e6a8182', type: 'Scope'}
       // openid
       {id: '37f7f235-527c-4136-accd-4a02d197296e', type: 'Scope'}
       // profile
       {id: '14dad69e-099b-42c9-810b-d002981feec1', type: 'Scope'}
     ]
    }
  ]
}

resource clientSp 'Microsoft.Graph/servicePrincipals@beta' = {
  appId: clientApp.appId
}
</code></pre>
<p><em>Bicep file declaring a Microsoft Entra ID application and service principal</em></p>
<p>This file declares an applications resource for a web application, that can only be used in its home tenant, along with the set of permissions that this application requires so it can access the relevant Microsoft Graph APIs. This file also creates an associated service principal. The variables <code>webAppName</code>, <code>webAppDisplayName</code>, and <code>wwebAppEndpoint</code> can be automatically tailored to the target tenant (or environment) that the application is being deployed to, whether it’s test, stage, or production, in a reliable and repeatable manner.</p>
<p>Now that we&#8217;ve walked you through how Bicep templates for Microsoft Graph works and demonstrated it through a scenario sample, you can start creating your own Bicep templates to meet your infrastructure as code scenario needs.</p>
<h2>Learn more</h2>
<ul>
<li><a href="https://learn.microsoft.com/graph/templates">Bicep templates for Microsoft Graph resources documentation</a></li>
<li>Try out the <a href="https://learn.microsoft.com/graph/templates/quickstart-create-bicep-interactive-mode">create and deploy your first Bicep file with Microsoft Graph resources</a> quickstart</li>
<li>Explore more samples on our <a href="https://github.com/microsoftgraph/msgraph-bicep-types/tree/main/quickstart-templates">Microsoft Graph Bicep GitHub repo</a> and feel free to contribute your samples too</li>
</ul>
<p>To test out other features in the Microsoft Entra portfolio, visit our <a href="https://developer.microsoft.com/en-us/identity/">developer center</a>. Make sure you subscribe to the <a href="https://devblogs.microsoft.com/identity/">Identity blog</a> for more insights and to keep up with the latest on all things Identity. And, follow us on <a href="https://www.youtube.com/@MicrosoftSecurity/playlists">YouTube</a> for video overviews, tutorials, and deep dives.</p>
<p>The post <a href="https://devblogs.microsoft.com/identity/bicep-templates-for-microsoft-entra-id-resources-is-ga/">Announcing GA of Bicep templates support for Microsoft Entra ID resources</a> appeared first on <a href="https://devblogs.microsoft.com/identity">Microsoft Entra Identity Platform</a>.</p>
