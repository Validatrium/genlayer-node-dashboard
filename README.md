# Genlayer Node Dashboard

Dashboard for monitoring Genlayer (Supra Network) nodes using InfluxDB and Prometheus.

## 📦 Datasources

- InfluxDB (UID: `${{datasource}}`)
- Prometheus (UID: `${{datasource}}`)

## 🔧 Variables

- `datasource`: selected automatically
- `host`: node exporter host
- `node`: validator or node address

## 📊 Panels

- Status (`genlayer_node_status`)
- Uptime (`genlayer_node_uptime_seconds`)
- Blocks Behind / Latest / Synced / Processing
- Transaction lifecycle: accepted, activated, proposed, revealed, committed
- CPU, memory, disk, network

## 🛠 Requirements

- Grafana 12+
- InfluxDB datasource configured and named in `datasource` variable
- Prometheus datasource for additional metrics

### Configuration

To ensure metrics are exposed for Prometheus, the node must have the following configuration in `config.yaml`:

```yaml
ops:
  port: 9153
  endpoints:
    metrics: true
    health: true

metrics:
  interval: "15s"
  collectors:
    node:
      enabled: true
      interval: "30s"
    genvm:
      enabled: true
      interval: "20s"
    webdriver:
      enabled: true
      interval: "60s"
```

This enables Prometheus to scrape metrics at `http://<node_ip>:9153/metrics` and is required for dashboard to function properly.

## 🚀 Import manually

1. Go to Grafana → Dashboards → Import.
2. Paste contents of `dashboard.json`.
3. Set `datasource` variable to your datasource UID.

## ⚙️ Provisioning (optional)

To load automatically via provisioning:

```yaml
provisioning/dashboards.yaml
```

## 🪪 License

MIT License
