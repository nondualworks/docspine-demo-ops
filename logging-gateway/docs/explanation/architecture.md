# Log Architecture

## Pipeline

```
Application → Fluent Bit (sidecar) → Kafka → Logging Gateway → Elasticsearch
                                                           → S3 (archive)
```

## Why Kafka in the Middle?

Kafka decouples ingestion rate from indexing rate. During traffic spikes, logs queue in Kafka rather than overwhelming Elasticsearch. The logging gateway consumes at a sustainable rate.

## Structured Logging Contract

All services must emit logs as JSON with these required fields:

```json
{
  "timestamp": "2026-02-24T10:15:30Z",
  "level": "info",
  "service": "checkout-api",
  "message": "Checkout session created",
  "trace_id": "abc123"
}
```

Additional fields are indexed automatically.
