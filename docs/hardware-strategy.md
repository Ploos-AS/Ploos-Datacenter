# NO-SIR1 — Server and hardware strategy

Status: proposed architecture; no hardware purchased or supplier selected.

## Hardware tiers

| Role | Candidate hardware | Requirements |
|---|---|---|
| Internal lab and lightweight SaaS | Used Dell Micro, Lenovo Tiny, HP Mini, Intel NUC | Measured idle power, replaceable storage, supported firmware |
| Commercial VPS compute | Refurbished enterprise rack servers or efficient modern server platforms (AMD EPYC, Intel Xeon, server-grade Ryzen where validated) | ECC RAM, remote management, supported firmware, mirrored enterprise SSDs with power-loss protection, 10 GbE capability |
| Storage and backup | Separate storage servers | ECC, appropriate drive endurance, monitoring, tested restores, off-site copies |
| Network and management | Managed switches, routers and independent monitoring | VLANs, tenant isolation, secure management, spare capacity |

Mini PCs are suitable for selected internal workloads, not the default public VPS compute tier. Evaluate newer efficient hardware against older dual-socket servers using measured whole-system consumption, performance and total cost.

## Reference pilot

Three compute nodes are an illustrative target, not a purchase specification. Each: 16 physical cores / 32 threads where supported, 192 GiB ECC RAM, two 4 TB enterprise SSDs in a mirror, remote management and 10 GbE. Confirm CPU performance, DIMM compatibility, storage endurance, cooling and actual power draw.

With one node unavailable, two nodes provide 384 GiB installed RAM. Reserving 32 GiB per surviving node for host and operational headroom leaves 320 GiB theoretical guest RAM. This is an upper planning bound, not guaranteed sellable capacity: workload placement, CPU, storage, IOPS and failover constraints may reduce it. Local mirrors alone do not provide cross-node storage availability or automatic failover; replication and recovery design must be validated separately. No memory overcommit in initial commercial capacity planning.

Two 4 TB drives mirrored provide approximately 4 TB decimal raw usable capacity per node before filesystem overhead and free-space reserve. Do not count backup capacity as production storage.

## Procurement and acceptance

Compare used and new offers including VAT treatment, shipping, warranty, rails, caddies, RAM, SSDs, NICs, licensing, spares and electricity. Seek Norwegian ITAD lots and refurbished enterprise equipment. Do not buy obsolete hardware merely because acquisition cost is low.

For each candidate record purchase cost, idle and representative load watts at the wall, CPU benchmark, RAM capacity, storage health and endurance, firmware support, noise, dimensions, and replacement availability. Test memory, CPU stability, SSD health, network throughput, thermal behavior and remote management before admission. Sanitize reused drives using verified methods; reject equipment with unresolved security or reliability issues.

## Economics

Monthly electricity per node = measured average watts / 1000 × 730 × facility PUE × marginal NOK/kWh. Example: 100 W at PUE 1.3 and NOK 1.25/kWh costs about NOK 119/month; 250 W costs about NOK 297/month. Excludes fixed and demand charges. Compare three-year total cost, including replacement and support, against conservative sellable capacity.

Initial hardware planning allowance in the project budget is NOK 50,000–100,000 for servers, excluding separately budgeted network and facility equipment. The three-node reference design may exceed this allowance; obtain quotes and revise scope rather than treating it as funded.

## Operational gates

Maintain spare drives, compatible memory and replacement network components. Inventory assets privately; keep serial numbers, management addresses and access details outside public GitHub. Validate isolation, capacity limits, backup restoration and node-loss recovery before selling VPS capacity. Keep independent off-site backup and monitoring. Expand only after measured demand and approved financing.
