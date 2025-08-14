# Genlayer Node Dashboard

Dashboard for monitoring Genlayer nodes with metrics from **Prometheus**.

## 📦 Datasources

- Prometheus (UID: `${datasource}`)

## 🔧 Variables

- `datasource`: selected automatically
- `host`: node exporter host
- `node`: node address

## 📊 Panels

- Status (`genlayer_node_status`)
- Uptime (`genlayer_node_uptime_seconds`)
- Blocks Behind / Latest / Synced / Processing
- Transaction lifecycle: accepted, activated, proposed, revealed, committed
- CPU, memory, disk, network

## 🛠 Requirements

- Grafana 12+
- Prometheus datasource for additional metrics

## 🚀 Import manually

1. Go to Grafana → Dashboards → Import.
2. Paste contents of `dashboard.json`.
3. Set `datasource` variable to your datasource UID.

## ⚙️ Provisioning (optional)

To load automatically via provisioning:

```yaml
provisioning/dashboards.yaml
