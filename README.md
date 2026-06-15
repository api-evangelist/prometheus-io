# Prometheus (prometheus-io)

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
