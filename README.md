# Microsoft Azure Active Directory (microsoft-azure-active-directory)

<!-- API-EVANGELIST-PROVENANCE:BEGIN -->
> ### About this repository
>
> **This is not our API.** This repository is an independent, third-party profile of a company's
> **publicly available** API surface, maintained by [API Evangelist](https://apievangelist.com).
> API Evangelist does not operate, host, resell, or support this company's APIs, and is not
> affiliated with or endorsed by the company unless stated on the profile.
>
> **Where the information came from.** Everything here is assembled from material a member of the
> public can reach with a browser and no credentials — the company's own website, developer portal
> and documentation, the specifications it publishes for public use (OpenAPI, AsyncAPI, JSON Schema,
> `apis.json`, `llms.txt` and similar), its public repositories, and its public status, pricing and
> changelog pages. **Nothing here is obtained by breaching a system, defeating an access control, or
> using credentials of any kind.**
>
> **The rating is an independent assessment.** The Kin Score and Agent Readiness rating are
> independently calculated scores of a company's *public* API artifacts, produced by API Evangelist
> against a published rubric. They are not certifications, endorsements, security assessments, or
> audits, and they score published artifacts — not the quality, safety, or security of the software.
>
> **Corrections, re-scores, and removal are free.** No partnership, contract, or purchase is
> required, and you do not need to justify the request.
>
> - **Something wrong?** Open an issue on this repository, or email
>   [info@apievangelist.com](mailto:info@apievangelist.com).
> - **Published something new?** Ask for a re-score and we will re-run the rating.
> - **Want the listing taken down?** Say so and we will honor it. The profile is reduced to your
>   company name, a factual description, and a link to your own site, and the company is recorded as
>   **unrated** — never scored zero for having asked.
>
> **Response times.** Acknowledgement within **one business day**; removal or restriction within
> **two business days**; corrections and re-scores within **five business days**.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

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
