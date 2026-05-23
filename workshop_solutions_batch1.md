# DORA Workshop — Proposed Solutions
**Instructor Reference | CESC / DORA Workshop**

> These are defensible model answers, not the only correct ones. Students who justify different choices with clear reasoning should be credited equally. Use these as a benchmark for discussion, not as an answer key.

---

## Lecture Reference Map

| Lecture | Title | Tasks It Supports |
|---|---|---|
| Lecture 1 | The Significance of DORA | Background context across all tasks |
| Lecture 2 | Key Principles of DORA | T2 (proportionality), T5 (accountability), T6 (governance principle) |
| Lecture 3 | The Five Pillars of DORA | T1 (pillar mapping), T1 (interdependencies) |
| Lecture 4 | Key Definitions in DORA | T1 (concentration risk), T2 (critical function), T4 (major incident), T5 (concentration risk types) |
| Lecture 5 | Interaction with NIS 2 | T7 (NIS 2 alignment, CSIRTs) |
| Lecture 6 | Implementation and Audit under DORA | T2 (gap analysis framing), T5 (audit rights) |
| Lecture 7 | Implementing DORA – Overall Approach | T2 (gap analysis methodology), T5 (ISO 27001 assurance levels) |
| Lecture 8 | Implementing DORA – Planning and Initiation | T2 (gap analysis methodology) |
| Lecture 9 | Building the Compliance Engine | T2 (PDCA), T3 (risk register), T6 (RACI) |
| Lecture 10 | Governance under DORA | T6 (management body, RACI, terms of reference) |
| Lecture 11 | Risk Management | T1 (Pillar 1), T2 (ICT risk obligations), T3 (risk register, five phases) |
| Lecture 12 | Incident Response | T1 (Pillar 2), T4 (classification criteria, reporting stages, GDPR) |
| Lecture 13 | Digital Operational Resilience Testing | T1 (Pillar 3), T4 (forensic extension), T6 (TLPT governance) |
| Lecture 14 | ICT Third-Party Risk Management | T1 (Pillar 4), T2 (Pillar 4 gaps), T5 (Article 30, concentration risk, ISO 27001) |
| Lecture 15 | Information and Intelligence Sharing | T1 (Pillar 5), T7 (Article 45, ISACs, GDPR, notification) |

---

# BATCH 1 — Foundation Tasks

---

## Task 1 — Pillar Mapping

> 📚 **Source lectures:** Lecture 3 (Five Pillars — overview and interdependencies), Lecture 4 (Key Definitions — concentration risk, critical function), Lecture 11 (Pillar 1), Lecture 12 (Pillar 2), Lecture 13 (Pillar 3), Lecture 14 (Pillar 4), Lecture 15 (Pillar 5)

### Model Answer

| Pillar | Likely Already Doing | Likely Missing | Highest-Risk Gap |
|---|---|---|---|
| **1 — ICT Risk Management** *(→ L.11)* | Basic IT security policies, some incident logging, outdated risk register | Updated risk register, formal risk assessment cycle, documented critical function mapping | Risk register is 2 years old and does not reflect DataSwift or AWS concentration — the board cannot see their actual risk exposure |
| **2 — Incident Management** *(→ L.12)* | Informal IT helpdesk escalation process | Formal incident classification using DORA criteria *(→ L.4)*, multi-stage regulatory reporting procedures, incident register | No defined threshold for "major ICT-related incident" *(→ L.4)* — NordPay does not know when they are legally required to notify regulators |
| **3 — Digital Resilience Testing** *(→ L.13)* | Basic vulnerability scanning, possibly annual pen testing | TLPT (never conducted), threat-led testing, formal result documentation and remediation tracking | No TLPT ever conducted — NordPay has no objective evidence of resilience against real-world attack scenarios |
| **4 — Third-Party Risk Management** *(→ L.14)* | DataSwift and BankCore contracts in place (pre-DORA), basic vendor management | Article 30-compliant contracts, concentration risk assessment *(→ L.4)*, ongoing monitoring, exit strategies | DataSwift contract has no audit rights, no incident notification clause, no exit plan — it is a single point of failure with no contractual fallback |
| **5 — Information Sharing** *(→ L.15)* | Likely none | ISAC participation or equivalent arrangement, formal notification to competent authority | No participation in any intelligence sharing — NordPay has no early warning system for threats targeting payment processors |

### Technical Extension Answer

DataSwift (Pillar 4) creates the worst **ICT concentration risk** *(→ L.4 — definition of ICT Concentration Risk)*  — it is the sole payment routing provider with no secondary option. A DataSwift outage equals a total NordPay service outage. AWS (Pillar 1) is the second-highest: single-region cloud dependency with no documented failover architecture.

The **interdependence of pillars** *(→ L.3)* is visible here: the Pillar 4 gap (no Article 30 contract) directly causes the Pillar 2 gap (no incident notification from DataSwift), which worsens the Pillar 1 gap (stale risk register misses the dependency entirely).

---

## Task 2 — Gap Analysis

> 📚 **Source lectures:** Lecture 2 (proportionality principle), Lecture 4 (critical function, ICT risk definitions), Lecture 6 (implementation framing, audit readiness), Lecture 7 (gap analysis methodology, ISO 27001, assurance), Lecture 8 (gap analysis as project starting point), Lecture 9 (PDCA, documentation), Lecture 11 (Pillar 1 obligations), Lecture 14 (Pillar 4 obligations, Article 30, concentration risk)

### Model Answer — Pillar 1: ICT Risk Management *(→ L.11)*

