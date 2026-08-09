# Business Requirements Document (BRD)
## OrthoApp — Digital Operations & Family Engagement Platform for OrthoAssist HomeCare Services

| | |
|---|---|
| **Document owner** | OrthoAssist HomeCare Services |
| **Version** | 1.0 (Draft) |
| **Date** | 2026-08-08 |
| **Source of record** | `OrthoApp.docx` (service charter / brochure) |
| **Status** | For business review |

---

## 1. Executive Summary

OrthoAssist HomeCare Services delivers doctor-supervised, in-home caretaking and safe hospital escort for orthopedic patients — the bedridden, the post-surgical, the elderly, and anyone whose mobility has been changed by injury or disease. The service already promises families that *"daily progress reports are shared through our app."*

**OrthoApp** is that platform. It is the digital backbone that runs the business end-to-end: it captures leads, turns them into doctor-designed care plans, matches and schedules verified caretakers and escorts, records every act of care at the bedside, and keeps families continuously informed with the transparency the brand promises. It also enforces the safety, compliance, and dignity standards the brochure commits to — the 2-hour repositioning protocol, the <30-minute emergency response, HIPAA-aligned confidentiality, and NABH-aligned quality.

This BRD defines *what the business needs the platform to do and why*. It is deliberately solution-agnostic on technology; implementation detail belongs in a downstream TRD.

---

## 2. Business Context & Problem Statement

Families caring for orthopedic patients face two gaps the brochure identifies explicitly:

1. **A clinical-skill gap at home** — safe transfers, pressure-sore prevention, wound care, and complication detection are trained skills, not skills that "love can substitute for."
2. **A continuity gap between hospital and home** — appointments are missed, discharge instructions are lost, and unaccompanied travel is unsafe for immobile patients.

OrthoAssist closes these gaps with people. Today those people coordinate over phone calls, paper notes, and WhatsApp — which does not scale, does not create an auditable record of care, and does not give families a single trustworthy view of their loved one's recovery.

**The problem OrthoApp solves:** operating a distributed, clinically-supervised, dignity-first care service *reliably and transparently at scale*, while proving that every safety and quality promise was actually kept.

---

## 3. Business Objectives & Success Metrics

| # | Objective | Success metric (KPI) |
|---|-----------|----------------------|
| O1 | Never miss an appointment or escort | 0 missed scheduled visits/escorts per month |
| O2 | Meet the emergency-response promise | ≥95% of emergency escalations acknowledged in <30 min |
| O3 | Prevent immobility complications | 100% adherence to 2-hour repositioning logs; bed-sore incidence trending to zero |
| O4 | Keep families continuously informed | Daily report delivered every service day; family app engagement ≥ X% |
| O5 | Prove quality & compliance | 100% of active staff with valid, unexpired certifications and clearances |
| O6 | Convert enquiries into care | Lead → active-patient conversion rate; time from enquiry to care start |
| O7 | Sustain trust | Post-visit feedback captured after every visit; CSAT ≥ target |
| O8 | Transparent revenue | 100% of services billed with GST invoice; zero billing disputes from "hidden charges" |

*(X and target values to be set by the business during review.)*

---

## 4. Scope

### 4.1 In Scope (v1)
- Lead capture, free home-assessment scheduling, and patient onboarding
- Doctor-authored, per-patient **care plans**
- Staff registry with **certification & background-verification tracking**
- Team **matching, assignment, and shift scheduling**
- **Bedside care logging**: vitals, repositioning, wound/medication/physio/nutrition tasks
- **Hospital escort management** (home→hospital, hospital→home) with visit documentation
- **Family portal**: daily reports, care team, schedule, care-plan progress, messaging, billing
- **Safety & incident management**: emergency escalation, alerts for overdue safety tasks
- **Service packages, subscriptions, GST billing, and in-app payment collection** with discounts and payment plans
- **Offline field capability**: caretakers/escorts can log care without connectivity; syncs when back online
- **Feedback capture** after every visit
- **Periodic review** workflow (weekly supervisor, monthly physician)

