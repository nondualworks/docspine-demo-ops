# Metrics Collector Reference

## Prometheus-Compatible Endpoints

### `GET /metrics`
Standard Prometheus scrape endpoint. Returns all registered metrics in Prometheus exposition format.

### `POST /api/v1/metrics`
Push custom metrics for services that can't be scraped (batch jobs, lambdas).

## Custom Metric Types

| Type | Use Case | Example |
|------|----------|---------|
| `counter` | Monotonically increasing values | `http_requests_total` |
| `gauge` | Values that go up and down | `active_connections` |
| `histogram` | Distribution of values | `request_duration_seconds` |
| `summary` | Pre-calculated quantiles | `gc_pause_duration` |

## Labels

Standard labels applied to all metrics:

- `service` — source service name
- `env` — environment (production, staging)
- `region` — AWS region
- `instance` — pod/instance identifier
