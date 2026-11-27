# NO-SIR1 connectivity strategy

Status: proposed; no carrier coverage, price or contract confirmed.

## Phases
- Internal pilot: symmetric business fiber, target 1 Gbps, routed IPv6 and public IPv4, explicit hosting permission.
- Public VPS: evaluate independent second fiber route, carrier DDoS mitigation, documented repair SLA and tested failover. Disclose any remaining single points of failure.
- Expansion: 10 Gbps interfaces, two upstreams, own ASN and suitable globally routable address resources subject to RIPE policy and commercial feasibility.

## Carrier enquiry
Investigate local access operators, Altifiber/Altibox business partners, GlobalConnect and Telenor Wholesale. These are enquiry candidates, not confirmed site providers. Ask for 1 and 10 Gbps options, installation and monthly fees, committed bandwidth, burst and traffic charges, SLA, physical route independence, customer hosting/resale permission, IP allocation and reverse DNS, BGP, DDoS mitigation, contract duration and lead time. Compare direct internet access against Ethernet transport to an upstream POP; include both transport and transit costs.

Reference product descriptions (not site offers):
- Telenor Wholesale: https://www.telenorwholesale.no/wp-content/uploads/2022/06/Internet-Service-Portfolio_Global-IP-Transit_tjenestebeskrivelse_Gyldig-fra-1.6.2022.pdf
- GlobalConnect: https://bedrift.globalconnect.no/wp-content/uploads/2023/01/Tjenestebeskrivelse-Internett-GC-13.01.2023-v.4.22.pdf
- RIPE NCC policy and resource guidance: https://www.ripe.net/

## Address strategy
IPv6 by default; request a suitable provider allocation and plan customer subnet delegation. Validate policy before assigning downstream resources. Offer shared IPv4 NAT only with clearly documented inbound port limitations; dedicated public IPv4 as optional paid resource. Track allocation, abuse ownership and reverse DNS. Compare provider-assigned IPv4 blocks with leased or transferred resources; /24 is a common global IPv4 routing minimum, not an entitlement. Evaluate sponsoring LIR versus membership, ASN eligibility, IPv6 allocation versus PI restrictions, RPKI ROAs and IRR records before independent BGP.

## Internal network
Separate management, storage, backup and tenant traffic. Evaluate redundant switches and routers as demand grows. Use tenant isolation, source validation, default-deny management access, prefix filters and maximum-prefix limits. Evaluate FRR/VyOS and independent external monitoring. Keep authoritative DNS and recovery access outside the site. Never publish actual addressing or security configurations here.

## Cost and acceptance
Monthly connectivity cost = access + transport + transit + IP resources + DDoS + maintenance. Model per-customer contribution under low occupancy; measure peak traffic and reserve capacity. Before public launch verify throughput, packet loss, IPv4/IPv6 reachability, reverse DNS, isolation, failover, recovery, abuse response and provider permissions. Mobile backup may support management but is not equivalent to redundant production transit.

No binding site acquisition until written connectivity and utility offers are available.
