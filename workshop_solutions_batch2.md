# DORA Workshop — Proposed Solutions
**Instructor Reference | CESC / DORA Workshop**

> These are defensible model answers, not the only correct ones 

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

### What Makes a Strong Student Answer

- Connects pillar gaps to each other — demonstrates understanding of pillar interdependence *(→ L.3)*
- Distinguishes between "missing the document" and "missing the underlying capability"
- Uses NordPay-specific evidence (DataSwift, BankCore, AWS) rather than generic compliance statements
- Justifies the prioritisation of one pillar over others with a risk-based argument *(→ L.2 — risk-based approach)*

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

### What Makes a Strong Student Answer

- Identifies High-severity gaps separately from Medium — does not treat all gaps as equal
- Correctly applies **proportionality** *(→ L.2)*: notes where it applies and where it does not (Article 30 and concentration risk assessment are non-negotiable regardless of size)
- First actions are specific and actionable — not "improve third-party risk management" but "initiate contract renegotiation with DataSwift"
- Flags assumptions — demonstrates the audit-ready mindset described in Lecture 6 *(→ L.6)*

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

### What Makes a Strong Student Answer

- Risk scoring is justified — likelihood and impact are argued, not guessed
- Risks span multiple categories — demonstrates the broad view of **ICT Risk** *(→ L.4)*
- Current controls column is honest: "annual training" is not strong, and the student names that
- Ownership is assigned to a specific role, not "the company" or "IT" — reflects the **RACI logic** introduced in Lecture 9 *(→ L.9)*
- At least one risk directly links to the gap analysis — shows the register is a living tool, not a static document *(→ L.9)*

---

# BATCH 2 — Scenario-Based Tasks

---

## Task 4 — Incident Classification & Regulatory Reporting

> 📚 **Source lectures:** Lecture 4 (definitions — major ICT-related incident, critical function, ICT-related incident), Lecture 12 (classification criteria, three reporting stages, communication, GDPR, root cause analysis), Lecture 13 (forensic extension — detection and investigation methods from TLPT chapter)

### Part A — Classification Decision

**Verdict: YES — this is a major ICT-related incident.** *(→ L.4 — definition of Major ICT-Related Incident; L.12 — classification framework)*

| Criterion *(→ L.12)* | Evidence | Assessment |
|---|---|---|
| Availability / Authenticity *(→ L.4 — ICT-Related Incident definition)* | Payment routing down ~3 hours (confirmed). API key anomaly detected since prior evening (suspected authenticity compromise) | Availability: confirmed impaired. Authenticity: under active investigation — treat as suspected |
| Criticality of affected services *(→ L.4 — Critical or Important Function)* | Payment routing is NordPay's core function — 100% of B2B transactions depend on DataSwift | Core function fully impaired. Criticality: maximum |
| Economic impact *(→ L.12)* | ~3h outage across 8 EU member states; transaction volume during downtime not yet known; SLA breach with clients likely | Economic impact: significant — formal major incident threshold exceeded |

Classification should be made with available information and explicitly flagged as preliminary. Students should note that **DORA does not require certainty before notification** *(→ L.12 — timing and evolution of information)* — classification is updated as the investigation progresses.

---

### Part B — Draft Initial Notification *(→ L.12 — Article 20, reporting stages)*

> **From:** [Compliance Officer], NordPay EU B.V.
> **To:** De Nederlandsche Bank (DNB) — Supervisory Department
> **Subject:** Major ICT-Related Incident — Initial Notification — NordPay EU B.V. — [Date / Time CET]
>
> Dear [Authority representative],
>
> NordPay EU B.V. hereby submits an initial notification pursuant to Article 19 of Regulation (EU) 2022/2554 (DORA).
>
> At approximately 11:30 CET on [date], NordPay's payment routing function became unavailable following an outage at a critical ICT third-party service provider, DataSwift sp. z o.o. (Warsaw, Poland). As of the time of this notification, the outage has persisted for approximately [X] hours. In addition, anomalous API key activity has been identified in NordPay's logs dating from approximately [time] on [date-1], suggesting possible unauthorized access. The nature and scope of this activity is currently under active investigation.
>
> The incident has impaired cross-border B2B payment processing across NordPay's operations in 8 EU member states. The number of affected clients and the precise financial impact have not yet been quantified. NordPay is treating this as a major ICT-related incident for the purposes of this notification, pending final classification upon completion of the forensic investigation.
>
> NordPay's ICT incident response team has been activated. Internal containment and forensic investigation are underway. We are in direct contact with DataSwift to establish root cause and restoration timeline.
>
> An intermediate report will be submitted as material information becomes available. A final report including root-cause analysis and remediation plan will be provided upon resolution.
>
> **Point of contact:** [Name, Title, Email, Phone]

