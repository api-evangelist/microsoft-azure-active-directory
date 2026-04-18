# Azure Active Directory (azure-active-directory)
Microsoft Azure Active Directory (Azure AD), now Microsoft Entra ID, is Microsoft's cloud-based identity and access management service, which helps employees sign in and access resources.

**URL:** [Visit APIs.json URL](https://azure.microsoft.com/en-us/services/active-directory/)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags:

 - Authentication, Authorization, Identity, Microsoft, Microsoft Entra, OAuth, OpenID Connect, SAML, SCIM, Single Sign-On, Zero Trust

## Timestamps

- **Created:** 2024-01-15 
- **Modified:** 2026-04-18 

## APIs

### Microsoft Graph API
The Microsoft Graph API offers a single endpoint to access Azure AD data and other Microsoft 365 services.

**Human URL:** [https://docs.microsoft.com/en-us/graph/overview](https://docs.microsoft.com/en-us/graph/overview)

#### Tags:

 - Graph, Groups, Identity, Users

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/graph/api/overview)
- [OpenAPI](openapi/microsoft-graph-identity-api.yml)
- [Authentication](https://docs.microsoft.com/en-us/graph/auth/)
- [SDK](https://docs.microsoft.com/en-us/graph/sdks/sdks-overview)
- [Pricing](https://azure.microsoft.com/en-us/pricing/details/active-directory/)
- [GettingStarted](https://learn.microsoft.com/en-us/graph/use-the-api)
- [Console](https://developer.microsoft.com/en-us/graph/graph-explorer)
- [ChangeLog](https://learn.microsoft.com/en-us/graph/changelog)

### Microsoft Graph Identity and Access API
Microsoft Graph APIs for managing Microsoft Entra identity and network access capabilities.

**Human URL:** [https://learn.microsoft.com/en-us/graph/identity-network-access-overview](https://learn.microsoft.com/en-us/graph/identity-network-access-overview)

#### Tags:

 - Access Management, Authentication Methods, Conditional Access, Identity, Identity Governance

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/graph/api/resources/identity-network-access-overview?view=graph-rest-1.0)
- [OpenAPI](openapi/microsoft-graph-identity-api.yml)
- [JSONSchema](json-schema/azure-active-directory-user-schema.json)
- [JSONLD](json-ld/azure-active-directory-context.jsonld)

### Microsoft Identity Platform
The Microsoft identity platform provides authentication and authorization services using OAuth 2.0 and OpenID Connect.

**Human URL:** [https://learn.microsoft.com/en-us/entra/identity-platform/](https://learn.microsoft.com/en-us/entra/identity-platform/)

#### Tags:

 - App Registration, Authentication, Authorization, OAuth, OpenID Connect

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/entra/identity-platform/)
- [GettingStarted](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-register-app)
- [CodeExamples](https://learn.microsoft.com/en-us/entra/identity-platform/quickstart-web-app-sign-in)

### Microsoft Entra Verified ID API
Microsoft Entra Verified ID is a managed verifiable credentials service based on W3C standards.

**Human URL:** [https://learn.microsoft.com/en-us/entra/verified-id/](https://learn.microsoft.com/en-us/entra/verified-id/)

#### Tags:

 - Decentralized Identity, Identity Verification, Verifiable Credentials, W3C

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/entra/verified-id/)
- [APIReference](https://learn.microsoft.com/en-us/entra/verified-id/admin-api)
- [GettingStarted](https://learn.microsoft.com/en-us/entra/verified-id/verifiable-credentials-configure-tenant)

### Microsoft Entra ID Governance API
Microsoft Entra ID Governance APIs enable automated access reviews, entitlement management, and lifecycle workflows.

**Human URL:** [https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview)

#### Tags:

 - Access Reviews, Entitlement Management, Governance, Lifecycle Workflows, Privileged Identity Management

#### Properties

- [Documentation](https://learn.microsoft.com/en-us/entra/id-governance/identity-governance-overview)
- [APIReference](https://learn.microsoft.com/en-us/graph/api/resources/identitygovernance-overview?view=graph-rest-1.0)
- [Pricing](https://learn.microsoft.com/en-us/entra/id-governance/licensing-fundamentals)

### Microsoft Authentication Library (MSAL)
Modern authentication library for Microsoft identity platform.

**Human URL:** [https://docs.microsoft.com/en-us/azure/active-directory/develop/msal-overview](https://docs.microsoft.com/en-us/azure/active-directory/develop/msal-overview)

#### Tags:

 - Authentication, Library, OAuth, OpenID Connect

#### Properties

- [Documentation](https://docs.microsoft.com/en-us/azure/active-directory/develop/msal-overview)
- [GitHubRepository](https://github.com/AzureAD/microsoft-authentication-library-for-js)
- [CodeExamples](https://docs.microsoft.com/en-us/azure/active-directory/develop/sample-v2-code)

## Common Properties

- [Portal](https://portal.azure.com/)
- [StatusPage](https://status.azure.com/)
- [Support](https://azure.microsoft.com/en-us/support/)
- [Blog](https://techcommunity.microsoft.com/t5/azure-active-directory/bg-p/Azure-Active-Directory)
- [TermsOfService](https://azure.microsoft.com/en-us/support/legal/)
- [PrivacyPolicy](https://privacy.microsoft.com/en-us/privacystatement)
- [Pricing](https://azure.microsoft.com/en-us/pricing/details/active-directory/)
- [Training](https://docs.microsoft.com/en-us/learn/azure/)
- [DeveloperPortal](https://developer.microsoft.com/en-us/graph)
- [GitHubOrganization](https://github.com/AzureAD)
- [ReleaseNotes](https://learn.microsoft.com/en-us/entra/fundamentals/whats-new)

## Features

| Name | Description |
|------|-------------|
| Single Sign-On | Enable users to sign in once and access all connected applications without re-authenticating. |
| Conditional Access | Enforce granular access policies based on user, device, location, and risk signals for zero trust security. |
| Multi-Factor Authentication | Add a second layer of security with phone, app, or hardware token verification for identity protection. |
| SCIM User Provisioning | Automate user and group lifecycle management across cloud applications using SCIM 2.0 standard. |
| Verifiable Credentials | Issue and verify decentralized identity credentials based on W3C standards for privacy-preserving identity verification. |
| Identity Governance | Automate access reviews, entitlement management, and lifecycle workflows for identity governance at scale. |
| Application Proxy | Publish on-premises web applications externally with secure remote access without VPN infrastructure. |

## Use Cases

| Name | Description |
|------|-------------|
| Enterprise SSO | Implement single sign-on across SaaS and on-premises applications for seamless employee access management. |
| B2B Collaboration | Enable secure collaboration with external partners and guests using Azure AD B2B identity federation. |
| Customer Identity | Build customer-facing applications with self-service sign-up, social identity providers, and branded login experiences. |
| Zero Trust Security | Implement zero trust architecture with conditional access policies, continuous access evaluation, and risk-based authentication. |
| Automated User Provisioning | Automate user account creation, updates, and deprovisioning across connected SaaS applications using SCIM. |

## Integrations

| Name | Description |
|------|-------------|
| Microsoft 365 | Native identity provider for all Microsoft 365 applications including Teams, Outlook, SharePoint, and OneDrive. |
| Salesforce | Single sign-on and automated user provisioning for Salesforce CRM using SAML and SCIM protocols. |
| ServiceNow | Federated authentication and automated user lifecycle management for ServiceNow ITSM platform. |
| AWS | Cross-cloud identity federation enabling Azure AD users to access AWS resources with single sign-on. |
| Workday | HR-driven identity provisioning with automated user creation and attribute synchronization from Workday. |

## Artifacts

Machine-readable API specifications organized by format.

### OpenAPI

- [Microsoft Graph Identity API](openapi/microsoft-graph-identity-api.yml)

## Capabilities

Naftiko capabilities organized as shared per-API definitions composed into customer-facing workflows.

### Shared Per-API Definitions

- [Microsoft Graph Identity API](capabilities/shared/microsoft-graph-identity.yaml) -- 25 operations for user, group, application, and service principal management

### Workflow Capabilities

| Workflow | APIs Combined | Tools | Persona |
|----------|--------------|-------|---------|
| [Identity and Access Management](capabilities/identity-and-access.yaml) | Microsoft Graph Identity | 17 | IT Administrator / Identity Engineer |

## Maintainers

**FN:** Microsoft

**Email:** azuread@microsoft.com

**FN:** Kin Lane

**Email:** kin@apievangelist.com
