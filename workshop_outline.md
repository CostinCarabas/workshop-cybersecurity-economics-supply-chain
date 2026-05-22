# DORA in Practice — A Day as a Compliance Consultant
**CESC / DORA Workshop**

---

## Your Brief

You are a DORA compliance consultant. NordPay EU B.V. — a payment institution regulated in Amsterdam — has brought in your team. Their supervisory authority has signalled that a review is coming. NordPay's internal assessment puts them at roughly forty percent compliant. They know they have gaps. They do not know which ones to fix first, or how.

That is what you are here for.

---

## NordPay EU B.V. — Company Profile

| Attribute | Detail |
|---|---|
| Entity type | Payment Institution (PSD2-licensed, DORA in-scope) |
| Size | ~450 employees, operations in 8 EU member states |
| Core business | Cross-border B2B payment processing for SMEs |
| Cloud infrastructure | AWS (primary), no secondary provider |
| Critical fintech API | DataSwift sp. z o.o. (Warsaw) — handles payment routing |
| Core banking software | BankCore GmbH (Frankfurt) — on-premise, deployed 2019 |
| DORA readiness | ~40% — governance exists on paper; risk register is 2 years old; no TLPT ever conducted; third-party contracts predate DORA |

---

## How the Day Works

| Block | What Happens |
|---|---|
| **Morning** | Batch 1 — Foundation tasks (you work, instructor circulates) |
| **Mid-morning** | Instructor demo: reading a gap professionally |
| **Pre-lunch** | Scenario drop — the afternoon changes |
| **Lunch** | — |
| **Post-lunch** | Instructor demo: classifying an incident under pressure |
| **Afternoon** | Batch 2 — Scenario-based tasks |
| **End of day** | Instructor walkthrough: one thread, end to end |

You work individually or in a team of your choice. There are no deliverables to hand in. The point is the thinking, not the document.

---

# BATCH 1 — Foundation Tasks

*All three tasks are open at the same time. Choose your own order and pace.*

---

## Task 1 — Pillar Mapping

**Time:** ~30 min

Using only the NordPay profile, map all five DORA pillars against their current situation. For each pillar write:

- **(a)** What NordPay is probably already doing
- **(b)** What they are likely missing
- **(c)** Where the highest-risk gap sits

**Format:** A five-row table. There is no single right answer — your reasoning is what matters.

> **If you have a technical background, also consider:** Which specific ICT system or vendor is most exposed in each pillar? Which provider creates the worst concentration risk, and why?

---

**Key question to discuss with your team:**
*If you had to tell NordPay's board which single pillar to address first, which would it be — and how would you justify that choice?*

---

## Task 2 — Gap Analysis

**Time:** ~45 min

Conduct a structured DORA gap analysis for NordPay. Select **any two pillars**. For each gap you identify, complete the following table:

| Current State | Required State | Gap Severity (H / M / L) | Proportionality Applicable? | Recommended First Action |
|---|---|---|---|---|

> **If you have a technical background, also consider:** Which systems, configurations, or integrations need to change to close each gap? Name them specifically using the NordPay profile.

---

**Key question to discuss with your team:**
*Where did proportionality change your assessment? Would a smaller entity have the same gap — or a different one entirely?*

---

**A note on how to read a gap:**

There is a difference between a surface gap and a meaningful gap.

| Surface Gap | Meaningful Gap |
|---|---|
| "NordPay needs to update their risk register." | "NordPay's outdated risk register means DataSwift's single-point-of-failure status is invisible to their board. They cannot manage a risk they cannot see." |

A meaningful gap tells you what the missing piece *prevents* — and that is what drives prioritisation.

---

## Task 3 — Risk Register

**Time:** ~45 min

Build a risk register for NordPay covering **at least six ICT risks**. For each risk include:

| Risk | Category | Likelihood (1–5) | Impact (1–5) | Current Controls | Owner | Priority |
|---|---|---|---|---|---|---|