---

### Part C — Information Map *(→ L.12 — three reporting stages)*

| Report Stage | Information Needed | NordPay Role Responsible |
|---|---|---|
| **Intermediate** | Confirmed number of affected clients and failed transactions | ICT Operations / Business Operations |
| **Intermediate** | Scope of API key compromise — exfiltration confirmed or ruled out | ICT Operations / external forensics |
| **Intermediate** | DataSwift's root cause statement and restoration timeline | CTO (vendor liaison) |
| **Intermediate** | GDPR assessment — was personal data accessed? *(→ L.12 — GDPR parallel obligation)* | Data Protection Officer / Compliance |
| **Final** | Financial impact estimate — SLA breach exposure, penalties | Finance / Legal |
| **Final** | Complete root-cause analysis (technical and contractual) *(→ L.12 — root-cause analysis)* | CTO + ICT Operations |
| **Final** | All remediation steps taken | ICT Operations + Compliance |
| **Final** | Changes made to risk management framework *(→ L.12 — continuous improvement and risk re-evaluation)* | Compliance Officer |
| **Final** | Post-incident review findings | All functions |

### Technical Extension Answer — Forensic Steps (First 2 Hours) *(→ L.12 — documentation and recovery; L.13 — TLPT closure phase methodology)*

1. **Immediately rotate all DataSwift API keys** — revoke current credentials and issue new ones; limits ongoing unauthorized access before root cause is confirmed *(→ L.11 — response phase)*
2. **Pull and preserve all API gateway logs** from the past 72 hours — timestamps, source IPs, request volumes, endpoint targets; these are the primary evidence chain *(→ L.12 — documentation)*
3. **Capture memory images** of any affected servers before remediation begins — essential for forensic chain of custody if criminal action is suspected *(→ L.13 — TLPT closure phase: forensic outputs)*
4. **Identify all NordPay systems** that have authenticated to DataSwift endpoints in the past 72 hours — map the blast radius *(→ L.11 — detection phase)*
5. **Check for lateral movement indicators** — did source IPs seen in the API anomaly logs contact any other internal NordPay systems?
6. **Preserve logs in write-once storage** — logs that can be altered are not admissible evidence and undermine the regulatory report *(→ L.12 — documentation and recovery)*

These artefacts feed the regulatory report directly: timestamps establish the incident timeline; source IPs establish whether the attack was external or internal; API logs establish what data may have been accessed; memory captures support forensic attribution.

### What Makes a Strong Student Answer

- Classification argued using all three criteria *(→ L.12)*, not just one
- Initial notification sent despite incomplete information — not held until DataSwift confirms *(→ L.12)*
- Notification explicitly flags what is unknown and why it does not prevent notification
- Information map assigns ownership to specific roles, not "the company" or "IT"
- Students who identify GDPR as a **parallel reporting obligation** *(→ L.12)* show advanced understanding of the regulatory compliance dimension

---

## Task 5 — Third-Party Contract Evaluation

> 📚 **Source lectures:** Lecture 2 (accountability principle — outsourcing ≠ delegating responsibility), Lecture 4 (ICT concentration risk definition), Lecture 6 (audit rights and contractual adjustments), Lecture 7 (three levels of assurance; ISO 27001 as evidence of compliance), Lecture 14 (Article 30 elements, subcontracting chain, concentration risk Types 1 and 2, lead overseers, exit strategies, security standards, audit rights)

### Part A — Missing Article 30 Elements *(→ L.14)*

