---
title: "Third‑Party Due‑Diligence Questionnaire"
author: Zhang Lixin
last_updated: 2025‑08‑22
version: 1.0
---

# Third‑Party Due‑Diligence Q&A

This document provides a concise set of questions and answers to support banks and credit unions in performing due‑diligence on the Risk Monitoring Rule Pack developed by Zhang Lixin.  It is aligned with the **2023 Interagency Guidance on Third‑Party Relationships: Risk Management** issued by the OCC, FDIC and the Federal Reserve, which outlines a risk management life‑cycle of planning, due diligence, contract negotiation, ongoing monitoring and termination【725454682347634†L37-L47】【725454682347634†L92-L97】.  The answers below are designed to help institutions evaluate the security, compliance and operational readiness of the rule pack for a test or pilot deployment.

## 1 Planning

**Q1: What problems does the rule pack solve?**  
The rule pack contains ANSI‑SQL‑based monitoring rules that detect anomalies across consumer and small‑business lending, such as loan proceeds entering prohibited industries, abnormal collateral depreciation, repeated disbursements to the same payee, and suspicious employee–vendor transactions.  These rules complement existing AML/transaction monitoring systems by covering loan usage, collateral and internal‑fraud patterns often overlooked by standard packages.  The goal is to enhance risk coverage while minimising implementation cost and false positives.

**Q2: How does the offering fit our strategic objectives?**  
The rule pack supports regulatory priorities around BSA/AML, consumer protection, fair lending and small‑business credit by adding specific controls that improve anomaly detection and reduce manual review burden.  It is designed for community and mid‑size banks that need lightweight, explainable rules aligned with OCC SR 11‑7 governance expectations【725454682347634†L37-L47】.

## 2 Due Diligence

**Q3: What is the vendor’s background and expertise?**  
Zhang Lixin is a certified Financial Risk Manager (FRM) and Certified Internal Auditor (CIA) with over 18 years of risk‑management experience at a global systemically important bank.  She has built a library of 300 + monitoring rules and has participated in international data‑science competitions (Kaggle silver medal).  The rule pack is derived from practical experience in loan monitoring, AML and operational risk, abstracted into generic SQL logic.

**Q4: How is data handled?**  
Only de‑identified or synthetic data is used for testing.  The pilot does not access production systems or personally identifiable information (PII).  The bank runs scripts on their own test or anonymised datasets.  Data never leaves the bank’s environment.  All scripts are read‑only and do not perform updates.

**Q5: What technical environments are supported?**  
The rules are delivered as plain SQL scripts and YAML/CSV mapping templates.  They can run on any relational database platform (e.g., Oracle, SQL Server, MySQL/PostgreSQL, DB2, Snowflake) that supports ANSI‑SQL and basic window functions.  For banks without internal SQL capability, the developer can process data offline and return only aggregate alerts.

**Q6: How is security managed?**  
The solution follows a defence‑in‑depth approach detailed in the [Security One‑Pager](security_one_pager.md).  All code is reviewed for injection risks, variables are parameterised, and scripts include strict input filtering.  Access to scripts and logs is controlled via role‑based access controls.  Audit fields (rule_id, run_id, input_hash, created_at, created_by) are embedded in outputs.

**Q7: Does the vendor comply with relevant laws and regulations?**  
Yes.  The rule pack is designed to support compliance with the Bank Secrecy Act (BSA), Anti‑Money Laundering (AML) regulations, the OCC’s Model Risk Management guidance (SR 11‑7) and the 2023 Interagency Third‑Party Risk Management guidance.  It does not relieve the bank of its statutory obligations but provides tools to help meet them.

## 3 Contract Negotiation

**Q8: What licensing model is proposed?**  
The pilot is offered under an evaluation licence, permitting use of the rules solely for internal testing and validation.  The bank may not redistribute or commercialise the scripts.  Post‑pilot, the parties may negotiate a subscription or perpetual licence with optional maintenance services.

**Q9: What are the confidentiality provisions?**  
All data, logs and outcomes generated during the pilot remain the property of the bank and are confidential.  The developer will sign a non‑disclosure agreement (NDA).  The developer will not retain any bank data after the pilot concludes.

**Q10: Who owns the intellectual property?**  
The underlying rule logic and code remain the sole property of Zhang Lixin.  The bank receives a non‑exclusive, non‑transferable licence to use the rules in accordance with the agreed scope.

## 4 Ongoing Monitoring

**Q11: How will performance be measured?**  
Key performance indicators include detection lift (additional valid alerts vs. baseline), false‑positive reduction rate, time‑to‑first‑alert and audit readiness (completeness of documentation, rule cards and change logs).  Weekly progress reports and summary dashboards are included.  SLA details are described in the PoC Statement of Work.

**Q12: How are updates and patches managed?**  
Each rule has a semantic version identifier.  The bank receives release notes, a changelog, and a regression test kit.  Minor updates (e.g., threshold adjustments) are provided quarterly.  Critical security fixes are delivered within five business days.  Updates are backward compatible unless major changes are agreed.

**Q13: What support channels are available?**  
Support is provided via email and scheduled video calls.  Response time is one business day for questions; bug fixes are typically delivered within five business days.  Urgent security issues are escalated immediately.

## 5 Termination & Exit

**Q14: How does the pilot end?**  
At the conclusion of the agreed 30‑day pilot, the bank will receive a debrief report and may, at its sole discretion, choose to discontinue or extend the relationship.  If discontinuing, the bank will destroy all copies of the scripts and confirm deletion in writing.  The developer will likewise destroy all materials related to the bank’s data.

**Q15: What happens if either party wants to exit early?**  
Either party may terminate the pilot with seven days’ written notice.  Upon early termination, both parties will destroy any exchanged data and confirm in writing.  There are no fees for early termination.

**Q16: Does the solution provide continuity in case of vendor incapacity?**  
The delivered scripts are self‑contained and can continue running without vendor involvement.  At the bank’s request, the developer will provide source code escrow or training to ensure continuity.  The documentation allows internal teams to maintain and tune the rules independently.

---

For further information or to request additional due‑diligence documentation, please contact **Zhang Lixin** at `rosiezhang1218@gmail.com`.