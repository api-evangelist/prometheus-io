# Prometheus GraphQL Schema

This directory contains a conceptual GraphQL schema that maps the Prometheus HTTP API to GraphQL types and queries. Prometheus itself exposes a REST/PromQL HTTP API — this schema is a structural representation for tooling, documentation, and integration work, not a deployed GraphQL endpoint.

## Source API

- HTTP API Reference: https://prometheus.io/docs/prometheus/latest/querying/api/
- GitHub: https://github.com/prometheus/prometheus

## Schema File

- `prometheus-io-schema.graphql` — GraphQL SDL with 60+ named types covering the full Prometheus data model.

## Type Inventory

### Core Metric Primitives

| Type | Kind | Description |
|------|------|-------------|
| `Metric` | Object | Named metric with labels, type, help, and unit |
| `MetricName` | Scalar | String identifier mapping to the `__name__` label |
| `LabelPair` | Object | A key/value label pair attached to a metric or sample |
| `LabelSet` | Object | Unordered set of label pairs uniquely identifying a time series |
| `MetricValue` | Scalar | Floating-point measurement value |
| `MetricType` | Enum | COUNTER, GAUGE, HISTOGRAM, SUMMARY, UNTYPED |

### Metric Type Objects

| Type | Kind | Description |
|------|------|-------------|
| `Counter` | Object | Monotonically increasing metric with value and timestamp |
| `Gauge` | Object | Metric that can go up and down |
| `Histogram` | Object | Sampled distribution with configurable buckets |
| `HistogramBucket` | Object | Single bucket boundary and cumulative count |
| `Summary` | Object | Streaming quantile summary over a sliding time window |
| `Quantile` | Object | Quantile/value pair from a summary metric |

### Timestamps and Samples

| Type | Kind | Description |
|------|------|-------------|
| `Timestamp` | Scalar | Unix timestamp with millisecond precision |
| `Sample` | Object | Single timestamp + float value data point |
| `SamplePair` | Object | (timestamp, value) pair used in range query results |

### Vectors and Matrices

| Type | Kind | Description |
|------|------|-------------|
| `InstantVector` | Object | Instant query result — one sample per matching time series |
| `RangeVector` | Object | Range query result — multiple samples per matching time series |
| `Vector` | Object | Alias for InstantVector in API responses |
| `Matrix` | Object | Matrix result from a range query |
| `Series` | Object | Identified time series with optional samples |
| `SeriesRange` | Object | Time range over which series data is queried |

### Query Results

| Type | Kind | Description |
|------|------|-------------|
| `Result` | Object | Top-level /api/v1 response wrapper |
| `ResultStatus` | Enum | SUCCESS or ERROR |
| `QueryResult` | Object | Data payload of a /query response |
| `ResultType` | Enum | MATRIX, VECTOR, SCALAR, STRING |
| `VectorOrMatrix` | Object | Union-like type covering both instant and range vector items |
| `QueryRange` | Object | Data payload for a /query_range response |
| `MetadataResult` | Object | Result wrapper for /api/v1/metadata |

### Targets

| Type | Kind | Description |
|------|------|-------------|
| `TargetResult` | Object | Wrapper returned by /api/v1/targets |
| `Target` | Object | Active scrape target tracked by Prometheus |
| `TargetDetails` | Object | Extended target view with additional metadata |
| `TargetHealth` | Enum | UP, DOWN, or UNKNOWN |
| `DroppedTarget` | Object | Target dropped during relabeling |
| `ScrapePool` | Object | Named group of targets sharing a scrape config |

### Alerts and Rules

| Type | Kind | Description |
|------|------|-------------|
| `Alert` | Object | Active alert firing in Prometheus |
| `AlertDetails` | Object | Alert with name and rule context |
| `AlertState` | Enum | INACTIVE, PENDING, or FIRING |
| `AlertName` | Scalar | String name of an alert rule |
| `AlertRule` | Object | Named alert rule with query, duration, and labels |
| `AlertingRule` | Object | Alerting rule with full alert state list |
| `RecordingRule` | Object | Named recording rule that pre-computes expressions |
| `Rule` | Object | Union-like type for alerting or recording rule |
| `RuleType` | Enum | ALERTING or RECORDING |
| `RuleGroup` | Object | Named group of rules evaluated together |

### Configuration and Scraping

