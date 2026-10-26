# Prometheus (prometheus-io)

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

**APIs.json:** [https://raw.githubusercontent.com/api-evangelist/prometheus-io/refs/heads/main/apis.yml](https://raw.githubusercontent.com/api-evangelist/prometheus-io/refs/heads/main/apis.yml)

## Scope

- **Access:** Self-Hosted

## Tags

- Monitoring
- Metrics
- Observability
- Time Series
- Alerting
- Cloud Native
- CNCF
- Open Source
- PromQL
- Telemetry

## Timestamps

- **Created:** Sun May 24 2026 20:00:00 GMT-0400 (Eastern Daylight Time)
- **Modified:** Sun May 24 2026 20:00:00 GMT-0400 (Eastern Daylight Time)

## APIs

### Prometheus Server HTTP API

The HTTP API exposed by every Prometheus server under /api/v1. Lets clients evaluate instant and range PromQL queries, list and search series, labels and metric metadata, inspect targets, scrape pools, rules, active alerts, alertmanagers, status, TSDB stats, WAL replay, build/runtime info, server-side notifications, and the live feature set. Also includes admin endpoints behind --web.enable-admin-api for snapshots, series deletion, and tombstone clean-up, plus optional remote read/write and OTLP metrics receivers. Stable v1 with non-breaking additions; experimental endpoints (parse_query, query_exemplars, targets/relabel_steps, status/tsdb/blocks, notifications) are clearly marked.

- **Human URL:** [https://prometheus.io/docs/prometheus/latest/querying/api/](https://prometheus.io/docs/prometheus/latest/querying/api/)
- **Base URL:** `http://localhost:9090/api/v1`

#### Tags

- Metrics
- PromQL
- Query
- Monitoring

#### Properties

- [Documentation](https://prometheus.io/docs/prometheus/latest/querying/api/)
- [Documentation](https://prometheus.io/docs/prometheus/latest/querying/basics/)
- [Documentation](https://prometheus.io/docs/prometheus/latest/querying/operators/)
- [Documentation](https://prometheus.io/docs/prometheus/latest/querying/functions/)
- [OpenAPI](openapi/prometheus-server-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/prometheus-server-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/prometheus-server-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [JSON Schema](json-schema/prometheus-query-result-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON Schema](json-schema/prometheus-target-schema.json) — [JSON Schema](https://json-schema.org/specification)
- [JSON-LD](json-ld/prometheus-io-context.jsonld) — [JSON-LD](https://www.w3.org/TR/json-ld11/)
- [Example](examples/prometheus-query-example.json)
- [Example](examples/prometheus-query-range-example.json)
- [Example](examples/prometheus-targets-example.json)

### Prometheus Alertmanager API v2

Alertmanager's HTTP API v2 — the canonical interface for posting alerts, listing and grouping firing/inhibited/silenced alerts, managing silences, listing configured receivers, and inspecting cluster status. Spec is generated with go-swagger from api/v2/openapi.yaml in the alertmanager repo and consumed by the Alertmanager UI and external integrations.

- **Human URL:** [https://github.com/prometheus/alertmanager](https://github.com/prometheus/alertmanager)
- **Base URL:** `http://localhost:9093/api/v2`

#### Tags

- Alerts
- Silences
- Notifications
- Receivers
- Cluster

#### Properties

- [Documentation](https://github.com/prometheus/alertmanager/blob/main/api/v2/openapi.yaml)
- [Documentation](https://prometheus.io/docs/alerting/latest/alertmanager/)
- [OpenAPI](openapi/prometheus-alertmanager-api-openapi.yml) — [OpenAPI Specification](https://spec.openapis.org/oas/latest.html)
- [Postman Collection](collections/prometheus-alertmanager-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/prometheus-alertmanager-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Prometheus Remote Write

Remote Write is Prometheus' push protocol for shipping scraped samples to long-term storage and analysis backends (Cortex, Thanos, Mimir, VictoriaMetrics, InfluxDB, Datadog, etc.). Snappy-compressed protocol-buffer payloads POSTed over HTTP. Version 1.0 is stable and widely implemented; version 2.0 (experimental specification) adds native histograms, metadata-per-series, created timestamps, and tighter validation.

- **Human URL:** [https://prometheus.io/docs/specs/prw/remote_write_spec_2_0/](https://prometheus.io/docs/specs/prw/remote_write_spec_2_0/)

#### Tags

- Remote Write
- Ingest
- Protocol Buffers
- Streaming

#### Properties

- [Documentation](https://prometheus.io/docs/specs/prw/remote_write_spec/)
- [Documentation](https://prometheus.io/docs/specs/prw/remote_write_spec_2_0/)
- [Proto Buf](https://github.com/prometheus/prometheus/blob/main/prompb/remote.proto)
- [Postman Collection](collections/prometheus-alertmanager-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/prometheus-alertmanager-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/prometheus-server-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/prometheus-server-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Prometheus Exposition Format / OpenMetrics

The text-based exposition format that every instrumented target exposes (typically on /metrics) and that the Prometheus server scrapes over HTTP. The format evolved into OpenMetrics, a CNCF Sandbox specification that is the standardized successor; both are scrape-compatible with Prometheus. Defines counters, gauges, histograms, summaries, and (in OpenMetrics) info, stateset, gaugehistogram, and exemplars.

- **Human URL:** [https://prometheus.io/docs/instrumenting/exposition_formats/](https://prometheus.io/docs/instrumenting/exposition_formats/)

#### Tags

- Exposition
- OpenMetrics
- Scraping
- Metrics Format

#### Properties

- [Documentation](https://prometheus.io/docs/instrumenting/exposition_formats/)
- [Documentation](https://openmetrics.io/)
- [Source Code](https://github.com/prometheus/OpenMetrics)
- [Postman Collection](collections/prometheus-alertmanager-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/prometheus-alertmanager-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/prometheus-server-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/prometheus-server-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

### Prometheus OTLP Metrics Receiver

Optional OpenTelemetry Protocol metrics receiver exposed on /api/v1/otlp/v1/metrics when the Prometheus server is started with --web.enable-otlp-receiver. Accepts OTLP/HTTP protobuf payloads from OpenTelemetry Collectors and SDKs; delta-to-cumulative conversion is available behind --enable-feature=otlp-deltatocumulative.

- **Human URL:** [https://prometheus.io/docs/prometheus/latest/feature_flags/](https://prometheus.io/docs/prometheus/latest/feature_flags/)

#### Tags

- OTLP
- OpenTelemetry
- Receiver
- Ingest

#### Properties

- [Documentation](https://prometheus.io/docs/guides/opentelemetry/)
- [Source Code](https://github.com/open-telemetry/opentelemetry-proto)
- [Postman Collection](collections/prometheus-alertmanager-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/prometheus-alertmanager-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)
- [Postman Collection](collections/prometheus-server-api.postman_collection.json) — [Postman Collection 2.1](https://schema.getpostman.com/json/collection/v2.1.0/collection.json)
- [Open Collection](collections/prometheus-server-api.opencollection.json) — [Open Collection 1.0](https://schema.opencollection.com/opencollection/v1.0.0.json)

## Common Properties

- [Portal](https://prometheus.io/)
- [Documentation](https://prometheus.io/docs/introduction/overview/)
- [Documentation](https://prometheus.io/docs/prometheus/latest/querying/api/)
- [Source Code](https://github.com/prometheus)
- [Source Code](https://github.com/prometheus/prometheus)
- [Changelog](https://github.com/prometheus/prometheus/releases)
- [Download](https://prometheus.io/download/)
- [Forum](https://prometheus.io/community/)
- [Documentation](https://prometheus.io/docs/introduction/glossary/)
- [Blog](https://prometheus.io/blog/)
- [Terms of Service](https://github.com/cncf/foundation/blob/main/charter.md)
- [Documentation](https://www.cncf.io/projects/prometheus/)
- [Terms of Service](https://github.com/prometheus/governance)
- [License](https://github.com/prometheus/prometheus/blob/main/LICENSE)
- [Security](https://github.com/prometheus/prometheus/security/policy)
- [Changelog](https://github.com/prometheus/prometheus/blob/main/CHANGELOG.md)
- [SDK](https://github.com/prometheus/client_golang)
- [SDK](https://github.com/prometheus/client_python)
- [SDK](https://github.com/prometheus/client_java)
- [SDK](https://github.com/prometheus/client_ruby)
- [SDK](https://github.com/prometheus/client_rust)
- [SDK](https://github.com/siimon/prom-client)
- [SDK](https://github.com/jupp0r/prometheus-cpp)
- [Tools](https://github.com/prometheus/alertmanager)
- [Tools](https://github.com/prometheus/node_exporter)
- [Tools](https://github.com/prometheus/blackbox_exporter)
- [Tools](https://github.com/prometheus/snmp_exporter)
- [Tools](https://github.com/prometheus/statsd_exporter)
- [Tools](https://github.com/prometheus/jmx_exporter)
- [Tools](https://github.com/prometheus/mysqld_exporter)
- [Tools](https://github.com/prometheus/cloudwatch_exporter)
- [Tools](https://github.com/prometheus/pushgateway)
- [Tools](https://github.com/prometheus/promlens)
- [Tools](https://github.com/prometheus/prom2json)
- [Documentation](https://github.com/prometheus/OpenMetrics)
- [Documentation](https://github.com/prometheus/proposals)
- [Documentation](https://prometheus.io/docs/prometheus/latest/installation/)
- [Container Image](https://hub.docker.com/r/prom/prometheus)
- [LinkedIn](https://www.linkedin.com/company/cloud-native-computing-foundation/)
- [Twitter](https://twitter.com/PrometheusIO)

## Maintainers

**FN:** Kin Lane
**Email:** info@apievangelist.com
