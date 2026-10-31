# Prometheus

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

Prometheus is a Cloud Native Computing Foundation graduated open source systems monitoring and alerting toolkit. A Prometheus server scrapes metrics over HTTP from instrumented targets, stores them in an embedded time series database, and lets operators query, alert, and aggregate them with the PromQL query language. The project pairs the Prometheus server with Alertmanager for alert routing and silencing, official client libraries for Go, Java, Python, Ruby, and Rust, and a large ecosystem of exporters (node, blackbox, snmp, statsd, jmx, mysqld, cloudwatch, consul, graphite, memcached, pushgateway, etc.) for pulling metrics out of existing systems. Prometheus also drives the OpenMetrics exposition format and an experimental Remote Write 2.0 protocol for shipping samples to long-term storage backends.

**Areas:** Prometheus · Monitoring · Metrics · Observability · Time Series · Alerting · Cloud-Native · CNCF · Open Source · PromQL · Telemetry

## Prometheus on APIs.io

Everything profiled for Prometheus is published on APIs.io rather than in this repository. Start at the provider page — **[apis.io/providers/prometheus-io/](https://apis.io/providers/prometheus-io/)** — or go straight to one of the APIs or properties below.

### APIs (21)

- [Prometheus Remote Write](https://apis.io/apis/prometheus-io/prometheus-remote-write/) — Remote Write is Prometheus' push protocol for shipping scraped samples to long-term storage and analysis backends (Cortex, Thanos, Mimir, VictoriaMetrics,…
- [Prometheus Exposition Format / OpenMetrics](https://apis.io/apis/prometheus-io/prometheus-exposition-format/) — The text-based exposition format that every instrumented target exposes (typically on /metrics) and that the Prometheus server scrapes over HTTP. The format…
- [Prometheus OTLP Metrics Receiver](https://apis.io/apis/prometheus-io/prometheus-otlp-receiver/) — Optional OpenTelemetry Protocol metrics receiver exposed on /api/v1/otlp/v1/metrics when the Prometheus server is started with --web.enable-otlp-receiver.…
- [Prometheus Admin API](https://apis.io/apis/prometheus-io/prometheus-io-admin-api/) — Administrative operations for TSDB management.
- [Prometheus Alert API](https://apis.io/apis/prometheus-io/prometheus-io-alert-api/) — Everything related to Alertmanager alerts
- [Prometheus Alertgroup API](https://apis.io/apis/prometheus-io/prometheus-io-alertgroup-api/) — The alertgroup API from Prometheus — 1 operation(s) for alertgroup.
- [Prometheus Alerts API](https://apis.io/apis/prometheus-io/prometheus-io-alerts-api/) — Query active alerts and alertmanager discovery.
- [Prometheus Features API](https://apis.io/apis/prometheus-io/prometheus-io-features-api/) — Query enabled features.
- [Prometheus General API](https://apis.io/apis/prometheus-io/prometheus-io-general-api/) — General Alertmanager operations
- [Prometheus Labels API](https://apis.io/apis/prometheus-io/prometheus-io-labels-api/) — Query label names and values.
- [Prometheus Metadata API](https://apis.io/apis/prometheus-io/prometheus-io-metadata-api/) — Retrieve metric metadata such as type and unit.
- [Prometheus Notifications API](https://apis.io/apis/prometheus-io/prometheus-io-notifications-api/) — Server notifications and events.
- [Prometheus Otlp API](https://apis.io/apis/prometheus-io/prometheus-io-otlp-api/) — OpenTelemetry Protocol metrics ingestion.
- [Prometheus Query API](https://apis.io/apis/prometheus-io/prometheus-io-query-api/) — Query and evaluate PromQL expressions.
- [Prometheus Receiver API](https://apis.io/apis/prometheus-io/prometheus-io-receiver-api/) — Everything related to Alertmanager receivers
- [Prometheus Remote API](https://apis.io/apis/prometheus-io/prometheus-io-remote-api/) — Remote read and write endpoints.
- [Prometheus Rules API](https://apis.io/apis/prometheus-io/prometheus-io-rules-api/) — Query recording and alerting rules.
- [Prometheus Series API](https://apis.io/apis/prometheus-io/prometheus-io-series-api/) — Query and manage time series.
- [Prometheus Silence API](https://apis.io/apis/prometheus-io/prometheus-io-silence-api/) — Everything related to Alertmanager silences
- [Prometheus Status API](https://apis.io/apis/prometheus-io/prometheus-io-status-api/) — Retrieve server status and configuration.
- [Prometheus Targets API](https://apis.io/apis/prometheus-io/prometheus-io-targets-api/) — Retrieve target and scrape pool information.

### Published properties

Each property below is a page on APIs.io carrying the machine-readable artifact and what it says.

#### GraphQL (1)

GraphQL schemas.

- [Moved to /providers/prometheus-io/](https://apis.io/graphqls/prometheus-io/prometheus-io-graphql/)

#### Agentic access (1)

Which operations an agent can call, which act, and which need a human in the loop.

- [Prometheus Io Agentic Access](https://apis.io/agentic-access/prometheus-io/prometheus-io-agentic-access/)

#### JSON Schema (2)

The data models the API reads and writes.

- [Prometheus Query Result](https://apis.io/schemas/prometheus-io/prometheus-query-result/)
- [Prometheus Scrape Target](https://apis.io/schemas/prometheus-io/prometheus-target/)

#### JSON-LD (1)

Linked-data contexts for the provider's vocabulary.

- [Prometheus Io Context](https://apis.io/jsonld/prometheus-io/prometheus-io-context/)

#### Vocabulary (1)

The provider's domain terms, defined.

- [Prometheus Vocabulary](https://apis.io/vocabularies/prometheus-io/prometheus-io-vocabulary/)

#### Examples (3)

Example requests and responses.

- [Prometheus Query Example](https://apis.io/examples/prometheus-io/prometheus-query-example/)
- [Prometheus Query Range Example](https://apis.io/examples/prometheus-io/prometheus-query-range-example/)
- [Prometheus Targets Example](https://apis.io/examples/prometheus-io/prometheus-targets-example/)

#### Collections (20)

Postman and Open Collection request collections.

- [Alertmanager API](https://apis.io/collections/prometheus-io/open-prometheus-alertmanager-api/)
- [Alertmanager admin API](https://apis.io/collections/prometheus-io/open-prometheus-io-admin-api/)
- [Alertmanager admin alert API](https://apis.io/collections/prometheus-io/open-prometheus-io-alert-api/)
- [Alertmanager admin alertgroup API](https://apis.io/collections/prometheus-io/open-prometheus-io-alertgroup-api/)
- [Alertmanager admin alerts API](https://apis.io/collections/prometheus-io/open-prometheus-io-alerts-api/)
- [Alertmanager admin features API](https://apis.io/collections/prometheus-io/open-prometheus-io-features-api/)
- [Alertmanager admin general API](https://apis.io/collections/prometheus-io/open-prometheus-io-general-api/)
- [Alertmanager admin labels API](https://apis.io/collections/prometheus-io/open-prometheus-io-labels-api/)
- [Alertmanager admin metadata API](https://apis.io/collections/prometheus-io/open-prometheus-io-metadata-api/)
- [Alertmanager admin notifications API](https://apis.io/collections/prometheus-io/open-prometheus-io-notifications-api/)
- [Alertmanager admin otlp API](https://apis.io/collections/prometheus-io/open-prometheus-io-otlp-api/)
- [Alertmanager admin query API](https://apis.io/collections/prometheus-io/open-prometheus-io-query-api/)
- [Alertmanager admin receiver API](https://apis.io/collections/prometheus-io/open-prometheus-io-receiver-api/)
- [Alertmanager admin remote API](https://apis.io/collections/prometheus-io/open-prometheus-io-remote-api/)
- [Alertmanager admin rules API](https://apis.io/collections/prometheus-io/open-prometheus-io-rules-api/)
- [Alertmanager admin series API](https://apis.io/collections/prometheus-io/open-prometheus-io-series-api/)
- [Alertmanager admin silence API](https://apis.io/collections/prometheus-io/open-prometheus-io-silence-api/)
- [Alertmanager admin status API](https://apis.io/collections/prometheus-io/open-prometheus-io-status-api/)
- [Alertmanager admin targets API](https://apis.io/collections/prometheus-io/open-prometheus-io-targets-api/)
- [Prometheus API](https://apis.io/collections/prometheus-io/open-prometheus-server-api/)

#### Governance rules (2)

Spectral rulesets for the provider's contracts.

- [Prometheus — jsonschema rules](https://apis.io/rules/prometheus-io/prometheus-io-jsonschema-spectral-rules/)
- [Prometheus API Rules](https://apis.io/rules/prometheus-io/prometheus-io-rules/)

#### Security (1)

Authentication, trust centre, and vulnerability disclosure.

- [Prometheus Io Domain Security](https://apis.io/security/prometheus-io/prometheus-io-domain-security/)

## Where to find this API

Links to the company's own pages. This repository publishes no copy of their specifications — the canonical document is theirs and lives at the URLs below.

- [Website](https://www.prometheus.io/)
- [Documentation](https://prometheus.io/docs/introduction/overview/)
- [Changelog](https://github.com/prometheus/prometheus/releases)
- [Blog](https://prometheus.io/blog/)
- [Security](https://github.com/prometheus/prometheus/security/policy)
- [Terms of service](https://github.com/cncf/foundation/blob/main/charter.md)

## API Evangelist rating

**Kin Score 35.4** — thin · rubric 0.24.0 · scored 2026-10-17

| Facet | Score |
|---|---|
| Discoverability | 57.1 |
| Contract quality | 56.3 |
| Contract governance | 13.6 |
| Operational transparency | 31.6 |
| Developer ergonomics | 42.9 |
| Access clarity | 10.5 |

**Agent readiness 19.8** — agent-aware

| Agent-readiness dimension | Result |
|---|---|
| Spec Presence | yes |
| Agentic Access | derived (partial credit) |
| Reversibility Documented | — |
| MCP Server | — |
| Auth Clarity | — |
| Idempotency | — |
| Error Semantics | — |
| OpenAPI Examples | verified |
| Rate Limit Signal | — |
| Event Surface Described | — |
| Agent Skills | — |
| Well Known Catalog | — |
| Consent Identity | — |
| Agent Card | — |
| Dry Run Mode | — |
| Delegated Identity | — |
| Protected Resource Metadata | — |
| Dynamic Client Registration | — |
| Agentic Commerce | — |

**Regulatory alignment 14.7** — Horizontal (data, software, accessibility, platform)

The rubric is published at [github.com/api-evangelist/kin-score](https://github.com/api-evangelist/kin-score). The per-check breakdown behind these numbers — which checks were earned, partial or missed — along with score history and how this provider compares to its peers, is available at [apis.io/providers/prometheus-io/](https://apis.io/providers/prometheus-io/).

## How this profile is made

API Evangelist profiles a company's public API surface the way a developer would find it: the website, developer portal and documentation, the specifications it publishes, its public repositories, and its pricing, status and changelog pages. From that it derives the properties above — contracts split per API, workflows, schemas, collections, governance rules, plans and rate limits — and scores them against the published [Kin Score rubric](https://github.com/api-evangelist/kin-score).

The artifacts are published on [APIs.io](https://apis.io), not in this repository. This repository is the public record for Prometheus: the place to say something is wrong, missing or out of date, and to ask for a re-score or a removal.

## Open an issue

- **Something about this listing** — a wrong description, a missing API, a stale artifact or a question about the rating: [open an issue on this repository](https://github.com/api-evangelist/prometheus-io/issues/new).
- **A new API, or one that is not in the catalog yet** — [submit it on APIs.io](https://apis.io/add/).
- **Anything else** — [the APIs.io inbox](https://github.com/api-search/inbox/issues/new) or [info@apievangelist.com](mailto:info@apievangelist.com).