### 4.2 Out of Scope (v1)
- Direct integration with hospital EMR/HIS systems
- Live turn-by-turn navigation for escort vehicles (GPS *tracking* is in scope; routing is not)
- Insurance claim adjudication (billing documentation support only)
- Public marketing website (the brochure itself)

### 4.3 Assumptions
- OrthoAssist retains the panel of surgeons, physiotherapists, nurses, and escorts described in the charter.
- Patients/families have a smartphone or a family member who does (WhatsApp fallback supported).
- **Launch market is Hyderabad** (currency INR; GST applicable; NABH guidelines and Indian Nursing Council norms apply). Escort logistics, GPS coverage, and hospital coverage are scoped to Hyderabad for v1.
- **Languages at launch: English, Telugu, and Hindi** — the app and family communications support all three.

### 4.4 Constraints
- Patient data is sensitive health data → confidentiality is a hard requirement, not a feature.
- Care must remain **doctor-supervised**; the platform cannot let unsupervised care plans go live.
- **No-substitution policy**: staff cannot be swapped without prior recorded family consent.

---

## 5. Stakeholders & User Personas

| Persona | Role in the business | Primary needs from OrthoApp |
|---------|---------------------|------------------------------|
| **Patient** | The person recovering | Dignity, consent, comfort; a voice in their own care |
| **Family member / decision-maker** | Pays, worries, decides | One trustworthy view of the patient's day; reassurance; transparent cost |
| **Care Coordinator (Head Caretaker)** | Runs day-to-day operations | Assign teams, build schedules, watch alerts, resolve issues |
| **Supervising Orthopedic Surgeon** | Clinical authority | Author/approve care plans; monthly review; sign off protocols |
| **Registered Physiotherapist** | Mobility program owner | Plan and track home exercise regimens |
| **Trained Orthopedic Caretaker** | Delivers bedside care | Simple task list + logging at the bedside; escalate fast |
| **Patient Escort Associate** | Safe hospital transport | Escort itinerary, checklists, visit notes, GPS check-in |
| **Home Nurse / Nutritionist** | Add-on clinical services | Record clinical acts and diet plans |
| **Operations / Admin** | Business owner | Compliance, billing, staffing, KPIs |

---

## 6. Business Requirements

Requirements are grouped by capability. Each is a *business* requirement (the "what/why"), not a technical spec.

### 6.1 Intake & Onboarding
- **BR-1.1** The platform shall capture enquiries from an online form and a helpline, recording patient condition, location, and care needs.
- **BR-1.2** The platform shall schedule a **free home-assessment visit** and assign a coordinator to conduct it.
- **BR-1.3** The platform shall onboard a patient with their profile, condition category, home environment notes, and uploaded medical records/prescriptions.
- **BR-1.4** The platform shall record patient/family consent before any care begins.

### 6.2 Care Planning (Doctor-Supervised)
- **BR-2.1** A supervising physician shall author a **personalized care plan** specifying caretaker duties, physiotherapy schedule, diet requirements, and escort needs.
- **BR-2.2** A care plan shall not become active until reviewed/approved by a supervising physician (enforces "doctor-supervised" promise).
- **BR-2.3** The platform shall support **monthly physician review** and versioned adjustments as the patient recovers, including planned transition to independence/discharge.

### 6.3 Staffing, Certification & Trust
- **BR-3.1** The platform shall maintain a staff registry with role, qualifications, and assigned patients.
- **BR-3.2** Each staff record shall track **mandatory credentials**: criminal background/police clearance, medical fitness, ≥120-hr orthopedic handling certification, BLS & First Aid, and dignity/confidentiality training.
- **BR-3.3** The platform shall flag and prevent assignment of staff with **missing or expired** credentials.
- **BR-3.4** The platform shall record periodic refresher training and supervised performance evaluations.

### 6.4 Matching, Assignment & Scheduling
- **BR-4.1** The platform shall assign a **matched, background-verified** care team to each patient and brief them on the care plan, history, family preferences, and emergency protocols.
- **BR-4.2** The platform shall build and display caretaker shift schedules per the package (8h / 12h / 24h) and escort appointments.
- **BR-4.3** The platform shall enforce the **no-substitution policy**: a staff change requires recorded prior family consent.

