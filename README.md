# Lemonflow

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
> **Not from the company, and here with a question?** You are welcome here — we would rather be the
> front line and point you the right way than have a good report go nowhere. What this repository
> can answer is narrow, though, so it is worth knowing who you are actually looking for:
>
> - **A question about how the API works, an account, billing, or a bug in the service** — that is
>   the company's own support, not us. We profile this API; we do not operate it and cannot see
>   your account.
> - **A bug in an open-source project we only catalog** — file it on that project's own repository.
>   This has happened with a real and correct bug report that reached us instead of the people who
>   could fix it, which helped nobody.
> - **Anything about this listing itself** — the description, the tags, the rating, a missing or
>   wrong artifact — is ours. Open an issue here.
> - **Not sure, or something general about API Evangelist or APIs.io** — open an issue on the
>   [APIs.io Inbox](https://github.com/api-search/inbox) and we will route it.
>
> **This repository contains no software, and we will never ask you to download anything.** There is
> no build, release, installer, or binary here — only text and machine-readable API descriptions, so
> there is nothing here that can be "corrupt" or need "repairing". Any issue, comment, or email
> claiming otherwise and offering a download link is not from us and is hostile. Do not follow the
> link; it is a lure. Report it to GitHub and, if you like, tell us at
> [info@apievangelist.com](mailto:info@apievangelist.com) so we can take it down.
>
> **On a security or compliance team?** Email
> [info@apievangelist.com](mailto:info@apievangelist.com) with *security* in the subject line and
> you will get a person, not a form. We will tell you exactly which public URLs this profile was
> built from so your team can see the same surface we did, and we will take the listing down on
> request while you work through it.
>
> Full detail: **[Where this data comes from](https://apievangelist.com/about/where-our-data-comes-from)**
<!-- API-EVANGELIST-PROVENANCE:END -->

Lemonflow Technologies GmbH (Munich, Germany) builds AI agents purpose-built for the
electric-vehicle charging industry — 24/7 driver support across voice, chat and email
in 30+ languages, plus an Operations Hub for proactive network monitoring, OCPP log
interpretation and self-healing automations such as remote charger resets.

The developer-facing surface is the **Lemonflow Chat Widget** — a `lemonflow-chat`
web component (or an equivalent headless iframe) loaded from `chat.lemonflow.ai` and
driven through a `postMessage` command/event API — together with a documented set of
CPMS integration requirements covering bulk station data, real-time status, OCPP logs,
remote actions and ticketing.

- Website: https://lemonflow.ai
- Documentation: https://lemonflow-ai.github.io/lemonflow-docs/
- GitHub: https://github.com/lemonflow-ai
- Status: https://status.lemonflow.ai
- Trust Center: https://trust.lemonflow.ai

Backed by: Speedinvest

## Artifacts in this repo

| Directory | Artifact |
|---|---|
| `authentication/` | Company ID + public-key model for the widget; partner-side auth options |
| `components/` | Chat Widget web component + headless iframe, attributes, events, a11y |
| `conformance/` | OCPP 1.6/2.0.1, WCAG 2.1 AA, GDPR/EU hosting, ISO 27001 & SOC 2 alignment |
| `conventions/` | postMessage envelopes, tracing, versioning, error envelope, latency budgets |
| `data-model/` | Location → Station → EVSE → Connector → Session hierarchy + conversation entities |
| `errors/` | Widget `chat:error` surface + documented HTTP semantics for partner endpoints |
| `integrations/` | The five CPMS endpoints Lemonflow asks partners to expose, plus channels |
| `lifecycle/` | incident.io status page, agent versioning, doc revision dates |
| `llms/` | Verbatim `llms.txt` published at the apex host |
| `packages/` | Registry sweep — no first-party client libraries published |
| `security/` | Probed TLS/HSTS/DNSSEC/SPF/DMARC posture + Vanta Trust Center |
| `well-known/` | `/.well-known/` sweep (all 404) + robots.txt Content-Signal directives |

## Notes

- Lemonflow publishes **no OpenAPI definition** and no public REST API. The API guides
  in its documentation describe the endpoints a **partner CPMS** should expose, not
  Lemonflow's own. Artifacts here label that distinction explicitly.
- The documentation portal is StatiCrypt password-gated in two tiers (Tech,
  Operations); credentials come from `tech@lemonflow.ai`. The unencrypted sources are
  public in `lemonflow-ai/lemonflow-docs`.
- No MCP server, CLI, sandbox, OAuth scopes, AsyncAPI or published SDKs were found.
