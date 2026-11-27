# NO-SIR1 — Power and energy strategy

Status: preliminary planning; no grid capacity, tariff or installation quote confirmed.

## Capacity targets

| Phase | IT load | Facility load at assumed PUE 1.3 |
|---|---:|---:|
| Pilot | 2 kW | 2.6 kW |
| Initial deployment | 5 kW | 6.5 kW |
| Expansion | 10 kW | 13 kW |
| Further expansion | 20 kW | 26 kW |

PUE 1.3 is an illustrative modeling assumption, not a performance guarantee. Size electrical infrastructure for peak demand, startup currents, UPS losses, battery recharge, cooling extremes and future loads using qualified engineering. Verify local voltage and earthing system before equipment selection.

## Grid enquiry

Identify the responsible distribution system operator for each candidate parcel. Request written information on available three-phase supply, connection cost, capacity reservation, lead time, energy and demand tariffs, metering, expansion and outage history. Compare 10, 20 and 40 kW facility connection scenarios without committing to capacity prematurely. Confirm applicable taxes and VAT with an accountant. No land purchase before acceptable written utility offers.

## Energy model

Monthly energy = average IT kW × measured or assumed PUE × 730 hours. Illustrative all-variable energy rates below exclude fixed fees, demand charges and capital recovery; do not double count charges when using actual tariffs.

| Average IT load | Facility kWh/month at PUE 1.3 | NOK 0.75/kWh | NOK 1.25/kWh | NOK 2.00/kWh |
|---|---:|---:|---:|---:|
| 2 kW | 1898 | 1424 | 2373 | 3796 |
| 5 kW | 4745 | 3559 | 5931 | 9490 |
| 10 kW | 9490 | 7118 | 11863 | 18980 |
| 20 kW | 18980 | 14235 | 23725 | 37960 |

Rounded to nearest NOK (half up). Track actual interval consumption, peak demand and IT energy separately. Allocate shared facility overhead to products by measured resource use; model idle consumption and low occupancy. Include network, staffing, depreciation and support before setting VPS prices.

## Resilience and safety

- Have qualified electrical contractors design distribution, protection, grounding, metering and maintenance isolation.
- Evaluate modular online UPS with monitored batteries and a preliminary 15–30 minute runtime objective at protected load. Validate runtime at end-of-life and test shutdown.
- Evaluate generator-ready infrastructure and reserve generation separately; UPS alone does not provide extended outage coverage.
- Use suitable rack PDUs and dual power supplies where justified; A/B feeds from one upstream source do not constitute independent utility supplies.
- Test alarm escalation, power failure, recovery and backup restoration before customer launch.
- Keep sensitive electrical diagrams and operational details private.

## Cooling and heat reuse

Evaluate filtered free cooling and efficient mechanical cooling for local seasonal conditions. Engineer for summer extremes, condensation, frost, snow, humidity, filtration and failure scenarios. Measure annual PUE rather than relying on nameplate efficiency. Almost all IT electrical energy becomes heat; investigate nearby heat demand, heat exchanger or heat pump economics, and seasonal mismatch. Assume zero heat revenue until an agreement and feasibility study exist.

## Acceptance gates

Obtain grid and contractor quotations, approve total cost and expansion plan, complete statutory electrical and fire checks, verify peak load and cooling capacity, test UPS and outage procedures, and document operational limits. Do not claim redundant power or uptime guarantees without verified design and tests.
