# Query Logs

Search and filter logs using structured queries.

## Basic Query

```
service:checkout-api AND level:error AND timestamp:[now-1h TO now]
```

## Field Filters

| Field | Example | Description |
|-------|---------|-------------|
| `service` | `service:auth-gateway` | Filter by service name |
| `level` | `level:error` | Log level (debug, info, warn, error) |
| `trace_id` | `trace_id:abc123` | Follow a distributed trace |
| `user_id` | `user_id:usr_456` | All logs for a specific user |

## Time Ranges

- `now-15m` — last 15 minutes
- `now-1h` — last hour
- `now-7d` — last 7 days
- `2026-02-24T00:00:00Z TO 2026-02-24T12:00:00Z` — specific range