| Missing Element | DORA Basis | Risk to NordPay |
|---|---|---|
| Audit and access rights *(→ L.14, L.6)* | Art. 30(2)(d) | NordPay cannot verify DataSwift's security posture or compliance — oversight is impossible without access |
| Incident notification timeline *(→ L.14, L.12)* | Art. 30(2)(f) | NordPay has no contractual right to early warning — today's incident was discovered internally, not reported by DataSwift |
| Subcontracting disclosure and approval *(→ L.14 — subcontracting and chain risk)* | Art. 30(2)(g) | NordPay has no visibility into DataSwift's service delivery chain — unknown sub-vendor failures cannot be anticipated |
| Data location and residency requirements | Art. 30(2)(e) | NordPay cannot confirm that data processed by DataSwift stays within EU jurisdiction |
| Exit strategy and transition plan *(→ L.14 — testing and exit strategies)* | Art. 30(2)(h) | A DataSwift termination would strand NordPay with no migration path and no timeline for data return |
| Minimum security standards obligation *(→ L.14 — security standards and certification)* | Art. 30(2)(c) | DataSwift has no contractual obligation to maintain any specific security baseline |
| Business continuity obligations *(→ L.14)* | Art. 30(2)(b) | DataSwift has no obligation to share or maintain a business continuity plan covering NordPay's services |

---

### Part B — Three Critical Draft Clauses *(→ L.14 — contractual requirements)*

**Clause 1 — Audit and Access Rights** *(→ L.14 — audit rights and data access; L.6 — audit process)*

> The Service Provider shall grant the Client, and any competent supervisory authority designated by the Client, the right to conduct audits and inspections of the Service Provider's relevant premises, systems, processes, and documentation. Audit requests shall be submitted with a minimum of ten (10) business days' prior written notice, except where a security incident is suspected or ongoing, in which case audits may be initiated within twenty-four (24) hours of written notice. The Service Provider shall cooperate fully and provide timely access to all information reasonably required for audit purposes. The cost of audits shall be borne by the Client unless the audit reveals material non-compliance, in which case costs shall be borne by the Service Provider.

**Clause 2 — Incident Notification** *(→ L.14 — incident notification; L.12 — reporting timeline)*

> The Service Provider shall notify the Client without undue delay — and in any event within four (4) hours of detection — of any ICT-related incident that affects or may affect the availability, integrity, confidentiality, or authenticity of services or data provided under this Agreement. Such notification shall include: (a) the nature and scope of the incident; (b) the systems and data affected; (c) the estimated impact on service continuity; and (d) the actions taken or planned. Progress updates shall be provided every four (4) hours until the incident is fully resolved. Failure to notify within the stipulated timeframe constitutes a material breach of this Agreement and entitles the Client to terminate immediately under Clause [X].

**Clause 3 — Exit Strategy and Transition** *(→ L.14 — testing and exit strategies)*

> Upon termination of this Agreement for any reason — whether by notice, breach, or insolvency — the Service Provider shall: (a) continue to deliver services at agreed performance standards for a transition period of not less than ninety (90) calendar days from the date of termination notice; (b) return all Client data in a mutually agreed interoperable format within thirty (30) calendar days of the effective termination date; (c) permanently and irreversibly delete all copies of Client data within sixty (60) calendar days of the effective termination date, confirmed in writing by a duly authorised officer of the Service Provider; and (d) provide reasonable technical cooperation to facilitate the Client's migration to an alternative provider, including provision of relevant technical documentation and API specifications.

---

### Part C — Concentration Risk Assessment *(→ L.4 — ICT Concentration Risk; L.14 — Types 1 and 2)*

DataSwift represents a **Type 1** concentration risk *(→ L.14)*: a single provider delivering NordPay's most critical ICT function (payment routing). It may also constitute a **Type 2** risk *(→ L.14)* if DataSwift serves other EU payment institutions simultaneously — meaning a DataSwift outage could impair multiple financial entities at once, creating systemic risk.

| Type *(→ L.14)* | Definition | NordPay's Situation |
|---|---|---|
| Type 1 | One provider, multiple or critical services to same entity | DataSwift is the sole payment routing provider — any outage = total NordPay service failure |
| Type 2 | Many institutions dependent on same provider | Likely, given DataSwift is a fintech API provider — requires verification |

**NordPay's current fallback: none.** No secondary payment routing provider. No documented alternative mechanism. No transition plan. This is the most critical single finding of the engagement.

