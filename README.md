# Prometheus (prometheus-io)

Prometheus is a Cloud Native Computing Foundation (CNCF) graduated open source systems monitoring and alerting toolkit. A Prometheus server scrapes metrics over HTTP from instrumented targets, stores them in an embedded time series database (TSDB), and lets operators query, alert, and aggregate them with the PromQL query language. The project pairs the Prometheus server with Alertmanager for alert routing and silencing, official client libraries for Go, Java, Python, Ruby, and Rust, and a large ecosystem of exporters (`node_exporter`, `blackbox_exporter`, `snmp_exporter`, `statsd_exporter`, `jmx_exporter`, `mysqld_exporter`, `cloudwatch_exporter`, `consul_exporter`, `graphite_exporter`, `memcached_exporter`, `pushgateway`, and many more) for extracting metrics from existing systems. Prometheus also drives the OpenMetrics exposition format and an experimental Remote Write 2.0 protocol for shipping samples to long-term storage backends.

**URL:** [Visit APIs.json](https://raw.githubusercontent.com/api-evangelist/prometheus-io/refs/heads/main/apis.yml)

**Run:** [Capabilities Using Naftiko](https://github.com/naftiko/fleet?utm_source=api-evangelist&utm_medium=readme&utm_campaign=opensource-api-evangelist&utm_content=prometheus-io)

## Tags

- Monitoring, Metrics, Observability, Time Series, Alerting, Cloud Native, CNCF, Open Source, PromQL, Telemetry

## Project Facts

| Item | Value |
|---|---|
| License | Apache 2.0 |
| Governance | CNCF (Graduated) |
| Primary language | Go |
| Source | [github.com/prometheus/prometheus](https://github.com/prometheus/prometheus) |
| Releases | [GitHub releases](https://github.com/prometheus/prometheus/releases) |
| Container image | [prom/prometheus on Docker Hub](https://hub.docker.com/r/prom/prometheus) |
| Binaries shipped | `prometheus`, `promtool` |
| Pricing model | Free, open source. Hosted offerings exist via third parties (Grafana Cloud, Amazon Managed Prometheus, Google Managed Service for Prometheus, Chronosphere, Levitate, etc.) but are out of scope for this profile. |

## APIs

### Prometheus Server HTTP API
The HTTP API exposed by every Prometheus server under `/api/v1`. Lets clients evaluate instant and range PromQL queries, list and search series, labels, and metric metadata, inspect targets, scrape pools, rules, active alerts, alertmanagers, status, TSDB stats, WAL replay, build/runtime info, server-side notifications, and the live feature set. Includes admin endpoints behind `--web.enable-admin-api` for snapshots, series deletion, and tombstone clean-up, plus optional remote read/write and OTLP metrics receivers.

**Human URL:** [https://prometheus.io/docs/prometheus/latest/querying/api/](https://prometheus.io/docs/prometheus/latest/querying/api/)

- [Documentation — HTTP API](https://prometheus.io/docs/prometheus/latest/querying/api/)
- [Documentation — PromQL Basics](https://prometheus.io/docs/prometheus/latest/querying/basics/)
- [Documentation — PromQL Operators](https://prometheus.io/docs/prometheus/latest/querying/operators/)
- [Documentation — PromQL Functions](https://prometheus.io/docs/prometheus/latest/querying/functions/)
- [OpenAPI](openapi/prometheus-server-api-openapi.yml) — sourced from `web/api/v1/testdata/openapi_3.1_golden.yaml` in the prometheus/prometheus repo
- [JSON Schema — Query Result](json-schema/prometheus-query-result-schema.json)
- [JSON Schema — Target](json-schema/prometheus-target-schema.json)
- [JSON-LD context](json-ld/prometheus-io-context.jsonld)
- [Example — Instant Query (`/api/v1/query`)](examples/prometheus-query-example.json)
- [Example — Range Query (`/api/v1/query_range`)](examples/prometheus-query-range-example.json)
- [Example — Targets (`/api/v1/targets`)](examples/prometheus-targets-example.json)
- [Naftiko Capability — Query](capabilities/prometheus-query.yaml)
- [Naftiko Capability — Metadata](capabilities/prometheus-metadata.yaml)
- [Naftiko Capability — Targets](capabilities/prometheus-targets.yaml)
- [Naftiko Capability — Rules and Alerts](capabilities/prometheus-rules-alerts.yaml)
- [Naftiko Capability — Status](capabilities/prometheus-status.yaml)
- [Naftiko Capability — Admin TSDB](capabilities/prometheus-admin-tsdb.yaml)

### Prometheus Alertmanager API v2
Alertmanager's HTTP API v2 — the canonical interface for posting alerts, listing and grouping firing alerts, managing silences, listing configured receivers, and inspecting cluster status. Generated from `api/v2/openapi.yaml` in the prometheus/alertmanager repository and consumed by the Alertmanager UI and external integrations.

**Human URL:** [https://github.com/prometheus/alertmanager](https://github.com/prometheus/alertmanager)

- [OpenAPI](openapi/prometheus-alertmanager-api-openapi.yml) — Swagger 2.0, sourced from prometheus/alertmanager `api/v2/openapi.yaml`
- [Documentation — Alertmanager Overview](https://prometheus.io/docs/alerting/latest/alertmanager/)
- [Naftiko Capability — Alertmanager](capabilities/prometheus-alertmanager.yaml)

### Prometheus Remote Write
Push protocol for shipping scraped samples to long-term storage and analysis backends (Cortex, Thanos, Mimir, VictoriaMetrics, InfluxDB, Datadog, etc.). Snappy-compressed protocol-buffer payloads over HTTP. Version 1.0 is stable; version 2.0 (experimental specification) adds native histograms, metadata-per-series, created timestamps, and tighter validation.

- [Remote Write 1.0 Specification](https://prometheus.io/docs/specs/prw/remote_write_spec/)
- [Remote Write 2.0 Specification](https://prometheus.io/docs/specs/prw/remote_write_spec_2_0/)
- [Protocol Buffers — `remote.proto`](https://github.com/prometheus/prometheus/blob/main/prompb/remote.proto)

### Prometheus Exposition Format / OpenMetrics
The text-based exposition format every instrumented target exposes (typically on `/metrics`) and that the Prometheus server scrapes. The format evolved into OpenMetrics, a CNCF specification that is the standardized successor. Both are scrape-compatible with Prometheus.

- [Exposition Format Documentation](https://prometheus.io/docs/instrumenting/exposition_formats/)
- [OpenMetrics](https://openmetrics.io/)
- [prometheus/OpenMetrics on GitHub](https://github.com/prometheus/OpenMetrics)

### Prometheus OTLP Metrics Receiver
Optional OpenTelemetry Protocol metrics receiver exposed on `/api/v1/otlp/v1/metrics` when the Prometheus server is started with `--web.enable-otlp-receiver`. Accepts OTLP/HTTP protobuf payloads from OpenTelemetry Collectors and SDKs; delta-to-cumulative conversion is available behind `--enable-feature=otlp-deltatocumulative`.

- [OpenTelemetry Guide](https://prometheus.io/docs/guides/opentelemetry/)
- [OTLP Protocol Buffers](https://github.com/open-telemetry/opentelemetry-proto)

## Ecosystem

### Client Libraries (Official)
[Go](https://github.com/prometheus/client_golang) · [Java/JVM](https://github.com/prometheus/client_java) · [Python](https://github.com/prometheus/client_python) · [Ruby](https://github.com/prometheus/client_ruby) · [Rust](https://github.com/prometheus/client_rust)

### Client Libraries (Community)
[Node.js (prom-client)](https://github.com/siimon/prom-client) · [C++](https://github.com/jupp0r/prometheus-cpp) · [Elixir](https://github.com/deadtrickster/prometheus.ex) · [Erlang](https://github.com/deadtrickster/prometheus.erl) · [Haskell](https://github.com/fimad/prometheus-haskell) · [PHP](https://github.com/promphp/prometheus_client_php) · [Swift](https://github.com/swift-server/swift-prometheus) · [Dart](https://github.com/tentaclelabs/prometheus_client) · [Julia](https://github.com/fredrikekre/Prometheus.jl) · [Lua/Nginx](https://github.com/knyar/nginx-lua-prometheus) · plus the unofficial list at [prometheus.io/docs/instrumenting/clientlibs](https://prometheus.io/docs/instrumenting/clientlibs/).

### Exporters & Tools
[node_exporter](https://github.com/prometheus/node_exporter) · [blackbox_exporter](https://github.com/prometheus/blackbox_exporter) · [snmp_exporter](https://github.com/prometheus/snmp_exporter) · [statsd_exporter](https://github.com/prometheus/statsd_exporter) · [jmx_exporter](https://github.com/prometheus/jmx_exporter) · [mysqld_exporter](https://github.com/prometheus/mysqld_exporter) · [cloudwatch_exporter](https://github.com/prometheus/cloudwatch_exporter) · [consul_exporter](https://github.com/prometheus/consul_exporter) · [graphite_exporter](https://github.com/prometheus/graphite_exporter) · [memcached_exporter](https://github.com/prometheus/memcached_exporter) · [influxdb_exporter](https://github.com/prometheus/influxdb_exporter) · [collectd_exporter](https://github.com/prometheus/collectd_exporter) · [pushgateway](https://github.com/prometheus/pushgateway) · [promlens](https://github.com/prometheus/promlens) · [prom2json](https://github.com/prometheus/prom2json) · [exporter-toolkit](https://github.com/prometheus/exporter-toolkit) · [promu](https://github.com/prometheus/promu).

## Governance & Community

- [CNCF Project Page](https://www.cncf.io/projects/prometheus/) (Graduated)
- [prometheus/governance](https://github.com/prometheus/governance)
- [Design Proposals](https://github.com/prometheus/proposals)
- [Community Page](https://prometheus.io/community/)
- [Security Policy](https://github.com/prometheus/prometheus/security/policy)
- [Changelog](https://github.com/prometheus/prometheus/blob/main/CHANGELOG.md)

## Notes on Profile Scope

Prometheus is pure open source software — the profile captures the **API contract of a Prometheus server you deploy**, not a hosted commercial offering. Hosted Prometheus-compatible services (Grafana Cloud, Amazon Managed Service for Prometheus, Google Managed Service for Prometheus, Chronosphere, Levitate, Logz.io, Last9, etc.) re-implement subsets of this same `/api/v1` and Remote Write surface; that's why this profile is the right starting point for governing any of them. Plans, rate limits, and FinOps artifacts are intentionally omitted (no first-party commercial surface).

## Timestamps

- **Created:** 2026-05-25
- **Modified:** 2026-05-25
