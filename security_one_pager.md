# Security One‑Pager

**Author:** Zhang Lixin  
**Purpose:** Provide a concise overview of how the risk‑monitoring rule pack is designed, delivered and operated to satisfy U.S. banking information‑security and privacy expectations (OCC 12 CFR Part 30 App. B, FFIEC BSA/AML Manual) without introducing new risks to the bank.

## Scope & Data Handling

- **Environment Isolation.** All pilots run on **test or de‑identified snapshots** provided by the bank; no production systems or customer Personally Identifiable Information (PII) are accessed.  
- **Data Minimisation.** Rule cards and sample scripts define a **minimal set of fields** needed to detect anomalies (e.g., loan amount, transaction amount, merchant category).  Fields such as customer names or complete account numbers are not required.  
- **De‑Identification.** All sample datasets shipped with the toolkit are synthetic and contain no real customer data. When the bank provides test data, any direct identifiers (e.g., name, SSN, full account number) must be removed or tokenised before analysis.

## Access Control

- **Read‑Only Principle.** Pilot deployments use **read‑only** database credentials.  Neither code nor personnel will perform updates, deletes or inserts on the bank’s systems.  
- **Least Privilege.** Only those at the bank who need access to the scripts and output for review will be granted access.  No third parties will receive database credentials or data extracts.  
- **Segregation of Duties.** Any tuning or configuration changes must be reviewed by both the bank’s risk/IT team and Zhang Lixin before deployment.

## Encryption & Transmission

- **In‑Transit.** All data exchanges with the bank (e.g., log files, result summaries) occur over TLS‑encrypted channels such as SFTP or the bank’s secure file portal.  
- **At‑Rest.** Any temporary storage used by Zhang Lixin to analyse test data (e.g., laptops, cloud instances) employs full‑disk encryption and strong access controls.  Data is destroyed within 15 days of project completion.

## Logging & Auditability

- **Structured Logs.** Each script writes a log entry including `rule_id`, `run_id`, `input_hash`, timestamp (`created_at`) and summary counts of alerts.  These logs enable the bank to verify when and how rules were executed.  
- **Change Management.** All SQL files and documentation are versioned with semantic version numbers.  Any changes are tracked in a changelog and are subject to the bank’s internal model governance process.

## Vulnerability & Incident Management

- **Secure Coding.** Scripts avoid dynamic SQL injection or external code execution.  They use parameterised queries where applicable.  
- **Patch Management.** Should a vulnerability be discovered in a script, Zhang Lixin will provide an updated version within five business days of notification.  
- **Incident Response.** In the unlikely event of a security incident, Zhang Lixin will notify the designated bank contact within 24 hours and cooperate fully with the bank’s incident response procedures.

## Compliance Alignment

- **Regulatory References.** The approach aligns with the OCC’s guidance on safeguarding customer information (12 CFR Part 30 App. B) and the **Model Risk Management guidance** (SR 11‑7/OCC 2011‑12).  
- **AML & BSA support.** Rules that detect unusual fund flows (e.g., loan funds going to prohibited sectors) are designed to supplement the bank’s existing BSA/AML monitoring framework and do not replace mandated suspicious activity monitoring.  
- **International Data Restrictions.** All data stays within the jurisdiction chosen by the bank.  No data is transferred across borders without prior written consent.

## Contact & Support

All questions about security, privacy or compliance should be directed to **Zhang Lixin** at `rosiezhang1218@gmail.com`.  Additional documentation such as detailed security policies or technical architecture diagrams can be provided under a mutual nondisclosure agreement (NDA).