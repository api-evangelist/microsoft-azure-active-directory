# Microsoft Azure Active Directory (microsoft-azure-active-directory)

Microsoft Azure Active Directory (Azure AD), now Microsoft Entra ID, is Microsoft's cloud-based identity and access management service, which helps employees sign in and access resources.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/microsoft-azure-active-directory/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/microsoft-azure-active-directory/refs/heads/main/apis.yml)

## Scope

- **Type:** Index

## Tags

- Authentication
- Authorization
- Identity
- Microsoft
- Microsoft Entra
- OAuth
- OpenID Connect
- SAML
- SCIM
- Single Sign-On
- Zero Trust

## Timestamps

- **Created:** 2024-01-15
- **Modified:** 2026-05-19

## APIs

### Microsoft Graph API

The Microsoft Graph API offers a single endpoint to access Azure AD data and other Microsoft 365 services.

- **Human URL:** [https://docs.microsoft.com/en-us/graph/overview](https://docs.microsoft.com/en-us/graph/overview)
- **Base URL:** `https://graph.microsoft.com`

#### Tags

- Graph
- Groups
- Identity
- Users

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/overview)
- [OpenAPI](https://raw.githubusercontent.com/microsoftgraph/msgraph-metadata/master/openapi/v1.0/openapi.yaml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [OpenAPI](openapi/microsoft-graph-identity-api.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Authentication](https://docs.microsoft.com/en-us/graph/auth/)
- [SDK](https://docs.microsoft.com/en-us/graph/sdks/sdks-overview)
- [Pricing](https://azure.microsoft.com/en-us/pricing/details/active-directory/)
- [Getting Started](https://learn.microsoft.com/en-us/graph/use-the-api)
- [Console](https://developer.microsoft.com/en-us/graph/graph-explorer)
- [Changelog](https://learn.microsoft.com/en-us/graph/changelog)

### Microsoft Graph Identity and Access API

Microsoft Graph APIs for managing Microsoft Entra identity and network access capabilities, including user management, group management, application registration, conditional access policies, authentication methods, and identity governance.

- **Human URL:** [https://learn.microsoft.com/en-us/graph/identity-network-access-overview](https://learn.microsoft.com/en-us/graph/identity-network-access-overview)
- **Base URL:** `https://graph.microsoft.com`

#### Tags

- Access Management
- Authentication Methods
- Conditional Access
- Identity
- Identity Governance

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/identity-network-access-overview?view=graph-rest-1.0)
- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/conditionalaccesspolicy?view=graph-rest-1.0)
- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/identitygovernance-overview?view=graph-rest-1.0)
- [Documentation](https://learn.microsoft.com/en-us/entra/identity-platform/v2-conditional-access-dev-guide)
- [OpenAPI](openapi/microsoft-graph-identity-api.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/azure-active-directory-user-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/azure-active-directory-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Azure AD Graph API (Deprecated)

Legacy API for accessing Azure AD (deprecated in favor of Microsoft Graph).

- **Human URL:** [https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-graph-api](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-graph-api)
- **Base URL:** `https://graph.windows.net`

#### Tags

- Deprecated
- Identity
- Legacy

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/previous-versions/azure/ad/graph/api/api-catalog)
- [Documentation](https://docs.microsoft.com/en-us/graph/migrate-azure-ad-graph-overview)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Azure AD Authentication Library (ADAL)

Authentication library for Azure AD (being replaced by MSAL).

- **Human URL:** [https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-authentication-libraries](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-authentication-libraries)

#### Tags

- Authentication
- Legacy
- Library

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/active-directory-authentication-libraries)
- [GitHub Repository](https://github.com/AzureAD/azure-activedirectory-library-for-dotnet)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Authentication Library (MSAL)

Modern authentication library for Microsoft identity platform.

- **Human URL:** [https://docs.microsoft.com/en-us/azure/active-directory/develop/msal-overview](https://docs.microsoft.com/en-us/azure/active-directory/develop/msal-overview)

#### Tags

- Authentication
- Library
- OAuth
- OpenID Connect

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/msal-overview)
- [GitHub Repository](https://github.com/AzureAD/microsoft-authentication-library-for-js)
- [Code Examples](https://docs.microsoft.com/en-us/azure/active-directory/develop/sample-v2-code)
- [GitHub Repository](https://github.com/AzureAD/microsoft-authentication-library-for-dotnet)
- [GitHub Repository](https://github.com/AzureAD/microsoft-authentication-library-for-python)
- [GitHub Repository](https://github.com/AzureAD/microsoft-authentication-library-for-java)
- [GitHub Repository](https://github.com/AzureAD/microsoft-authentication-library-for-objc)
- [Documentation](https://learn.microsoft.com/en-us/entra/msal/)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Identity Platform

The Microsoft identity platform provides authentication and authorization services using standards-compliant implementations of OAuth 2.0 and OpenID Connect, enabling developers to build applications that sign in users and access secured APIs.

- **Human URL:** [https://learn.microsoft.com/en-us/entra/identity-platform/](https://learn.microsoft.com/en-us/entra/identity-platform/)
- **Base URL:** `https://login.microsoftonline.com`

#### Tags

- App Registration
- Authentication
- Authorization
- OAuth
- OpenID Connect

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/entra/identity-platform/)
- [Documentation](https://learn.microsoft.com/en-us/entra/identity-platform/v2-protocols)
- [Documentation](https://learn.microsoft.com/en-us/entra/identity-platform/v2-protocols-oidc)
- [Documentation](https://learn.microsoft.com/en-us/entra/identity-platform/v2-oauth2-auth-code-flow)
- [Getting Started](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app)
- [Documentation](https://learn.microsoft.com/en-us/entra/identity-platform/scopes-oidc)
- [Code Examples](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-web-app-sign-in)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Entra Verified ID API

Microsoft Entra Verified ID is a managed verifiable credentials service that enables organizations to issue, manage, and verify decentralized identity credentials based on W3C standards.

- **Human URL:** [https://learn.microsoft.com/en-us/entra/verified-id/](https://learn.microsoft.com/en-us/entra/verified-id/)
- **Base URL:** `https://verifiedid.did.msidentity.com`

#### Tags

- Decentralized Identity
- Identity Verification
- Verifiable Credentials
- W3C

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/entra/verified-id/)
- [API Reference](https://learn.microsoft.com/en-us/entra/verified-id/admin-api)
- [API Reference](https://learn.microsoft.com/en-us/entra/verified-id/vc-network-api)
- [Documentation](https://learn.microsoft.com/en-us/entra/verified-id/decentralized-identifier-overview)
- [Getting Started](https://learn.microsoft.com/en-us/entra/verified-id/verifiable-credentials-configure-tenant)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Entra ID Governance API

Microsoft Entra ID Governance APIs in Microsoft Graph enable automated access reviews, entitlement management, lifecycle workflows, and privileged identity management for identity governance scenarios.

- **Human URL:** [https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview)
- **Base URL:** `https://graph.microsoft.com`

#### Tags

- Access Reviews
- Entitlement Management
- Governance
- Lifecycle Workflows
- Privileged Identity Management

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview)
- [API Reference](https://learn.microsoft.com/en-us/graph/api/resources/identitygovernance-overview?view=graph-rest-1.0)
- [Documentation](https://learn.microsoft.com/en-us/entra/id-governance/deploy-access-reviews)
- [Documentation](https://learn.microsoft.com/en-us/entra/id-governance/lifecycle-workflows-deployment)
- [Pricing](https://learn.microsoft.com/en-us/entra/id-governance/licensing-fundamentals)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Entra SCIM Provisioning API

Microsoft Entra ID supports SCIM 2.0 protocol for automatic user and group provisioning to cloud applications, enabling automated identity lifecycle management through standardized REST APIs.

- **Human URL:** [https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups](https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups)

#### Tags

- Automation
- Group Management
- Provisioning
- SCIM
- User Management

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/entra/identity/app-provisioning/use-scim-to-provision-users-and-groups)
- [Documentation](https://learn.microsoft.com/en-us/entra/architecture/sync-scim)
- [GitHub Repository](https://github.com/azure-ad-b2c/rest-api)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Microsoft Entra PowerShell

The Microsoft Entra PowerShell module provides cmdlets for managing Microsoft Entra resources programmatically, built on the Microsoft Graph PowerShell SDK.

- **Human URL:** [https://learn.microsoft.com/en-us/powershell/entra-powershell/overview?view=entra-powershell](https://learn.microsoft.com/en-us/powershell/entra-powershell/overview?view=entra-powershell)

#### Tags

- Automation
- CLI
- PowerShell
- Scripting

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/powershell/entra-powershell/?view=entra-powershell)
- [Getting Started](https://learn.microsoft.com/en-us/powershell/entra-powershell/installation?view=entra-powershell)
- [GitHub Repository](https://github.com/microsoftgraph/entra-powershell)
- [Postman Collection](collections/microsoft-graph-identity-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/microsoft-graph-identity-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://portal.azure.com/)
- [Status Page](https://status.azure.com/)
- [Support](https://azure.microsoft.com/en-us/support/)
- [Blog](https://techcommunity.microsoft.com/t5/azure-active-directory/bg-p/Azure-Active-Directory)
- [Terms of Service](https://azure.microsoft.com/en-us/support/legal/)
- [Privacy Policy](https://privacy.microsoft.com/en-us/privacystatement)
- [Pricing](https://azure.microsoft.com/en-us/pricing/details/active-directory/)
- [Training](https://docs.microsoft.com/en-us/learn/azure/)
- [Portal](https://entra.microsoft.com)
- [Developer Portal](https://developer.microsoft.com/en-us/graph)
- [Blog](https://devblogs.microsoft.com/identity/)
- [Blog R S S](https://devblogs.microsoft.com/identity/feed/)
- [Release Notes](https://learn.microsoft.com/en-us/entra/fundamentals/whats-new)
- [Documentation](https://learn.microsoft.com/en-us/entra/identity/)
- [Console](https://developer.microsoft.com/en-us/graph/graph-explorer)
- [GitHub Organization](https://github.com/AzureAD)
- [OpenAPI](openapi/microsoft-graph-identity-api.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [JSON Schema](json-schema/azure-active-directory-user-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/azure-active-directory-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Features](undefined)
- [Use Cases](undefined)
- [Integrations](undefined)

## Maintainers

**Email:** azuread@microsoft.com
**URL:** https://azure.microsoft.com/en-us/services/active-directory/
**Email:** kin@apievangelist.com
**URL:** https://apievangelist.com