| Current State | Required State | Severity | Proportionality Applicable? *(→ L.2)* | First Action |
|---|---|---|---|---|
| Risk register exists but 2 years old, not reviewed | Updated register reviewed at least annually, covering cyber / third-party / operational risks | **High** | No — all in-scope entities must maintain one | Commission updated risk register covering all current ICT assets and providers |
| No documented critical function mapping *(→ L.4 — Critical or Important Function)* | All critical / important functions formally identified and mapped | **High** | No — required for all entities | Conduct Business Impact Analysis (BIA) to identify and document critical functions |
| IT security policies exist but not aligned to DORA Article 9(4) *(→ L.11)* | Policies must cover: ICT security, change management, access control, backup/restore, incident response | **Medium** | Yes — depth scales with entity size | Review existing policies against Article 9(4); create or update missing ones |
| No formal PDCA review cycle for ICT risk *(→ L.9)* | Continuous improvement cycle embedded in governance | **Medium** | Yes — simplified cycle acceptable for ~450-person entity | Establish quarterly ICT risk review at management level |

### Model Answer — Pillar 4: Third-Party Risk Management *(→ L.14)*

| Current State | Required State | Severity | Proportionality Applicable? *(→ L.2)* | First Action |
|---|---|---|---|---|
| DataSwift contract: standard SaaS 2021, no Article 30 elements *(→ L.14)* | Contract must include audit rights, incident notification, exit strategy, data location, security standards | **High** | No — Article 30 is mandatory for all critical ICT providers | Initiate contract renegotiation with DataSwift immediately |
| No formal ICT provider register *(→ L.14)* | Register of all ICT third-party providers with criticality classification required | **High** | No | Create ICT provider inventory: AWS, DataSwift, BankCore + all known subcontractors |
| No pre-contract risk assessment process *(→ L.14)* | Risk assessment required before engaging or renewing any ICT provider | **Medium** | Yes — depth scales with criticality | Develop risk assessment template; apply retrospectively to current providers |
| AWS is sole cloud provider; no secondary | Concentration risk *(→ L.4)* must be identified and mitigated | **High** | No — concentration risk assessment is mandatory | Assess AWS dependency; evaluate secondary cloud provider or multi-region architecture |
| DataSwift subcontractors unknown *(→ L.14 — subcontracting and chain risk)* | Subcontracting chain must be understood and controlled | **High** | Proportionality on depth, not on the requirement itself | Request DataSwift subcontractor disclosure; map full service delivery chain |

### Technical Extension Answer

**Pillar 1:** BankCore GmbH runs on on-premise servers deployed in 2019 with no documented patch management cycle — a **protection and prevention** gap *(→ L.11 — five-phase risk management cycle)*. Any unpatched CVE is a live ransomware entry point. Mitigation: implement quarterly patching schedule; segment BankCore network zone; deploy EDR tooling.

**Pillar 4:** AWS configuration has no documented failover region — a **single point of failure** in the infrastructure layer *(→ L.14 — SPOFs)*. DataSwift integration likely uses static API keys with no IP allowlisting — a **detection** gap *(→ L.11)* that also creates an uncontrolled authentication surface.

---

## Task 3 — Risk Register

> 📚 **Source lectures:** Lecture 4 (ICT Risk definition), Lecture 9 (risk register as a living compliance instrument), Lecture 11 (five-phase risk management — identification, protection, detection), Lecture 14 (third-party risks, SPOFs, subcontracting chain)

### Model Answer

| # | Risk | Category | Likelihood (1–5) | Impact (1–5) | Current Controls | Owner | Priority |
|---|---|---|---|---|---|---|---|
| 1 | DataSwift API failure causing complete payment routing outage *(→ L.14)* | Third-Party | 4 | 5 | SLA 99.5% — no enforcement mechanism; no exit plan | CTO | **Critical** |
| 2 | AWS single-region outage — no secondary cloud provider or failover architecture | Infrastructure | 2 | 5 | AWS standard SLA; no documented failover | CTO | **High** |
| 3 | Ransomware attack on BankCore GmbH on-premise server (2019 deployment, unverified patch status) *(→ L.11 — protection phase)* | Cyber | 3 | 5 | Antivirus software; basic patching (undocumented cycle) | ICT Operations | **High** |
| 4 | Unauthorized access via compromised or exfiltrated DataSwift API keys *(→ L.11 — detection phase)* | Cyber | 3 | 4 | API key rotation policy (informal; not contractually enforced on DataSwift) | ICT Operations | **High** |
| 5 | DORA audit failure — insufficient documentation and evidence of compliance *(→ L.6, L.9)* | Operational | 4 | 4 | Compliance team awareness; no formal DORA programme | Compliance Officer | **High** |
| 6 | Staff phishing attack leading to credential compromise *(→ L.11 — protection phase)* | Cyber | 4 | 3 | Annual security awareness training; no simulated phishing exercises | ICT Operations | **Medium** |

### Technical Extension Answer

**Risk 3 — BankCore ransomware** *(→ L.11 — protection and prevention)*: On-premise software from 2019 with no documented patch management cycle. Any unpatched CVE is a live ransomware entry point. Mitigation: quarterly patching schedule; network segmentation of BankCore zone; EDR tooling on all on-premise servers.

**Risk 4 — API key compromise** *(→ L.11 — detection; L.14 — contractual security standards)*: The DataSwift integration likely relies on static API keys without rotation or IP allowlisting *(→ L.14 — minimum security standards)*. A single credential leak gives an attacker persistent access to payment routing. Mitigation: API key rotation every 90 days; mutual TLS (mTLS) authentication; IP allowlisting at the DataSwift API gateway.

