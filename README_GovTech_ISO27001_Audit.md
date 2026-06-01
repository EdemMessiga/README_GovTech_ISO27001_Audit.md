# ISO 27001:2022 ISMS Surveillance Audit GovTech Ontario

**Framework:** ISO/IEC 27001:2022 + GO-ITS Government Security Standards
**Industry:** Government / Public Sector Provincial Digital Services (Crown Agency)
**Entity (Fictional):** GovTech Ontario responsible for Ontario.ca citizen portal serving 8.3M citizens
**Audit Type:** Year 2 Annual Surveillance Audit (3-year certification cycle)
**Certification Body:** BSI Group Canada (fictional)
**Auditor:** Edem Messiga, ISO 27001 Certified Lead Auditor Chief Information Security Office
**Audit Period:** May 1 to 23, 2026 (15 business days)

---

## Why Government / Public Sector?

Government digital services represent a unique and demanding GRC environment. A Crown agency operating citizen-facing services handles PROTECTED B personal information for millions of people under the Freedom of Information and Protection of Privacy Act (FIPPA) and its ISO 27001 certification is not just a business credential, it is a public accountability mechanism. A Major Nonconformity that puts certification at risk must be disclosed, affects procurement eligibility, and can appear in public accountability reports.

This project simulates a Year 2 ISO 27001:2022 surveillance audit for a fictional Ontario provincial digital services agency. The audit applies both ISO 27001 Annex A requirements and Ontario's government-specific GO-ITS security standards which in several areas are more prescriptive than ISO 27001 alone. Every finding is analyzed through both lenses.

---

## Engagement Context

GovTech Ontario processes applications for 47 provincial services including drivers' licence renewals, health card applications, OSAP student financial aid, and business permits. The Ontario.ca platform is classified as PROTECTED B under Ontario's Information Security Classification Standard meaning citizen personal information that, if compromised, could cause serious injury to individuals.

This is a Year 2 surveillance audit in a 3-year ISO 27001 certification cycle. The Year 1 audit (June 2025) identified 2 Minor NCs both closed and 3 Opportunities for Improvement. Year 2 is therefore a higher-stakes audit: the organization is expected to have matured, and any systemic failures that survived Year 1's corrective actions represent a more serious concern.

---

## What Makes a Government ISO 27001 Audit Different

**Major NC = Certification at Risk.** In an ISO 27001 surveillance audit, a Major Nonconformity must be closed within 90 days or the certification body initiates a suspension review. For a government agency, certification suspension could affect procurement eligibility, contract requirements with enterprise clients (Ontario Health), and public accountability reporting. This is a real governance consequence, not just a compliance checkbox.

**GO-ITS standards are more prescriptive than ISO 27001.** The Ontario government's GO-ITS suite (25.0 for IAM, 25.20 for cryptography, 25.30 for change management, 25.50 for logging) specifies requirements that go beyond ISO 27001 Annex A minimums. For example, GO-ITS 25.50 requires a specific citizen_id field in audit logs this is more specific than ISO 27001 A.8.15 which only requires "adequate logging." Both standards are applied simultaneously in this audit.

**FIPPA intersects with ISO 27001 at every IAM and logging control.** Every access control and logging gap has a FIPPA dimension personal information accessible to an unauthorized person, or access to personal information not captured in an audit trail, is a potential FIPPA compliance issue as well as an ISO 27001 nonconformity.

---

## Audit Scope

**ITGC Domains Assessed:**
- Identity and Access Management (7 controls: A.5.15, A.5.16, A.5.17, A.5.18, A.8.2, A.8.3, A.8.4)
- Change Management (5 controls: A.8.32, A.8.29, A.8.25, A.8.26, A.8.27)
- Logging and Monitoring (4 controls: A.8.15, A.8.16, A.8.17, A.8.20)
- Cryptography (2 controls: A.8.24, A.8.25)
- Supplier Risk (4 controls: A.5.19, A.5.20, A.5.21, A.5.22)

---

## Key Findings

| Ref | Control | Type | Finding |
|---|---|---|---|
| NC-001 | GT-IAM-06 | **Major NC** | Access review failed to detect J. Beaumont role change 86 days of stale entitlements. Certification at risk. |
| NC-002 | GT-IAM-02 | Minor NC | Contractor account disabled 6 days post-expiry SuccessFactors contract module gap |
| NC-003 | GT-IAM-04 | Minor NC | Ministry Integration Admin role not reviewed in 2.5 years 'under redefinition' flag never cleared |
| NC-004 | GT-IAM-05 | Minor NC | Break-glass accounts lack session logging and quarterly review per GO-ITS 25.0 |
| NC-005 | GT-CHG-01 | Minor NC | Authentication flow changes bypass CAB via stale Standard Change category (pre-MFA architecture) |
| NC-006 | GT-CHG-02 | Minor NC | OSAP release DAST evidence missing ZAP upload failed silently without blocking release |
| NC-007 | GT-LOG-01 | Minor NC | citizen_id missing from OSAP middleware logs for 41 days FIPPA audit trail gap |
| NC-008 | GT-LOG-02 | Minor NC | SOC alert SLA missed Saturday coverage depends on sick analyst self-notification |
| NC-010 | GT-CRY-02 | Minor NC | Key destruction certificates missing for 2 annual rotations |
| NC-011 | GT-SUP-01 | Minor NC | DataStream Analytics vendor reassessment 4 months overdue contract amendment bypass |

