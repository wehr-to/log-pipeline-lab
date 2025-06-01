# 🧱 log-pipeline-lab

This repository contains labs, configs, and architecture breakdowns for building, securing, and troubleshooting full log pipelines — from endpoint to SIEM or archive.

## 🎯 Why This Exists

In most real-world environments, logging is either:
- Overwhelming (too much noise)
- Incomplete (key sources missing)
- Insecure (logs tampered or lost in transit)

This repo exists to build **secure, enriched, and resilient log flows** — the kind security engineers, SREs, and forensic analysts rely on.

## 📦 Pipeline Stages Covered

| Stage | Examples |
|-------|----------|
| `01-sources/` | auditd, Windows logs, nginx, osquery, CloudTrail |
| `02-forwarders/` | Filebeat, Fluentd, native syslog, osquery |
| `03-aggregation/` | Logstash, Kafka, Syslog-ng |
| `04-storage-and-indexing/` | Elasticsearch, OpenSearch, S3 |
| `05-enrichment-and-parsing/` | Grok, GeoIP, tagging, field mapping |
| `06-visualization/` | Kibana dashboards, Grafana for metrics |
| `07-resilience-and-security/` | Buffering, integrity checks, TLS log forwarding |

## 🧪 Hands-On Labs

- `local-log-pipeline.md` – from `auditd` → `filebeat` → `logstash` → `ES`
- `cloudtrail-to-siem.md` – pull from S3 to index in OpenSearch
- `log-breakage-drill.md` – test buffer behavior, retry, and loss prevention

## 🛠 Tools Simulated

- `auditd`, `rsyslog`, `filebeat`, `fluentd`
- `logstash`, `kafka`, `syslog-ng`
- `elasticsearch`, `opensearch`, `kibana`, `grafana`
- TLS config, log tamper protection, multiline log handling

## 📈 Real-World Use Cases

| Goal | Folder |
|------|--------|
| Detect SSH brute force on Linux | `01-sources/linux-auditd` + `03-aggregation/logstash` |
| Index nginx logs with geo tags | `01-sources/nginx-logs` + `05-enrichment-and-parsing/` |
| Centralize Windows logs via GPO | `01-sources/windows-event-forwarding/` |
| Stream logs to S3 for cheap retention | `04-storage-and-indexing/s3-archival.md` |

## 🧠 Ideal For

- SOC engineers tuning log pipelines
- SREs prepping systems for observability
- Blue teamers building resilient detection infrastructure
- Anyone prepping for CySA+, Blue Team Level 2, or logging-intensive interviews


