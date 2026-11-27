# NO-SIR1 — Virtualization and storage

Status: proposed architecture, subject to lab validation and procurement.

## Platform
Use Proxmox VE with KVM virtual machines for public VPS workloads. Use Debian-based cloud images, cloud-init and SSH keys. LXC may serve trusted internal workloads but is not the default public tenant boundary. Evaluate subscriptions and support costs before production. Keep Ploos-VPS control plane separate from hypervisors; use scoped API credentials, asynchronous provisioning, idempotency and audit logs. Never expose management interfaces to tenants.

## Pilot and growth
Start with a single lab node; target three compute nodes for production evaluation. Three voting nodes permit quorum after one node loss if the remaining nodes communicate. Quorum alone does not guarantee VM availability. Use separate management, tenant, migration and storage networks or validated isolation and bandwidth controls. Test fencing, quorum loss, node maintenance and recovery before enabling HA.

## Storage
Start with local mirrored enterprise SSDs using ZFS. Reserve free space and RAM for host workloads and ZFS; monitor endurance, latency, capacity and scrub results. Local mirrors protect against a single drive failure, not node loss. Evaluate scheduled Proxmox ZFS replication for selected VMs; asynchronous replication can lose recent writes. Validate recovery point and recovery time objectives before offering any HA product. Never advertise zero data loss from asynchronous replication.

Consider Ceph only after benchmarking adequate dedicated storage devices, failure domains, network capacity and operational staffing. Three nodes are a minimum evaluation topology, not a guarantee of sufficient resilience. Three-way replication consumes roughly three times logical data capacity before overhead and reserve. Do not deploy Ceph merely to fill the initial rack.

## Backup
Use a separate Proxmox Backup Server and an independent off-site copy. Separate backup credentials and administrative domains; restrict deletion and test retention and restore procedures. Encrypt off-site backups where appropriate and protect recovery keys separately. Initial proposed internal target: daily backups, 24-hour RPO and 24-hour RTO for eligible workloads, subject to restore tests and capacity. Customer backup products and retention must be explicitly defined; snapshots are not backups. Test sample restores monthly and full recovery periodically.

## Capacity and isolation
Do not overcommit RAM initially. Model CPU contention, storage IOPS, replication traffic, backup windows and N+1 capacity separately. Use quotas, rate limits and tenant network isolation; test cross-tenant access prevention. Track actual resource use and reject provisioning when safe capacity is exhausted.

## Acceptance gates
Validate image integrity, provisioning and deletion, disk sanitization, tenant isolation, node loss, quorum, backup restoration, storage exhaustion, upgrade rollback and monitoring. Document measured recovery times and limitations. Keep secrets, production topology and addressing in restricted systems. Retain external monitoring and recovery capacity outside NO-SIR1.

No production deployment or hardware purchase is authorized by this document.
