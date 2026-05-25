# Remote (remote-com)
Remote is a global employment platform that lets companies hire, pay, and manage employees and contractors in 90+ countries without setting up local entities. Remote owns in-country legal entities across its EOR footprint and runs its own global payroll and benefits infrastructure rather than reselling third-party providers. The platform layers a developer API, partner OAuth flows, signed webhooks, a CLI, language SDKs, an AI agent toolkit, and an official MCP server on top of these services so customers and partners can automate hiring, onboarding, payroll, benefits, time off, expenses, and offboarding end-to-end.

**URL:** [Visit APIs.yml](https://raw.githubusercontent.com/api-evangelist/remote-com/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=company-api-evangelist&utm_content=repo)

## Tags

- Global Payroll, EOR, Contractor Management, Contractor of Record, PEO, HRIS, Recruiting, Benefits, Employment, HR, Compliance, Workforce, MCP, AI Agents

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25

## Environments

| Environment | API Base URL | UI |
|---|---|---|
| Production | `https://gateway.remote.com/v1` | https://remote.com |
| Sandbox | `https://gateway.remote-sandbox.com/v1` | https://remote-sandbox.com |
| Partners Sandbox | `https://gateway.partners.remote-sandbox.com/v1` | https://partners.remote-sandbox.com |

## Authentication

| Flow | Used By | Result |
|---|---|---|
| Authorization Code | Customer apps and partners | Company-scoped access token (+ refresh token) |
| Client Credentials | Partners | Partner-scoped access token |
| JWT Bearer Assertion | Partners acting for a specific company | Company-scoped access token |
| Refresh Token | All clients | New access token |
| Magic Link | Users and employees | Single-use passwordless sign-in URL |

All API calls use `Authorization: Bearer {access_token}`. See [openapi/remote-oauth-api-openapi.yml](openapi/remote-oauth-api-openapi.yml).

## Rate Limits

- 300 authenticated requests per 60-second window, applied **per company** (shared across every token belonging to the same company).
- Response headers: `x-ratelimit-count`, `x-ratelimit-remaining`, `x-ratelimit-reset` (ms until window reset).
- Throttling returns HTTP 429 with body `{"errors": {"detail": "Customer rate-limit exceeded."}}`.
- Full policy in [rate-limits/remote-com-rate-limits.yml](rate-limits/remote-com-rate-limits.yml).

## Pricing

| Plan | Monthly Price | Notes |
|---|---|---|
| Recruit | from $199 / month | AI candidate sourcing, 800m+ profiles |
| Employer of Record (Monthly) | $699 / employee / month | 90+ countries, no entity required |
| Employer of Record (Annual) | $599 / employee / month | 14% savings vs monthly |
| Global Payroll | $29 / employee / month | + entity implementation fee + per-payroll delivery fee |
| Contractor Management (Standard) | $29 / contractor / month | Localized contracts, invoice approval |
| Contractor Management (Plus) | $99 / contractor / month | Adds $100k indemnity protection |
| Contractor of Record | from $325 / contractor / month | Uncapped indemnity, IP transfer |
| PEO (US) | from $99 / employee / month | US-only co-employment |
| Equity | from $39 / month | Equity grants administration |
| HR Management (HRIS) — Free | $0 | Free for direct employees on Remote |
| HR Management — Plus | $12 / employee / month | Advanced HRIS features |

Discounts: 15% for startups; 15% for social-purpose organizations. 12 billing currencies supported. Full plans in [plans/remote-com-plans-pricing.yml](plans/remote-com-plans-pricing.yml).

## APIs

### Remote Companies API
Create and manage companies on Remote — the entry point for every integration. Includes managers, departments, legal entities, compliance profile and hiring-eligibility reserves, SSO configuration, token identity, and magic-link generation.

**Human URL:** [https://developer.remote.com/reference/welcome-to-remote-api](https://developer.remote.com/reference/welcome-to-remote-api)

- [Documentation — Welcome](https://developer.remote.com/reference/welcome-to-remote-api)
- [Documentation — Company Creation](https://developer.remote.com/docs/creating-a-company)
- [OpenAPI](openapi/remote-companies-api-openapi.yml)
- [JSON Schema — Company](json-schema/remote-company-schema.json)
- [JSON-LD](json-ld/remote-com-context.jsonld)
- [Naftiko Capability — Companies](capabilities/companies-companies.yaml)

### Remote Employments API
Manage employment records across EOR, Global Payroll, and PEO models — create, invite, onboard, sign contracts, amend contracts, run identity verification, file travel-letter and work-authorization requests, manage company structure, and offboard.

**Human URL:** [https://developer.remote.com/docs/create-new-employment](https://developer.remote.com/docs/create-new-employment)

- [Documentation — Create Employment](https://developer.remote.com/docs/create-new-employment)
- [Documentation — Employment Lifecycle Stages](https://developer.remote.com/docs/employment-lifecycle-stages)
- [Documentation — Employment Statuses](https://developer.remote.com/docs/employment-statuses)
- [OpenAPI](openapi/remote-employments-api-openapi.yml)
- [JSON Schema — Employment](json-schema/remote-employment-schema.json)
- [Naftiko Capability — Employments](capabilities/employments-employments.yaml)
- [Example — Create Employment](examples/remote-create-employment-example.json)

### Remote Contractors API
Manage contractor subscriptions across the Standard, Plus (indemnity), and Contractor-of-Record plans. Covers contractor invoices, scheduled-invoice automation, contract-eligibility checks (powered by Remote's AI misclassification tooling), COR termination requests, and contractor currency catalogs.

**Human URL:** [https://developer.remote.com/reference/welcome-to-remote-api](https://developer.remote.com/reference/welcome-to-remote-api)

- [OpenAPI](openapi/remote-contractors-api-openapi.yml)
- [Naftiko Capability — Contractors](capabilities/contractors-contractors.yaml)

### Remote Payroll and Billing API
Inspect payroll calendars, billing documents (itemized breakdowns + PDF), incentives, expenses, payslips, and company billing currencies. The financial backbone of every Remote engagement.

**Human URL:** [https://developer.remote.com/docs/quick-start-guide-2](https://developer.remote.com/docs/quick-start-guide-2)

- [Documentation — Working With Expenses](https://developer.remote.com/docs/working-with-expenses)
- [Documentation — Incentives](https://developer.remote.com/docs/working-with-incentives)
- [OpenAPI](openapi/remote-payroll-billing-api-openapi.yml)
- [JSON Schema — Billing Document](json-schema/remote-billing-document-schema.json)
- [Naftiko Capability — Payroll & Billing](capabilities/payroll-billing.yaml)
- [Naftiko Capability — Expenses](capabilities/expenses.yaml)

### Remote Time and Attendance API
Manage time-off requests, leave policies, leave balances, and timesheets. Approve/decline/cancel flows for managers; submit and self-serve flows for employees. Every state change is emitted via webhook.

**Human URL:** [https://developer.remote.com/docs/working-with-time-off](https://developer.remote.com/docs/working-with-time-off)

- [Documentation — Time Off](https://developer.remote.com/docs/working-with-time-off)
- [Documentation — Leave Policies](https://developer.remote.com/docs/leave-policies-summary)
- [Documentation — Timesheets](https://developer.remote.com/docs/working-with-timesheets)
- [OpenAPI](openapi/remote-time-attendance-api-openapi.yml)
- [JSON Schema — Time Off](json-schema/remote-time-off-schema.json)
- [Naftiko Capability — Time Off](capabilities/time-off.yaml)
- [Naftiko Capability — Timesheets](capabilities/timesheets.yaml)
- [Example — Create Time Off](examples/remote-create-timeoff-example.json)

### Remote Benefits API
List localized benefit offers by country, attach offers to employments using JSON Schema forms, and respond to annual benefit-renewal requests.

**Human URL:** [https://developer.remote.com/docs/benefits-renewal](https://developer.remote.com/docs/benefits-renewal)

- [Documentation](https://developer.remote.com/docs/benefits-renewal)
- [OpenAPI](openapi/remote-benefits-api-openapi.yml)
- [Naftiko Capability — Benefits](capabilities/benefits.yaml)

### Remote Files and Custom Fields API
Upload and download files; define and set customer-managed custom fields on companies and employments; list supported countries; estimate the loaded annual cost of hiring an employee in any country.

**Human URL:** [https://developer.remote.com/docs/working-with-files](https://developer.remote.com/docs/working-with-files)

- [Documentation — Files](https://developer.remote.com/docs/working-with-files)
- [Documentation — Custom Fields](https://developer.remote.com/docs/custom-fields)
- [Documentation — Countries](https://developer.remote.com/docs/working-with-countries)
- [Documentation — Cost Estimation](https://developer.remote.com/docs/employment-cost-estimation)
- [OpenAPI](openapi/remote-files-api-openapi.yml)
- [Naftiko Capability — Cost Calculator](capabilities/cost-calculator.yaml)
- [Example — Cost Estimate](examples/remote-cost-estimate-example.json)

### Remote OAuth 2.0 API
OAuth 2.0 endpoints — authorization code, client credentials, JWT bearer assertion, and refresh token flows. Plus magic-link generation for passwordless employee sign-in.

**Human URL:** [https://developer.remote.com/docs/authentication](https://developer.remote.com/docs/authentication)

- [Documentation — Authentication](https://developer.remote.com/docs/authentication)
- [Documentation — Customer Authorization](https://developer.remote.com/docs/authorization-for-customers)
- [Documentation — Client Credentials (Partners)](https://developer.remote.com/docs/client-credentials-flow-for-partners)
- [Documentation — JWT Assertion](https://developer.remote.com/docs/authorization-method-oauth-assertion)
- [Documentation — Refresh Token](https://developer.remote.com/docs/refresh-token-flow)
- [OpenAPI](openapi/remote-oauth-api-openapi.yml)
- [Naftiko Capability — OAuth](capabilities/oauth.yaml)
- [Example — Token Exchange](examples/remote-oauth-token-exchange-example.json)

### Remote Webhooks
Remote emits 90+ signed webhook events covering companies, employments, contractors, payroll, billing, time off, timesheets, benefits, identity verification, and SSO. All events POST a signed JSON envelope to a customer-managed HTTPS endpoint and must be verified using the `X-Remote-Signature` header.

**Human URL:** [https://developer.remote.com/docs/available-webhooks](https://developer.remote.com/docs/available-webhooks)

- [Documentation — Available Webhooks](https://developer.remote.com/docs/available-webhooks)
- [Documentation — Working With Webhooks](https://developer.remote.com/docs/working-with-webhooks)
- [Documentation — Verifying Webhooks](https://developer.remote.com/docs/verifying-webhooks)
- [AsyncAPI](asyncapi/remote-webhooks-asyncapi.yml)
- [Example — onboarding.completed Webhook](examples/remote-employment-onboarding-completed-webhook-example.json)

## SDKs, CLI, and AI Tooling

| Tool | Package | Repo |
|---|---|---|
| Remote CLI | `curl ... install.sh \| sh` (Shell binary) | [remoteoss/remote-cli](https://github.com/remoteoss/remote-cli) |
| AI Agent Toolkit | `@remoteoss/ai-agent-toolkit` (npm) | [remoteoss/ai-agent-toolkit](https://github.com/remoteoss/ai-agent-toolkit) |
| Remote Flows (React Embedded SDK) | `@remoteoss/remote-flows` (npm) | [remoteoss/remote-flows](https://github.com/remoteoss/remote-flows) |
| JSON Schema Form | `@remoteoss/json-schema-form` (npm) | [remoteoss/json-schema-form](https://github.com/remoteoss/json-schema-form) |
| react-url-modal | `@remoteoss/react-url-modal` (npm) | [remoteoss/react-url-modal](https://github.com/remoteoss/react-url-modal) |
| Remote MCP / Remote-for-AI plugin | Claude Code, Cursor, Codex, Gemini CLI | [remoteoss/remote-for-ai](https://github.com/remoteoss/remote-for-ai) |
| Remote.com MCP server | OAuth 2.0; PII-aware | [Docs](https://developer.remote.com/docs/introduction-to-remote-mcp) |

## Integrations

Workday · HiBob · BambooHR · Personio · [Merge unified-API](https://developer.remote.com/docs/build-with-merge).

## Solutions

Global Hiring · Global Payroll · Contractor Management · US PEO · Equity Administration · Recruit · AI Agents.

## Operational Surface

- **Status:** [remote.com/status](https://remote.com/status)
- **Security & Trust:** [trust.remote.com](https://trust.remote.com) — SOC 2 Type 2, ISO 27001
- **Changelog:** [developer.remote.com/docs/changelogs](https://developer.remote.com/docs/changelogs)
- **Support:** [support.remote.com](https://support.remote.com)
- **LLMs.txt:** [developer.remote.com/llms.txt](https://developer.remote.com/llms.txt) — AI-discoverable index of every documentation page and OpenAPI operation
- **GitHub:** [github.com/remoteoss](https://github.com/remoteoss)

## Artifacts

| Artifact | Path |
|---|---|
| Plans (API Commons Plans 0.1) | [plans/remote-com-plans-pricing.yml](plans/remote-com-plans-pricing.yml) |
| Rate Limits (API Commons Rate Limits 0.1) | [rate-limits/remote-com-rate-limits.yml](rate-limits/remote-com-rate-limits.yml) |
| FinOps (FOCUS-aligned) | [finops/remote-com-finops.yml](finops/remote-com-finops.yml) |
| JSON-LD context | [json-ld/remote-com-context.jsonld](json-ld/remote-com-context.jsonld) |
| Spectral ruleset | [rules/remote-com-rules.yml](rules/remote-com-rules.yml) |
| Vocabulary | [vocabulary/remote-com-vocabulary.yml](vocabulary/remote-com-vocabulary.yml) |