**Overall:** 12 of 22 controls fully compliant | 1 Major NC | 9 Minor NCs | 2 OFIs
**Certification Status:** AT RISK NC-001 must be closed by August 25, 2026

---

## Deliverables

| File | Description |
|---|---|
| `GovTech_ISO27001_Audit_Workbook.xlsx` | 3-tab workbook: Engagement Overview (audit metadata, GO-ITS domain coverage, NC summary with formulas), ITGC Assessment (24 controls with ISO clause, audit procedure, population and sample, evidence, finding, NC type, root cause, government context, GO-ITS reference), NC and OFI Tracker (13 items with certification impact column) |
| `GovTech_ISO27001_Surveillance_Audit_Report.docx` | Formal surveillance audit report: Major NC escalation notice, government regulatory framework table, Major NC detailed finding with FIPPA dimension, 4 detailed Minor NC findings, complete NC summary table, positive observations section, certification status analysis, remediation timeline, and audit closing meeting record |

---

## What Makes This Project Realistic

**NC classification matters.** ISO 27001 has three finding types: Major NC (systematic failure, certification at risk), Minor NC (isolated failure or gap, must be closed before next audit), and OFI (Opportunity for Improvement, no certification consequence). This project uses all three correctly NC-001 is a Major NC because it is a systematic procedural gap, not an isolated error; NC-002 through NC-011 are Minor NCs for isolated failures; OFI-001 and OFI-002 are genuine improvement suggestions with no compliance consequence.

**The access review finding is nuanced.** NC-001 is a Major NC not because someone's access was wrong, but because the access review process has a systematic design gap it checks employment status but not current role. This is exactly the kind of finding that separates a surveillance audit from a checkbox exercise, and it is the kind of root cause analysis that a real ISO 27001 Lead Auditor would perform.

**Government-specific controls appear throughout.** The citizen_id logging requirement (GO-ITS 25.50), the break-glass account dual-person and session recording requirements (GO-ITS 25.0), and the Standard Change authentication reclassification (GO-ITS 25.30) are all grounded in Ontario government standards that go beyond ISO 27001 Annex A minimums. This shows understanding of how government GRC works in practice.

**The positive observations section is not an afterthought.** ISO 27001 audits should identify strengths as well as gaps a balanced report builds management trust and identifies best practices that can be shared across the organization. The SQL injection 58-hour remediation and the Digital ID threat model are genuinely strong controls worth showing.

---

## Government Security Standards Referenced

| Standard | Key Requirements Applied |
|---|---|
| GO-ITS 25.0 | IAM, PAM, MFA, access review cadence, break-glass account controls |
| GO-ITS 25.20 | AES-256 encryption, TLS 1.2 minimum, key destruction certificate requirements |
| GO-ITS 25.30 | Change management, SAST/DAST mandatory for citizen apps, Standard Change review cadence |
| GO-ITS 25.50 | Mandatory log fields including citizen_id, 1-year online retention, WORM immutability |
| Treasury Board Directive | Vendor of Record, annual reassessment, SOD, right-to-audit |
| FIPPA (R.S.O. 1990) | Personal information access audit trail, authorized access limits |
| Ontario Archives Act | 7-year minimum retention for government IT audit records |

---

## Lessons Learned

**The difference between Major and Minor NCs is about systematic vs. isolated failure.** NC-001 is Major because the access review procedure itself is flawed not just because one account was missed. Understanding this distinction is fundamental to ISO 27001 auditing. A single missed account would be a Minor NC; a procedure that will systematically miss an entire category of role changes is a Major NC.

**Government GRC requires dual-standard analysis.** Every finding in this engagement is evaluated against both ISO 27001:2022 Annex A and the applicable GO-ITS standard. Where GO-ITS is more prescriptive, GO-ITS governs. This is how GRC works in regulated government environments the ISO standard sets the floor, sector-specific standards set the ceiling.

**SOC coverage gaps are a systemic, not individual, problem.** NC-008 and NC-009 share the same root cause: a coverage procedure that depends on a sick individual to take action. The fix is not to ask analysts to be more diligent it is to implement a systematic control (automated on-call paging) that removes the human dependency. This is a principle that applies across many GRC control domains.

**Positive observations build credibility.** A surveillance audit report that only lists problems is less credible than one that demonstrates balanced judgment. Identifying the Digital ID threat model as a reference-quality deliverable and the SQL injection response as commendable shows that the auditor engaged fully with the evidence not just looked for gaps.

---

## Related Projects

| Repository | Framework |
|---|---|
| [GRC-PCI-DSS-v4-MapleFinancial](../GRC-PCI-DSS-v4-MapleFinancial) | PCI-DSS v4.0 Canadian Regional Bank |
| [GRC-SOC2-TypeI-CareSync](../GRC-SOC2-TypeI-CareSync) | SOC 2 Type I Healthcare SaaS (EHR platform) |
| [GRC-NIST-CSF-NovaSaaS](../GRC-NIST-CSF-NovaSaaS) | NIST CSF 2.0 Canadian B2B SaaS company |
| [GRC-PIA-PIPEDA-CanRetail](../GRC-PIA-PIPEDA-CanRetail) | PIA Canadian Retail Loyalty Program |

---

## About the Author

**Edem Messiga**
ISO 27001 Certified Lead Auditor | Cybersecurity GRC | Bilingual EN/FR
[linkedin.com/in/edem-messiga](https://linkedin.com/in/edem-messiga)

> All entities, government references, individuals, systems, and regulatory citations in this project are fictional or used for illustrative purposes. This document was created for professional portfolio and development purposes only.