### 6.5 Bedside Care Delivery & Logging
- **BR-5.1** Caretakers shall log **vitals and condition changes** with timestamps.
- **BR-5.2** The platform shall enforce and log a **2-hour repositioning protocol** for pressure-ulcer prevention, alerting when a reposition is overdue.
- **BR-5.3** The platform shall track scheduled tasks for wound/post-surgical care, **medication administration** (with reminders), physiotherapy assistance, personal hygiene, nutrition/feeding, and medical-equipment operation.
- **BR-5.4** The platform shall support a **fall-prevention** checklist and record incidents.
- **BR-5.5** Caretakers and escorts shall be able to **log care while offline** in low-connectivity homes; entries are stored on-device and **synced automatically** when connectivity returns, without data loss and with original timestamps preserved.

### 6.6 Hospital Escort & Transport
- **BR-6.1** The platform shall schedule and manage **home→hospital** and **hospital→home** escort journeys, each as a checklist-driven itinerary (dress/ready, transfer, accompany, registration/triage, consultation note-taking, diagnostics, pharmacy, discharge handover).
- **BR-6.2** Escort vehicles/journeys shall be **GPS check-in/tracked** for patient security.
- **BR-6.3** The escort shall capture **visit documentation** (doctor's instructions, follow-up, medication changes) and hand it back into the patient's home-care record for continuity.

### 6.7 Family Engagement & Transparency
- **BR-7.1** The platform shall deliver a **daily progress report** to the family via the app, with WhatsApp fallback.
- **BR-7.2** Families shall see the current **care team**, **schedule**, **care-plan progress**, and **upcoming escorts** at a glance.
- **BR-7.3** The platform shall provide a **messaging channel** between family and the care team/coordinator.
- **BR-7.4** The platform shall capture **feedback after every visit**.

### 6.8 Safety, Emergency & Incident Management
- **BR-8.1** The platform shall provide a **24×7 emergency escalation** path targeting <30-minute acknowledgement, with escalation tracking.
- **BR-8.2** The platform shall raise **alerts** for overdue safety-critical tasks (e.g., repositioning, medication) and unacknowledged escalations.
- **BR-8.3** The platform shall record incidents (falls, complications, equipment failure) and their resolution.

### 6.9 Packages, Billing & Payments
- **BR-9.1** The platform shall offer the four standard packages — **Basic / Standard / Comprehensive / Premium 360** — plus custom (short-term post-op, weekend-only, escort-only).
- **BR-9.2** The platform shall generate **GST invoices** for all services and provide written cost estimates *before* service begins ("no hidden charges").
- **BR-9.3** The platform shall apply discounts: **10% senior-citizen** and **referral** discounts, and support **flexible interest-free monthly plans**.
- **BR-9.4** The platform shall assist with documentation families need for **insurance reimbursement**.
- **BR-9.5** The platform shall support **in-app payment collection** — families can pay invoices and package fees within the app (India payment methods: UPI, cards, net-banking) — with receipts issued and payment status reflected on the invoice.

### 6.10 Quality, Review & Reporting (Operations)
- **BR-10.1** The platform shall support **weekly supervisor spot-visits** and quality assessments.
- **BR-10.2** The platform shall report operational KPIs (Section 3) to Operations.
- **BR-10.3** The platform shall maintain an **auditable record** of every care act, escalation, and staff assignment.

---

## 7. Key Business Process Flows

**7.1 Enquiry → Active Care**
Enquiry (form/helpline) → Free home assessment → Physician care-plan design → Physician approval → Team match & brief → Care delivery begins.

**7.2 A Service Day**
Caretaker on shift → logs vitals, repositioning, meds, physio, hygiene, nutrition → coordinator monitors alerts → daily report auto-compiled → sent to family → family feedback.

**7.3 Hospital Escort**
Escort scheduled → home pickup checklist → GPS-tracked transfer → accompany through hospital (notes, diagnostics, pharmacy) → return & settle at home → instructions handed to family → visit documented into care record.

**7.4 Recovery Review**
Weekly supervisor visit + monthly physician review → care plan adjusted/versioned → eventual transition to independence / discharge.

---

## 8. Non-Functional / Cross-Cutting Requirements

| Category | Requirement |
|----------|-------------|
| **Confidentiality** | HIPAA-aligned handling of patient health data; strict access by role; full audit trail. |
| **Compliance** | NABH-guideline aligned; Indian Nursing Council norms; GST-compliant invoicing. |
| **Availability** | 24×7 for emergency and escalation paths. |
| **Reliability** | Safety-task alerts and daily reports must not silently fail. |
| **Offline-first (field)** | Caretaker/escort logging works without connectivity and syncs on reconnect with no data loss and preserved timestamps (BR-5.5). |
| **Payments** | PCI-aware in-app payments via India methods (UPI, cards, net-banking); no raw card data stored by OrthoApp (BR-9.5). |
| **Usability** | Bedside/escort interfaces usable by non-technical field staff; family interface usable by anxious, non-technical relatives, including seniors. |
| **Localization** | Full app + family communications in **English, Telugu, and Hindi** at launch; large-type, high-contrast, simple language. |
| **Traceability** | Every care act, consent, escalation, and staff change is timestamped and attributable. |
| **Dignity by design** | Consent prompts and privacy protections are built into care-logging flows, not optional. |

---

## 9. Risks & Mitigations

| Risk | Impact | Mitigation |
|------|--------|-----------|
| Field staff skip logging at the bedside | Broken care record; unmet safety promise | Frictionless mobile logging + overdue alerts + supervisor spot-checks |
| Expired credential slips through | Compliance & safety breach | Hard block on assignment; automated expiry alerts (BR-3.3) |
| Emergency escalation missed | Patient harm; brand damage | 24×7 path + <30-min SLA tracking + auto-re-escalation (BR-8.1/8.2) |
| Patient health data exposure | Legal/ethical breach | Role-based access, audit trail, confidentiality controls (Section 8) |
| Family distrust from opaque billing | Churn | Estimate-before-service + GST invoices + no-substitution consent (BR-9.2, BR-4.3) |
| Low digital literacy of users | Non-adoption | WhatsApp fallback, accessible UI, coordinator-mediated onboarding |

---

## 10. Decisions Resolved (v1)
*(These were open questions in the draft; resolved with the business on 2026-08-08.)*

| # | Decision | Impact |
|---|----------|--------|
| D1 | **KPI set (Section 3) is accepted as the v1 starting set.** Numeric targets to be calibrated against the first baseline of live data. | KPIs are locked; thresholds tuned post-launch. |
| D2 | **In-app payment collection is IN scope for v1** (UPI, cards, net-banking). | Added BR-9.5; Payments NFR added; removed from Out of Scope. |
| D3 | **Launch market is Hyderabad.** | Escort logistics, GPS, and hospital coverage scoped to Hyderabad (§4.3). |
| D4 | **Launch languages: English, Telugu, Hindi.** | Localization NFR; all family-facing comms in three languages (§4.3, §8). |
| D5 | **Offline field capability is mandatory.** | Added BR-5.5 and Offline-first NFR. |

### Remaining to confirm
- Numeric KPI thresholds (D1) once a baseline exists.
- Preferred India payment provider/gateway for D2 (a TRD-level choice, but note any commercial preference).

---

## 11. Glossary
- **NABH** — National Accreditation Board for Hospitals & Healthcare Providers (India).
- **BLS** — Basic Life Support.
- **THR / TKR** — Total Hip / Knee Replacement.
- **DVT** — Deep Vein Thrombosis.
- **Repositioning protocol** — scheduled 2-hourly patient turning to prevent pressure ulcers.
- **No-substitution policy** — staff cannot be changed without prior recorded family consent.

---

*Derived from the OrthoAssist HomeCare service charter (`OrthoApp.docx`). This BRD captures business requirements only; technical design is deferred to a TRD.*
