# NO-SIR1 — Monitoring and operations

Status: proposed operating model; no production monitoring deployed or staffing commitment made.

## Architecture

Reuse the existing external Ploos monitoring platform where capacity and independence permit. Deploy local Prometheus collectors, Grafana dashboards, Alertmanager, Node Exporter and appropriate Proxmox, UPS and environmental exporters. Use Blackbox Exporter and SmokePing externally for reachability, latency and packet loss. Keep external probes and alert delivery independent of NO-SIR1 power, network and DNS dependencies. Evaluate a second independent probe provider. Secure metrics transport and management access; never expose exporters publicly. Keep secrets and detailed topology private.

## Monitoring coverage

| Domain | Signals |
|---|---|
| Facility | Temperature, humidity, water ingress, cooling state, power and energy |
| Electrical | UPS load, battery condition, runtime, supply failures and metered demand |
| Network | Reachability, latency, loss, interface errors, utilization, routing state |
| Compute | CPU contention, memory, disk health, thermals, quorum and VM availability |
| Storage | ZFS health, capacity, latency, replication lag and scrub results |
| Backup | Last successful backup, retention, off-site copy age and restore tests |
| Services | HTTP/TLS/DNS probes, provisioning errors and customer-facing availability |

Fire detection and electrical safety systems must be independently engineered and compliant; monitoring is supplementary.

## Alerts and initial thresholds

Illustrative starting thresholds, to be tuned against equipment limits and measured baselines: storage utilization warning 70%, critical 85%; backup overdue after 26 hours for daily policies; external service failure after three consecutive failed probes; alert on any degraded storage pool or loss of quorum. Set environmental and UPS thresholds from manufacturer limits and engineering design. Use severity levels, grouping, deduplication, maintenance silences and recovery notifications. Test notification delivery and dead-man heartbeat from outside the facility. Never assume automated alerts imply continuous human response.

## Operations

Daily automated health summary and review of actionable alerts during staffed hours. Weekly capacity and backup review. Monthly sample restore, patch review and alert delivery test. Quarterly recovery exercise and review of access, dependencies and spare inventory. Schedule electrical and cooling maintenance with qualified contractors. Use documented maintenance windows, change approvals, pre-change backups, rollback plans and customer communication.

Maintain private runbooks for power failure, cooling failure, network outage, node loss, degraded storage, backup failure, security incidents and service restoration. Record incident severity, impact, timeline, mitigation and follow-up. Publish a customer status page hosted independently of NO-SIR1, without sensitive operational details.

## Service objectives and staffing

Measure availability from customer-facing probes; define measurement windows, exclusions and per-product objectives before launch. Internal targets are not contractual SLAs. Establish staffed hours, escalation contacts, coverage during absence and realistic response commitments before accepting paying customers. Do not promise 24/7 human support without funded coverage. Monitor monitoring-system health, retention and costs; restrict tenant telemetry and avoid collecting unnecessary personal data.

## Acceptance gates

Demonstrate external detection of simulated site loss, independent notification delivery, local alerting, backup restoration, capacity alarms, status-page updates and documented incident escalation. Verify that alerting and recovery procedures work during planned maintenance. Obtain operational sign-off before public VPS launch.