The **accountability principle** *(→ L.2)* applies directly here: NordPay cannot transfer responsibility for payment routing resilience to DataSwift, regardless of what the contract says or fails to say.

### Technical Extension Answer — ISO 27001 Assessment *(→ L.7 — three levels of assurance; L.14 — security standards and certification)*

An ISO 27001 certificate issued 18 months ago is **insufficient** as standalone evidence under DORA:

1. DORA requires *ongoing* compliance evidence, not a point-in-time certification *(→ L.7 — third-party assurance)*
2. 18 months is approaching the 3-year recertification cycle — interim surveillance audits may have lapsed
3. The certificate covers DataSwift's ISMS scope — which may not include the specific systems used to deliver NordPay's payment routing API
4. ISO 27001 confirms a management system exists — it does not confirm that specific controls are effective *(→ L.7 — assurance limitations)*

**Additional assurance NordPay should contractually require** *(→ L.14 — certification and evidence)*:
- Most recent surveillance audit report (within last 12 months)
- Results of DataSwift's most recent penetration test
- DataSwift's formal ICT incident history for the past 24 months
- Written confirmation that the ISO 27001 scope covers the payment routing API service specifically
- Right to conduct NordPay's own audit (Clause 1 above)

### What Makes a Strong Student Answer

- Lists all seven missing Article 30 elements *(→ L.14)*, not just the obvious ones
- Draft clauses include timescales, triggers, and consequences — not vague obligations
- Correctly identifies DataSwift as Type 1 and raises the possibility of Type 2 *(→ L.14)*
- Acknowledges NordPay has no fallback — does not soften this finding
- Students who link the missing incident notification clause to the 14:07 CTO message demonstrate applied understanding of the **accountability principle** *(→ L.2)*

---

## Task 6 — Governance RACI

> 📚 **Source lectures:** Lecture 2 (governance principle, accountability principle), Lecture 9 (RACI matrix — structure and purpose), Lecture 10 (management body responsibilities, third-party oversight, terms of reference), Lecture 13 (TLPT governance — board approval of remediation)

### Model Answer *(→ L.9 — RACI; L.10 — management body duties)*

| Control | Board | CTO | Compliance Officer | ICT Operations |
|---|---|---|---|---|
| ICT risk register maintenance *(→ L.9, L.11)* | I | A | C | R |
| Incident classification and escalation *(→ L.12)* | I | A | C | R |
| Third-party contract oversight *(→ L.14, L.10)* | I | C | **A** | R |
| TLPT scheduling and remediation *(→ L.13)* | A | C | **R** | C |
| Business continuity plan approval *(→ L.10)* | **A** | I | C | R |
| Information sharing participation *(→ L.15)* | **A** | C | R | I |

*Bold = roles where vacancy creates the most immediate compliance risk*

---

### Vacancy Analysis *(→ L.10 — governance as a compliance safeguard)*

NordPay does not have a formally designated DORA Compliance Officer. This creates the following accountability vacancies:

| Control | Vacant Role | Consequence |
|---|---|---|
| Third-party contract oversight | Compliance Officer (A) *(→ L.10)* | Nobody owns the DataSwift contract review — which is why the contract is four years old and missing every mandatory Article 30 clause *(→ L.14)* |
| TLPT scheduling and remediation | Compliance Officer (R) *(→ L.13)* | Nobody is responsible for scheduling TLPT — which is why it has never been conducted |
| Information sharing participation | Board (A) *(→ L.15)* | The board has never formally decided whether NordPay participates in intelligence sharing — the answer by default is no |

**The direct consequence of the governance vacancy today:** When the 14:07 message arrived, no one was formally accountable for the DataSwift relationship *(→ L.2 — governance principle)*. The CTO received the alert from a system notification — not from DataSwift. The contract did not require DataSwift to notify. Nobody owned the contract. The governance gap created the information gap.

**Recommendation:** NordPay should immediately designate a DORA Compliance Officer — or formally assign DORA accountability to an existing role, with a documented terms of reference *(→ L.10 — terms of reference)*. The first task of that role is to own this RACI and ensure every control has a named Accountable individual.

### What Makes a Strong Student Answer

