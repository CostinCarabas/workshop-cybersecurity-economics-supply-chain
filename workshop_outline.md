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
| **Mid-morning** | Debate: reading a gap |
| **Pre-lunch** | Scenario drop — the afternoon changes |
| **Lunch** | — |
| **Post-lunch** | Debate: classifying an incident under pressure |
| **Afternoon** | Batch 2 — Scenario-based tasks |
| **End of day** | Discussions |

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
