# Logging Gateway API

## Ingestion

### `POST /api/v1/logs`
Ingest structured log entries. Accepts JSON or NDJSON.

### `POST /api/v1/logs/bulk`
Batch ingestion for high-throughput services.

## Query

### `POST /api/v1/logs/search`
Execute a structured query against the log index.

### `GET /api/v1/logs/tail`
Server-sent events stream of real-time logs matching a filter.

## Retention

| Tier | Duration | Storage |
|------|----------|---------|
| Hot | 7 days | Elasticsearch |
| Warm | 30 days | S3 + Athena |
| Cold | 1 year | S3 Glacier |
