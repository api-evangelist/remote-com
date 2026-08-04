# Remote (remote-com)

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

Remote.com is a global employment platform that lets companies hire,
pay, and manage employees and contractors in 90+ countries without
setting up local entities. Remote owns in-country legal entities
across its EOR footprint and runs its own global payroll and benefits
infrastructure rather than reselling third-party providers. The
platform layers a developer API, partner OAuth flows, webhooks, a
CLI, language SDKs, an AI agent toolkit, and an official MCP server
on top of these services so customers and partners can fully automate
hiring, onboarding, payroll, benefits, time off, expenses, and
offboarding.

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/remote-com/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/remote-com/refs/heads/main/apis.yml)

## Tags

- Global Payroll
- EOR
- Contractor Management
- Contractor of Record
- PEO
- HRIS
- Recruiting
- Benefits
- Employment
- HR
- Compliance
- Workforce
- MCP
- AI Agents

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## APIs

### Remote Companies API

Create and manage companies on Remote. Entry point for every
Remote integration — partners use this API to provision new
customer companies and obtain company-scoped access tokens. Also
covers company managers, departments, legal entities, compliance
profile, hiring eligibility reserves, SSO configuration, token
identity, and magic-link generation.

- **Human URL:** [https://developer.remote.com/reference/welcome-to-remote-api](https://developer.remote.com/reference/welcome-to-remote-api)
- **Base URL:** `https://gateway.remote.com/v1`

#### Tags

- Companies
- Compliance
- SSO
- Identity

#### Properties

- [Documentation](https://developer.remote.com/reference/welcome-to-remote-api)
- [Documentation](https://developer.remote.com/docs/creating-a-company)
- [OpenAPI](openapi/remote-companies-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/remote-companies-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-companies-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/remote-company-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/remote-com-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)

### Remote Employments API

Manage employment records across EOR, Global Payroll, and PEO
models. Covers the full lifecycle — create, invite, onboard,
sign contracts, amend contracts, run identity verification,
file travel-letter and work-authorization requests, manage
company structure, and offboard. Authoritative source of truth
for every worker record on Remote.

- **Human URL:** [https://developer.remote.com/docs/create-new-employment](https://developer.remote.com/docs/create-new-employment)
- **Base URL:** `https://gateway.remote.com/v1`

#### Tags

- Employments
- Onboarding
- Offboarding
- Contracts
- Travel Letters
- Work Authorization

#### Properties

- [Documentation](https://developer.remote.com/docs/create-new-employment)
- [Documentation](https://developer.remote.com/docs/employment-lifecycle-stages)
- [Documentation](https://developer.remote.com/docs/employment-statuses)
- [OpenAPI](openapi/remote-employments-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/remote-employments-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-employments-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/remote-employment-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/remote-com-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Example](examples/remote-create-employment-example.json)

### Remote Contractors API

Manage contractor subscriptions across the Standard, Plus
(indemnity), and Contractor-of-Record plans. Surfaces include
contractor invoices, scheduled-invoice automation,
contract-eligibility checks (powered by Remote's AI
misclassification tooling), COR termination requests, and
contractor currency catalogs.

- **Human URL:** [https://developer.remote.com/reference/welcome-to-remote-api](https://developer.remote.com/reference/welcome-to-remote-api)
- **Base URL:** `https://gateway.remote.com/v1`

#### Tags

- Contractors
- COR
- Contractor of Record
- Invoices
- Misclassification

#### Properties

- [Documentation](https://developer.remote.com/reference/welcome-to-remote-api)
- [OpenAPI](openapi/remote-contractors-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/remote-contractors-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-contractors-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Remote Payroll and Billing API

Inspect payroll calendars, billing documents (with itemized
breakdowns and PDF download), incentives (one-time bonuses and
recurring incentives), expenses (with approve/decline/reimburse
flows), payslips, and company billing currencies. The financial
backbone of every Remote engagement.

- **Human URL:** [https://developer.remote.com/docs/quick-start-guide-2](https://developer.remote.com/docs/quick-start-guide-2)
- **Base URL:** `https://gateway.remote.com/v1`

#### Tags

- Payroll
- Billing
- Incentives
- Expenses
- Payslips
- FinOps

#### Properties

- [Documentation](https://developer.remote.com/docs/quick-start-guide-2)
- [Documentation](https://developer.remote.com/docs/working-with-expenses)
- [Documentation](https://developer.remote.com/docs/working-with-incentives)
- [OpenAPI](openapi/remote-payroll-billing-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/remote-payroll-billing-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-payroll-billing-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/remote-billing-document-schema.json) — [JSON Schema](https://json-schema.org/specification)

### Remote Time and Attendance API

Manage time-off requests, leave policies, leave balances, and
timesheets. Approve/decline/cancel flows for managers; submit
and self-serve flows for employees. Every state change is also
emitted via webhook events.

- **Human URL:** [https://developer.remote.com/docs/working-with-time-off](https://developer.remote.com/docs/working-with-time-off)
- **Base URL:** `https://gateway.remote.com/v1`

#### Tags

- Time Off
- Leave
- Timesheets
- HRIS

#### Properties

- [Documentation](https://developer.remote.com/docs/working-with-time-off)
- [Documentation](https://developer.remote.com/docs/leave-policies-summary)
- [Documentation](https://developer.remote.com/docs/working-with-timesheets)
- [OpenAPI](openapi/remote-time-attendance-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/remote-time-attendance-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-time-attendance-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/remote-time-off-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [Example](examples/remote-create-timeoff-example.json)

### Remote Benefits API

List localized benefit offers by country, attach offers to
employments using JSON Schema forms, and respond to annual
benefit-renewal requests. Backed by Remote's in-country
benefits infrastructure.

- **Human URL:** [https://developer.remote.com/docs/benefits-renewal](https://developer.remote.com/docs/benefits-renewal)
- **Base URL:** `https://gateway.remote.com/v1`

#### Tags

- Benefits
- Health
- Pension
- Renewals

#### Properties

- [Documentation](https://developer.remote.com/docs/benefits-renewal)
- [OpenAPI](openapi/remote-benefits-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/remote-benefits-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-benefits-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Remote Files and Custom Fields API

Upload and download files attached to employments, companies,
and expenses. Define and set customer-managed custom fields on
companies and employments. List supported countries and their
employment models. Estimate the loaded annual cost of hiring an
employee in any country via the cost calculator.

- **Human URL:** [https://developer.remote.com/docs/working-with-files](https://developer.remote.com/docs/working-with-files)
- **Base URL:** `https://gateway.remote.com/v1`

#### Tags

- Files
- Documents
- Custom Fields
- Countries
- Cost Calculator

#### Properties

- [Documentation](https://developer.remote.com/docs/working-with-files)
- [Documentation](https://developer.remote.com/docs/custom-fields)
- [Documentation](https://developer.remote.com/docs/working-with-countries)
- [Documentation](https://developer.remote.com/docs/employment-cost-estimation)
- [OpenAPI](openapi/remote-files-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/remote-files-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-files-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Example](examples/remote-cost-estimate-example.json)

### Remote OAuth 2.0 API

OAuth 2.0 endpoints used to obtain access tokens for the Remote
API. Four supported flows — authorization code (customer apps
and partners), client credentials (partners), JWT bearer
assertion (partners acting for a specific company), and refresh
token. Plus magic-link generation for passwordless employee
sign-in.

- **Human URL:** [https://developer.remote.com/docs/authentication](https://developer.remote.com/docs/authentication)
- **Base URL:** `https://gateway.remote.com`

#### Tags

- OAuth
- Authentication
- Authorization
- Partners

#### Properties

- [Documentation](https://developer.remote.com/docs/authentication)
- [Documentation](https://developer.remote.com/docs/authorization-for-customers)
- [Documentation](https://developer.remote.com/docs/client-credentials-flow-for-partners)
- [Documentation](https://developer.remote.com/docs/authorization-method-oauth-assertion)
- [Documentation](https://developer.remote.com/docs/refresh-token-flow)
- [OpenAPI](openapi/remote-oauth-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/remote-oauth-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-oauth-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Example](examples/remote-oauth-token-exchange-example.json)

### Remote Webhooks

Remote emits webhook events for every meaningful state change
across companies, employments, contractors, payroll, billing,
time off, timesheets, benefits, identity verification, and SSO.
Webhooks are signed with `X-Remote-Signature` and delivered to a
customer-managed HTTPS endpoint. 90+ event types in total.

- **Human URL:** [https://developer.remote.com/docs/available-webhooks](https://developer.remote.com/docs/available-webhooks)
- **Base URL:** `https://gateway.remote.com`

#### Tags

- Webhooks
- Events
- AsyncAPI

#### Properties

- [Documentation](https://developer.remote.com/docs/available-webhooks)
- [Documentation](https://developer.remote.com/docs/working-with-webhooks)
- [Documentation](https://developer.remote.com/docs/verifying-webhooks)
- [AsyncAPI](asyncapi/remote-webhooks-asyncapi.yml) — [AsyncAPI Specification](https://www.asyncapi.com/docs/reference/specification/latest)
- [Example](examples/remote-employment-onboarding-completed-webhook-example.json)
- [Postman Collection](collections/remote-benefits-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-benefits-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/remote-companies-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-companies-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/remote-contractors-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-contractors-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/remote-employments-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-employments-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/remote-files-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-files-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/remote-oauth-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-oauth-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/remote-payroll-billing-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-payroll-billing-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/remote-time-attendance-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/remote-time-attendance-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Arazzo Workflows](arazzo/) — [Arazzo Specification](https://spec.openapis.org/arazzo/latest.html)
- [Web Site](https://remote.com)
- [Developer Portal](https://developer.remote.com)
- [L L M S Text](https://developer.remote.com/llms.txt)
- [Changelog](https://developer.remote.com/docs/changelogs)
- [Status Page](https://remote.com/status)
- [Security](https://trust.remote.com)
- [Pricing](https://remote.com/pricing)
- [Blog](https://remote.com/blog)
- [Support](https://support.remote.com)
- [Terms of Service](https://remote.com/legal/terms)
- [Privacy](https://remote.com/legal/privacy)
- [Careers](https://remote.com/careers)
- [Twitter](https://twitter.com/remote)
- [LinkedIn](https://www.linkedin.com/company/remote-com)
- [Git Hub](https://github.com/remoteoss)
- [Plans](plans/remote-com-plans-pricing.yml)
- [Rate Limits](rate-limits/remote-com-rate-limits.yml)
- [Fin Ops](finops/remote-com-finops.yml)
- [Spectral Rules](rules/remote-com-rules.yml)
- [Vocabulary](vocabulary/remote-com-vocabulary.yml)
- [Review](review.yml)
- [C L I](https://github.com/remoteoss/remote-cli)
- [SDK](https://github.com/remoteoss/ai-agent-toolkit)
- [SDK](https://github.com/remoteoss/remote-flows)
- [SDK](https://github.com/remoteoss/json-schema-form)
- [SDK](https://github.com/remoteoss/react-url-modal)
- [Integration](https://github.com/remoteoss/remote-for-ai)
- [M C P](https://developer.remote.com/docs/introduction-to-remote-mcp)
