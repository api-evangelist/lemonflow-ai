# Lemonflow

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