**Categories:** Cyber / Infrastructure / Third-Party / Operational

> **If you have a technical background, also consider:** For at least two risks, identify the specific technical vulnerability that makes the risk real — for example: an unpatched dependency in BankCore GmbH, the absence of MFA on the DataSwift API, or no secondary cloud provider for failover.

---

**Key question to discuss with your team:**
*If you could only fix three risks before the regulator arrives next month, which three would you choose — and in what order?*

---

# SCENARIO DROP

*This will be revealed by the instructor before lunch. Do not read ahead.*

---

> **14:07 — Message from NordPay's CTO:**
>
> *"Hi — we have a situation. DataSwift has been unreachable since approximately 11:30. Payment routing has been down for close to three hours. We have also just found what looks like anomalous API key activity in our logs going back to last night. We don't know if this is a breach or a misconfiguration on their side. The COO is asking whether we need to notify anyone. What do we do?"*

---

# BATCH 2 — Scenario-Based Tasks

*Continue in your team from the morning. The Stretch Task is available for fast-finishing groups.*

---

## Task 4 — Incident Classification & Regulatory Reporting

**Time:** ~40 min

Based on the DataSwift incident, complete the following:

**Part A — Classification**

Apply DORA's three classification criteria to the scenario. Is this a **major ICT-related incident**? Use the table below:

| Criterion | What We Know | What We Don't Know Yet | Preliminary Assessment |
|---|---|---|---|
| Confidentiality / Integrity / Availability / Authenticity | | | |
| Criticality of affected services | | | |
| Economic impact | | | |

State your classification decision and justify it.

**Part B — Initial Notification**

Draft the initial notification to NordPay's competent authority (De Nederlandsche Bank). You do not have all the facts yet. Write what you can, flag what you do not know, and explain why you are notifying now rather than waiting.

Your notification should include:
- Description of the incident (what is known)
- Services and functions affected
- Actions taken so far
- What remains unknown and under investigation
- Point of contact for follow-up

**Part C — Information Map**

List what additional information is needed for the **intermediate** and **final reports**, and identify which internal NordPay role is responsible for providing each piece.

> **If you have a technical background, also consider:** What forensic steps should NordPay's ICT team take in the first two hours? How do those steps directly feed the regulatory report — which logs, timestamps, and artefacts are essential?

---

**Key question to discuss with your team:**
*Who inside NordPay makes the call to notify the competent authority — and who approves that decision? Look at the RACI you built in Task 6.*

---

## Task 5 — Third-Party Contract Evaluation

**Time:** ~45 min

NordPay shares their existing contract with DataSwift. It is a standard SaaS agreement from 2021.

**What it contains:** standard liability caps, 30-day termination notice, GDPR data processing clauses, 99.5% uptime SLA.

**What it does not contain:** audit rights, incident notification timeline, subcontracting disclosure, data location requirements, exit and transition plan, security standards obligation, business continuity obligations.

**Part A — Missing elements**

List every mandatory element missing under **Article 30 of DORA**. For each, note the risk it creates for NordPay.

| Missing Element | DORA Basis | Risk to NordPay |
|---|---|---|

**Part B — Draft clauses**

Draft the **three most critical missing clauses** in plain professional language — as you would write them for NordPay's legal team to insert into the renegotiated contract.

**Part C — Concentration risk**

Is DataSwift a **Type 1** or **Type 2** concentration risk for NordPay? What is NordPay's current fallback — and is it adequate?

| Concentration Risk Type | Definition | NordPay's Situation |
|---|---|---|
| Type 1 | One provider delivering multiple critical services to the same entity | |
| Type 2 | Many institutions relying on the same ICT provider | |

> **If you have a technical background, also consider:** DataSwift's website lists an ISO 27001 certificate last audited 18 months ago. Is this sufficient evidence of compliance with DORA's security standards? What additional assurance would you recommend NordPay require?

---

**Key question to discuss with your team:**
*If NordPay wanted to terminate DataSwift today — given what the contract actually says — what would happen?*

