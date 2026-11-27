# NO-SIR1 — Security and regulatory readiness

Status: proposed baseline, not legal advice, certification or confirmation of compliance. Verify current Norwegian requirements before construction and commercial launch.

## Regulatory workstream

- Ask Nkom whether Ploos AS and NO-SIR1 fall within current datacenter registration, security, preparedness, reporting and supervision requirements. Confirm deadlines and any separate obligations for electronic communications services.
- Confirm applicability of the Norwegian digital security legislation and any applicable sector-specific requirements; do not assume small size automatically exempts the operator.
- Obtain municipal guidance on zoning, building permits and technical requirements. Engage qualified electrical and fire safety professionals; assess workplace safety, noise, environmental and insurance requirements.
- Maintain a private compliance register with legal basis, applicability, owner, evidence, deadlines and review dates.

Official starting points (current applicability not independently verified):
- https://nkom.no/
- https://lovdata.no/
- https://www.datatilsynet.no/
- https://www.dsb.no/
- https://www.dibk.no/

## Physical security

Restrict facility access to authorized personnel; maintain access records, visitor escort, revocation procedures and periodic reviews. Evaluate intrusion detection and appropriate surveillance with privacy assessment, signage and limited retention. Protect equipment from fire, water, environmental damage and unauthorized removal. Keep exact layouts, access mechanisms and security configurations private.

## Technical security

Separate tenant, management, storage and backup trust zones. Use MFA for privileged accounts, individual identities, least privilege, scoped API credentials, encrypted management channels and audited administrative actions. Maintain hardened images, patch schedules, vulnerability management, secret rotation and secure decommissioning. Test tenant isolation and recovery. Establish DDoS mitigation and abuse response with upstream providers. Do not expose hypervisor management publicly.

## Privacy and customer contracts

Map processing activities and determine controller and processor roles per service. Prepare GDPR Article 28 processor agreements where applicable, subprocessor inventory, retention and deletion policies, access controls, breach procedures and data subject request handling. Assess international transfers, including off-site backup, support and telemetry. Do not market all processing as Norwegian solely because primary compute is in Norway. Document actual data locations and contractual commitments. Assess whether a DPIA is required.

Prepare service terms, acceptable use policy, privacy notice, backup responsibilities, support hours, maintenance and suspension procedures. Define abuse reporting and lawful request handling. Review consumer rules if selling to individuals.

## Incident readiness

Maintain incident classification, escalation, evidence preservation, containment, recovery and customer communication procedures. For GDPR breaches, assess controller notification obligations including the applicable 72-hour supervisory authority deadline; processors notify controllers without undue delay. Verify separate Nkom and other statutory reporting obligations. Test incident response and backup restoration before launch.

## Assurance and launch gates

Use ISO 27001 and ISO 22301 as voluntary reference frameworks, without claiming certification. Assign accountable owners, obtain regulatory applicability assessments, complete permits and safety inspections, validate tenant isolation and recovery, approve contracts and privacy documentation, and test reporting and escalation. No public VPS launch until critical gaps are resolved and residual risks accepted. Review annually and after material changes.

No regulator contacted, registration submitted or certification obtained by this documentation activity.
