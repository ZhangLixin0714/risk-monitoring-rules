---
title: "Evaluation Licence & PoC Statement of Work"
author: Zhang Lixin
last_updated: 2025‑08‑22
version: 1.0
---

# Evaluation Licence & PoC Statement of Work (PoC SoW)

This document sets out the terms under which **Zhang Lixin** grants a limited evaluation licence for the Risk Monitoring Rule Pack and defines the scope of a 30‑day proof‑of‑concept (PoC) engagement.  By accepting the Evaluation Licence and initiating the PoC, the bank agrees to the terms herein.  These provisions align with the 2023 Interagency Third‑Party Risk Management guidance, SR 11‑7 model governance expectations, and GLBA information security requirements【725454682347634†L37-L47】【725454682347634†L92-L97】.

## 1 Evaluation Licence

1. **Grant of Licence**.  Zhang Lixin grants the bank a non‑exclusive, non‑transferable, royalty‑free licence to use the supplied SQL scripts, mapping templates, sample data and documentation (collectively, “Licensed Materials”) solely for internal evaluation in a non‑production environment during the PoC period.

2. **Restrictions**.  The bank shall not modify, reverse engineer, sell, sublicense, distribute or commercially exploit the Licensed Materials.  The bank shall use the Licensed Materials only in accordance with this Agreement and applicable law.

3. **Confidentiality**.  The bank shall treat the Licensed Materials as confidential.  Zhang Lixin shall treat all data and information provided by the bank as confidential.  Both parties agree to protect the other’s confidential information using at least the same degree of care as they use to protect their own.

4. **Ownership**.  Zhang Lixin retains all right, title and interest in the Licensed Materials.  No transfer of intellectual‑property rights is made, except for the limited rights expressly granted herein.

5. **Term & Termination**.  This licence commences on the Effective Date and expires at the earlier of (i) 30 calendar days or (ii) termination of the PoC.  Either party may terminate the licence and PoC at any time with seven days’ written notice.  Upon termination, the bank shall delete all copies of the Licensed Materials and certify deletion.  Sections 3, 4, and 7 survive termination.

6. **Disclaimer**.  The Licensed Materials are provided “as is” for evaluation purposes.  Zhang Lixin makes no warranty as to accuracy, completeness or fitness for a particular purpose.  In no event shall either party be liable for indirect or consequential damages arising from use of the Licensed Materials.

7. **Governing Law**.  This Agreement is governed by the laws of the State of New Jersey, without regard to conflicts of law principles.

## 2 Proof‑of‑Concept Statement of Work

### 2.1 Objective
Demonstrate the efficacy, accuracy and governance alignment of selected monitoring rules in the bank’s environment using de‑identified or synthetic data.  The PoC will focus on three representative rules:
* **R01 – Loan Proceeds Flow to Prohibited Sectors** (e.g., loan funds used for gambling or speculative investments),
* **R02 – Collateral Depreciation > 20 %**, and
* **R03 – Business Loan Volume Spike** (unusual transaction spikes in small‑business accounts).

### 2.2 Deliverables

1. **Rule Cards & Scripts** – Detailed rule cards outlining objectives, regulatory context, required input fields, logic (pseudocode + ANSI‑SQL), thresholds and expected output schema; parameterised SQL scripts incorporating audit fields (`rule_id`, `run_id`, `input_hash`, `created_at`).

2. **Field Mapping Template** – A CSV file listing generic field names with definitions to allow the bank to map its own core‑system fields.

3. **Sample Data & Expected Outputs** – Synthetic datasets representing typical loan and transaction scenarios for the bank to load into its test environment, with accompanying expected alert outputs.

4. **Weekly Progress Reports** – Summaries of activities, issues, detection metrics (true positives, false positives, detection lift), threshold tuning and next‑steps.

5. **Final PoC Report** – A consolidated report detailing detection performance, false‑positive reduction, key findings, governance compliance assessment and recommendations for production deployment.

### 2.3 Scope & Approach

1. **Week 1 – Field Mapping & Setup**.  The bank identifies core‑system fields and maps them to the generic schema using the provided template.  Scripts and sample data are loaded into a secure test environment.  Access is restricted to authorised personnel and audit logging is enabled.

2. **Week 2 – Rule Execution & Validation**.  The bank runs each rule on the mapped dataset and compares the outputs with expected results.  Thresholds may be adjusted to reflect the bank’s risk appetite.  Any discrepancies are jointly analysed.

3. **Weeks 3–4 – Pilot Monitoring & Analysis**.  The bank applies the rules to a rolling dataset of recent transactions/loans in the test environment.  Weekly metrics are collected on detection lift and false positives.  Findings are discussed in weekly calls.  Governance artefacts (rule cards, change logs, execution logs) are reviewed for completeness.

4. **PoC Closure**.  At the end of Week 4, Zhang Lixin delivers the final PoC report.  The bank decides whether to continue to a production implementation or discontinue.  All data and scripts are returned or destroyed as required.

### 2.4 Responsibilities

| Party | Responsibilities |
|---|---|
| **Bank** | Provide de‑identified/synthetic data and system access in a test environment; map fields to the generic schema; execute scripts; review alerts; provide feedback on false positives/negatives; ensure compliance with internal security policies. |
| **Zhang Lixin** | Deliver rule cards, scripts, mapping template, sample data and guidance; assist with field mapping and script tuning; provide weekly progress reports; document changes and issues; draft final PoC report; destroy or return all bank data post‑PoC. |

### 2.5 Assumptions & Constraints

1. The PoC uses only non‑production data.  No production credentials or PII are shared.  
2. The bank will allocate appropriate resources (data, IT and risk management staff) to complete the field mapping and rule execution.  
3. The evaluation is intended to demonstrate functional capability rather than ensure regulatory compliance; the bank remains solely responsible for regulatory reporting.  
4. All thresholds and tuning parameters are illustrative and will require calibration if deployed in production.  
5. The PoC outcomes are non‑binding; either party may discontinue without penalty.

### 2.6 Fees & Expenses

The evaluation licence and PoC are offered at no cost.  Should the bank wish to proceed beyond the PoC, licence and services fees will be negotiated separately.

## 3 Acceptance & Signature

By commencing the PoC or using the Licensed Materials, the bank acknowledges it has read, understood and agrees to the terms of this Evaluation Licence & PoC SoW.

\
**Bank’s Authorised Representative**\
Signature: ________________________  Date: ___________\
Name: _____________________________  Title: ___________\

**Zhang Lixin**\
Signature: ________________________  Date: ___________\

---

For questions about this Agreement or to request a customised PoC scope, please contact **Zhang Lixin** at `rosiezhang1218@gmail.com`.