| Type | Kind | Description |
|------|------|-------------|
| `Config` | Object | Full Prometheus configuration YAML |
| `Scrape` | Object | Result of a single scrape operation |
| `ScrapeConfig` | Object | Scrape configuration block for a job |

### Storage and TSDB

| Type | Kind | Description |
|------|------|-------------|
| `StorageInfo` | Object | High-level storage information |
| `TSDB` | Object | Embedded time-series database statistics |
| `TSDBHeadStats` | Object | In-memory HEAD block statistics |
| `MetricCount` | Object | Metric name with series count |
| `LabelCount` | Object | Label name with distinct value count |
| `LabelMemory` | Object | Label name with memory usage in bytes |
| `LabelValueCount` | Object | Label name=value pair with series count |

### Build / Runtime / Flags

| Type | Kind | Description |
|------|------|-------------|
| `FlagsResult` | Object | Command-line flags as returned by /api/v1/status/flags |
| `BuildInfo` | Object | Version, revision, build metadata |
| `RuntimeInfo` | Object | Start time, goroutines, GC settings, storage retention |

### Service Discovery

| Type | Kind | Description |
|------|------|-------------|
| `DiscoveryTarget` | Object | A discovered target from service discovery |
| `ServiceDiscovery` | Object | A configured service discovery block |

### Relabeling

| Type | Kind | Description |
|------|------|-------------|
| `RelabelConfig` | Object | A relabel configuration step |
| `RelabelAction` | Enum | REPLACE, KEEP, DROP, LABELMAP, LABELDROP, LABELKEEP, LOWERCASE, UPPERCASE, HASHMOD, KEEPEQUAL, DROPEQUAL |

### Remote Read / Write

| Type | Kind | Description |
|------|------|-------------|
| `RemoteRead` | Object | Configuration for a remote read endpoint |
| `RemoteWrite` | Object | Configuration for a remote write endpoint |
| `WriteRequest` | Object | Protobuf-encoded batch of time series for Remote Write |
| `ReadRequest` | Object | Batch of time series requested via Remote Read |
| `TimeSeries` | Object | Fully-labelled time series with samples for remote protocols |
| `QueryHints` | Object | Query hints passed in a remote read request |

### WAL

| Type | Kind | Description |
|------|------|-------------|
| `WAL` | Object | Write-Ahead Log replay status |

### Exemplars

| Type | Kind | Description |
|------|------|-------------|
| `Exemplar` | Object | OpenMetrics exemplar attached to a histogram or counter |
| `ExemplarLabels` | Object | Key-value labels carried by an exemplar (e.g., trace_id) |

### Feature Flags

| Type | Kind | Description |
|------|------|-------------|
| `FeatureFlags` | Object | A Prometheus feature flag and its enabled state |

## Root Query Operations

| Operation | Description |
|-----------|-------------|
| `query` | Evaluate an instant PromQL query at a single point in time |
| `queryRange` | Evaluate a PromQL expression over a time range |
| `series` | Find series matching a set of label matchers |
| `labels` | Return all label names matching optional matchers |
| `labelValues` | Return all label values for a given label name |
| `targets` | Return currently active and dropped scrape targets |
| `rules` | Return all rule groups (alerting and recording rules) |
| `alerts` | Return all currently firing alerts |
| `config` | Return current Prometheus server configuration |
| `flags` | Return current command-line flags |
| `buildInfo` | Return build information |
| `runtimeInfo` | Return runtime information |
| `tsdb` | Return TSDB head statistics |
| `walReplayStatus` | Return WAL replay status |
| `metadata` | Return metric metadata |
| `queryExemplars` | Return exemplars for a given PromQL query range |

## References

- Prometheus HTTP API: https://prometheus.io/docs/prometheus/latest/querying/api/
- PromQL Basics: https://prometheus.io/docs/prometheus/latest/querying/basics/
- PromQL Operators: https://prometheus.io/docs/prometheus/latest/querying/operators/
- PromQL Functions: https://prometheus.io/docs/prometheus/latest/querying/functions/
- Data Model: https://prometheus.io/docs/concepts/data_model/
- Metric Types: https://prometheus.io/docs/concepts/metric_types/
- Remote Write Spec: https://prometheus.io/docs/specs/prw/remote_write_spec_2_0/
- OpenMetrics: https://openmetrics.io/
