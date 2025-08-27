# mini-project-6-grafana-and-prometheus
# 🚀 Monitoring Stack with Node Exporter, Prometheus, Grafana & Alertmanager

This project sets up a **complete monitoring and alerting stack** using Docker and Docker Compose. It deploys **Node Exporter, Prometheus, Grafana, and Alertmanager** to monitor system resources and send alerts when thresholds are breached.

---

## 📌 What this project does
- Deploys **Node Exporter** on Docker through a `Dockerfile` and `docker-compose.yml`.
- Deploys **Prometheus** as a container using its official Docker image.
- Deploys **Grafana** as a container using its official Docker image.
- **Node Exporter** collects metrics like CPU usage, RAM usage, disk space, network activity, etc., and sends them to **Prometheus**.
- **Prometheus** stores and manages these metrics, then passes them to **Grafana** for visualization.
- **Grafana** provides beautiful and user-friendly dashboards for monitoring.
- If **CPU usage exceeds 60%**, Prometheus triggers an alert, and **Alertmanager** sends an email notification.

---


## 🔄 Project Flow

EC2 Instance
|
└── Metrics collected by Node Exporter
|
└── Sent to Prometheus (in HTML format)
|
└── Stored & processed by Prometheus
|
└── Forwarded to Grafana
|
└── Visualized in human-readable dashboards
|
└── Alerts triggered if CPU > 60%
|
└── Alertmanager notifies user via Email


---

## ⚙️ Important Setup Notes

1. **Grafana Datasource Setup**
   ```bash
   mkdir -p Grafana/provisioning/datasources
   vim Grafana/provisioning/datasources/datasource.yml
Paste the contents of datasource.yml from the Prometheus folder.

EC2 Security Group Inbound Rules

22 → from My IP (SSH)

9090 → from My IP (Prometheus)

3000 → from My IP (Grafana)

9093 → from My IP (Alertmanager)

9115 → from My IP (Node Exporter)

9100 → from EC2’s IP (Node Exporter)

8080 → from EC2’s IP

9115 → from EC2’s IP

Scaling to Multiple Instances

If you want to gather metrics from 2 or more EC2 instances, check out this repo:
👉 Automated Monitoring Alert Stack:


📊 Tech Stack

Docker & Docker Compose

Node Exporter

Prometheus

Grafana

Alertmanager

AWS EC2


✅ Outcomes

Real-time metrics collection (CPU, RAM, Disk, Network).

Interactive Grafana dashboards.

Email alerts when CPU usage exceeds 60%.

Easily extendable to multiple instances.