- No control is left with an empty Accountable cell — every row has exactly one A *(→ L.9)*
- The vacancy analysis is specific: names which vacancies create which risks
- Students trace the governance gap to the operational failure (no contract owner → no Article 30 clauses → no incident notification → 14:07 surprise) — demonstrates understanding of **pillar interdependence** *(→ L.3)*
- Students who note the Board must hold Accountable for strategic decisions show understanding of the **governance principle** *(→ L.2, L.10)*

---

## STRETCH Task 7 — Information Sharing Arrangement

> 📚 **Source lectures:** Lecture 5 (NIS 2 alignment, CSIRTs, cross-framework coordination), Lecture 15 (Article 45, voluntary participation, IOCs and TTPs, formal arrangement elements, GDPR compliance, ISACs, notification to competent authority)

### Part A — What to Share and What to Withhold *(→ L.15 — key types of information)*

| Share | Withhold | Reason for Withholding |
|---|---|---|
| IOCs *(→ L.15)*: anomalous API key activity patterns, specific API call signatures, timing and volume profiles | Client-specific transaction data | GDPR — personal and commercial transaction data must not be shared without legal basis *(→ L.15 — secure and responsible sharing)* |
| TTPs *(→ L.15)*: method of API credential exposure (credential stuffing / supply chain / insider — once forensically confirmed) | NordPay's internal system architecture and network topology | Commercial sensitivity; disclosure could expose further attack surface |
| Alert: payment routing API provider experienced availability failure correlated with authentication anomaly during [timeframe] | Vendor identity (DataSwift) unless forensic evidence confirms their role and legal review permits naming | Naming without confirmed evidence creates defamation and commercial liability exposure |
| Timeline: duration of outage, sequence of events, detection method | NordPay's regulatory correspondence with DNB | Privileged communications between NordPay and its supervisory authority |

---

### Part B — Formal Arrangement Elements (Article 45) *(→ L.15)*

1. **Participant identification:** names and roles of all financial entities, public authorities, and ICT providers participating in the arrangement
2. **Technical platform:** the secure channel or system used for intelligence exchange (e.g., encrypted portal, STIX/TAXII structured feed)
3. **Governance responsibilities:** who validates intelligence before sharing; who manages access credentials; who resolves disputes
4. **Data protection responsibilities:** how GDPR and confidentiality obligations are met *(→ L.15 — confidentiality and GDPR)*; what anonymisation standard applies
5. **Retention and deletion rules:** how long shared intelligence is stored; under what conditions it is updated or withdrawn
6. **Validation and update process:** how outdated or incorrect indicators are corrected or recalled; how quality is maintained

---

### Part C — Notification to DNB *(→ L.15 — notification obligations)*

NordPay must notify DNB upon **joining** and upon **leaving** the ISAC. This notification is administrative — no approval required, only transparency. It should include:
- Name and description of the ISAC
- Date of membership commencement
- Types of intelligence NordPay will share and receive
- Summary of the arrangement's governance and data protection approach

---

### Part D — Sharing the DataSwift Incident Without Exposure *(→ L.15 — secure and responsible sharing; value of secure sharing platforms)*

1. **Anonymise the vendor** *(→ L.15)*: describe as "a third-party payment routing API provider" — do not name DataSwift until forensic evidence confirms their role and legal review permits attribution
2. **Share IOCs only in the first instance** *(→ L.15)*: API anomaly signatures, IP ranges, timing profiles — none of these identify NordPay or DataSwift
3. **Use TLP:AMBER labelling** *(→ L.15 — value of secure sharing platforms)*: permits recipients to use intelligence internally but not distribute further
4. **Coordinate with DataSwift's legal team** before named disclosure — simultaneous coordinated disclosure is more defensible than unilateral attribution
5. **Work through the ISAC's legal framework** *(→ L.15 — legal protections for sharing)*: established ISACs include liability protections for good-faith anonymised sharing

### What Makes a Strong Student Answer

- Distinguishes between IOCs (safe to share anonymised), TTPs (share once confirmed), and internal architecture (never share) *(→ L.15)*
- Correctly identifies DORA does not require ISAC participation — the value is strategic *(→ L.15 — voluntary participation)*
- Recognises the DataSwift incident has **systemic value** for the sector — if other payment institutions use similar API routing, this intelligence prevents replication
- Students who connect Article 45 to NIS 2's CSIRT framework *(→ L.5)* show strong cross-framework understanding