---

## Task 6 — Governance RACI

**Time:** ~35 min

NordPay's management body has never formally assigned DORA responsibilities. Design a RACI matrix for the following six controls:

1. ICT risk register maintenance
2. Incident classification and escalation
3. Third-party contract oversight
4. TLPT scheduling and remediation
5. Business continuity plan approval
6. Information sharing participation

Map each control across four roles using **R / A / C / I**:

| Control | Board | CTO | Compliance Officer | ICT Operations |
|---|---|---|---|---|
| ICT risk register maintenance | | | | |
| Incident classification and escalation | | | | |
| Third-party contract oversight | | | | |
| TLPT scheduling and remediation | | | | |
| Business continuity plan approval | | | | |
| Information sharing participation | | | | |

**Then answer:** Are there any controls where no one is currently **Accountable** at NordPay, given their profile? What is the organisational risk of that vacancy — and what happened today as a result?

---

**Key question to discuss with your team:**
*When the CTO sent the 14:07 message, who should have received it first — and why wasn't that in the contract?*

---

## STRETCH Task 7 — Information Sharing Arrangement

**Time:** ~25 min | *For fast-finishing groups*

Following today's incident, NordPay wants to join a pan-EU financial sector ISAC (Information Sharing and Analysis Centre).

**Part A — What to share**

From the DataSwift incident, what types of intelligence would NordPay share with the ISAC? What would they withhold, and why?

| Share | Withhold | Reason for Withholding |
|---|---|---|

**Part B — Formal arrangement elements**

What formal elements must the participation arrangement include under **Article 45 of DORA**?

**Part C — Notification to the competent authority**

When NordPay joins the ISAC, what must they notify DNB — and what does that notification need to contain?

**Part D — Sharing without exposure**

How does the DataSwift incident become valuable intelligence for the wider financial sector without exposing NordPay to legal or reputational risk? What anonymisation and protocol decisions matter?

---

**Key question to discuss with your team:**
*If every payment institution in the EU had shared intelligence about DataSwift-type API vulnerabilities six months ago, would today's incident have happened — or would NordPay have seen it coming?*

---

# Reference

## DORA's Five Pillars

| Pillar | Core Obligation |
|---|---|
| **1 — ICT Risk Management** | Documented, board-approved framework covering identification, protection, detection, response, and recovery |
| **2 — Incident Management** | Formal classification criteria, incident register, multi-stage regulatory reporting (initial / intermediate / final) |
| **3 — Digital Resilience Testing** | Regular vulnerability testing; TLPT every 3 years for critical entities; results feed remediation |
| **4 — Third-Party Risk Management** | Provider register, Article 30-compliant contracts, concentration risk management, exit strategies |
| **5 — Information Sharing** | Voluntary ISAC participation; secure, GDPR-compliant arrangements; notification to competent authority |

## DORA Incident Classification Criteria

| Criterion | Key Questions |
|---|---|
| **Confidentiality / Integrity / Availability / Authenticity** | Has any of these been compromised or suspected? |
| **Criticality of affected services** | Is a critical or important function impaired? |
| **Economic impact** | Does the scope of disruption exceed the entity's material impact threshold? |

A **major ICT-related incident** requires all three criteria to indicate significant adverse impact. Notify the competent authority immediately upon classification — do not wait for certainty.

## Article 30 — Mandatory Contract Elements (ICT Third Parties)

- Access and audit rights
- Service Level Agreements with enforcement mechanisms
- Security standards obligations
- Incident notification timelines
- Subcontracting disclosure and approval
- Data location and residency requirements
- Exit strategy and transition plan
- Business continuity obligations

## Proportionality Reminder

DORA obligations scale with entity size and complexity. A ~450-person payment institution like NordPay has real DORA obligations — but the *depth* of implementation may differ from a systemically important bank. The obligation to have a risk register, incident classification process, and DORA-compliant contracts applies regardless of size. The *sophistication* of those instruments scales with risk exposure.
