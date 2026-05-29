# Compliance Framework Mapping
## Nexus Corp Security Operations Center
## Analyst: William | Case ID: COMP-2026-001

---

## Overview

Compliance frameworks define the minimum security controls
organisations must implement to protect data and systems.
A SOC analyst must understand these frameworks because:

- Every alert must be documented for compliance evidence
- Incident response procedures must meet framework requirements
- Detection rules must cover compliance-mandated log sources
- Security controls must be mapped and evidenced regularly

---

## Framework 1 — NIST Cybersecurity Framework (CSF)

**What it is:**
A voluntary framework developed by the US National Institute
of Standards and Technology. Widely adopted globally as a
best practice standard for cybersecurity risk management.

**Five Core Functions:**

```
IDENTIFY   — Understand your assets, risks, and environment
PROTECT    — Implement safeguards to limit attack impact
DETECT     — Develop capabilities to identify incidents
RESPOND    — Take action when incidents are detected
RECOVER    — Restore capabilities after an incident
```

**Nexus Corp Control Mapping:**

| NIST Function | NIST Control | Nexus Corp Implementation | Status |
|---|---|---|---|
| Identify | Asset Management | CMDB all assets inventoried | ✅ |
| Identify | Risk Assessment | Annual risk assessment completed | ✅ |
| Protect | Access Control | MFA + RBAC implemented | ✅ |
| Protect | Awareness Training | Annual security training mandatory | ✅ |
| Protect | Data Security | AES-256 encryption at rest and transit | ✅ |
| Detect | Anomalies & Events | Splunk SIEM 24/7 monitoring | ✅ |
| Detect | Security Monitoring | EDR on all endpoints | ✅ |
| Respond | Response Planning | IR playbooks documented | ✅ |
| Respond | Communications | Incident notification procedure | ✅ |
| Recover | Recovery Planning | BCP/DR plan documented | ⚠️ Not tested |
| Recover | Improvements | Post-incident reviews conducted | ✅ |

**NIST CSF Compliance Score: 10/11 (91%) ✅**

---

## Framework 2 — ISO 27001

**What it is:**
The international standard for Information Security Management
Systems (ISMS). Certification proves an organisation has
implemented systematic controls for managing sensitive data.

**Key Domains:**

```
A.5   — Information Security Policies
A.6   — Organisation of Information Security
A.7   — Human Resource Security
A.8   — Asset Management
A.9   — Access Control
A.10  — Cryptography
A.11  — Physical and Environmental Security
A.12  — Operations Security
A.13  — Communications Security
A.14  — System Acquisition, Development, Maintenance
A.16  — Information Security Incident Management
A.17  — Business Continuity Management
A.18  — Compliance
```

**Nexus Corp Control Mapping:**

| ISO Domain | Control | Nexus Corp Implementation | Status |
|---|---|---|---|
| A.5 | Information Security Policy | Policy documented and approved | ✅ |
| A.6 | Security Roles Defined | SOC team roles and responsibilities | ✅ |
| A.7 | Background Checks | Pre-employment screening | ✅ |
| A.8 | Asset Inventory | CMDB maintained | ✅ |
| A.9 | Access Control Policy | RBAC + MFA + least privilege | ✅ |
| A.10 | Encryption Policy | AES-256 + TLS 1.3 | ✅ |
| A.11 | Physical Security | Data centre access controls | ✅ |
| A.12 | Malware Controls | EDR deployed on all endpoints | ✅ |
| A.12 | Backup Policy | Daily backups immutable storage | ✅ |
| A.12 | Audit Logging | SIEM collects all logs | ✅ |
| A.13 | Network Segmentation | Micro-segmentation implemented | ✅ |
| A.16 | Incident Response | IR playbooks + SOC 24/7 | ✅ |
| A.16 | Incident Reporting | Regulatory notification procedure | ⚠️ Partial |
| A.17 | Business Continuity | BCP documented DR not tested | ⚠️ Gap |
| A.18 | Legal Compliance | GDPR + SOX compliance mapped | ✅ |

**ISO 27001 Compliance Score: 13/15 (87%) ⚠️**

---

## Framework 3 — SOC 2 (Type II)

**What it is:**
SOC 2 is an auditing standard for service organisations.
It evaluates controls across five Trust Service Criteria.
Type II means controls were tested over a period of time
(not just a point-in-time snapshot).

**Five Trust Service Criteria:**

```
Security       — System is protected against unauthorised access
Availability   — System is available for operation as agreed
Integrity      — System processing is complete, valid, accurate
Confidentiality — Information designated as confidential is protected
Privacy        — Personal information is collected and used correctly
```

**Nexus Corp Control Mapping:**

| SOC 2 Criteria | Control | Nexus Corp Implementation | Status |
|---|---|---|---|
| Security | Logical Access Controls | MFA + RBAC + PAM | ✅ |
| Security | Incident Response | SOC 24/7 + IR playbooks | ✅ |
| Security | Vulnerability Management | Monthly scans + patching SLA | ✅ |
| Security | Change Management | Change control process | ⚠️ Informal |
| Availability | System Monitoring | SIEM + uptime monitoring | ✅ |
| Availability | Backup & Recovery | Daily backups + DR plan | ⚠️ DR untested |
| Integrity | Input Validation | Application-level controls | ✅ |
| Integrity | Error Detection | Logging + alerting | ✅ |
| Confidentiality | Data Classification | 4-tier classification policy | ✅ |
| Confidentiality | Encryption | AES-256 at rest + TLS 1.3 | ✅ |
| Privacy | Data Retention | Retention policy documented | ✅ |
| Privacy | Data Subject Rights | GDPR process implemented | ✅ |

**SOC 2 Compliance Score: 10/12 (83%) ⚠️**

---

## Framework 4 — GDPR

**What it is:**
The General Data Protection Regulation EU law governing
how personal data of EU citizens must be collected, stored,
processed, and protected. Non-compliance fines: up to
€20 million or 4% of global annual turnover.

**Key GDPR Articles for SOC:**

```
Article 5  — Principles of data processing
Article 17 — Right to erasure (right to be forgotten)
Article 25 — Data protection by design and default
Article 32 — Security of processing encryption, pseudonymisation
Article 33 — Notification of data breach to authority (72 hours)
Article 34 — Communication of breach to data subjects
Article 35 — Data Protection Impact Assessment (DPIA)
```

**Nexus Corp GDPR Mapping:**

| Article | Requirement | Nexus Corp Implementation | Status |
|---|---|---|---|
| Art 5 | Lawful processing | Data processing register | ✅ |
| Art 17 | Right to erasure | Deletion workflow exists | ⚠️ Manual process |
| Art 25 | Privacy by design | Security built into SDLC | ⚠️ Partial |
| Art 32 | Encryption | AES-256 + TLS 1.3 | ✅ |
| Art 32 | Pseudonymisation | PII fields pseudonymised | ✅ |
| Art 33 | 72-hour breach notification | IR procedure includes notification | ✅ |
| Art 34 | Subject notification | Communication template ready | ✅ |
| Art 35 | DPIA completed | For high-risk processing activities | ⚠️ Partial |

**GDPR Compliance Score: 5/8 (63%) ❌**

---

## Compliance Gap Analysis

| Framework | Score | Status | Priority Gaps |
|---|---|---|---|
| NIST CSF | 91% | ✅ Good | DR plan not tested |
| ISO 27001 | 87% | ⚠️ Needs work | DR not tested, incident reporting partial |
| SOC 2 | 83% | ⚠️ Needs work | Change management informal, DR untested |
| GDPR | 63% | ❌ Critical | Privacy by design, right to erasure manual, DPIA partial |

---

## Priority Remediation Actions

### Critical — GDPR (Score 63%)
```
1. Automate right to erasure workflow
   Risk: Manual process too slow for GDPR 30-day requirement
   Timeline: 60 days

2. Embed privacy by design into SDLC
   Risk: New systems may not meet GDPR by default
   Timeline: 90 days

3. Complete DPIA for all high-risk processing activities
   Risk: Unidentified high-risk processing = regulatory exposure
   Timeline: 45 days
```

### High — ISO 27001 + SOC 2
```
4. Test DR plan schedule full DR exercise
   Risk: BCP/DR plan exists but untested = false confidence
   Timeline: 30 days

5. Formalise change management process
   Risk: Informal changes create audit evidence gaps
   Timeline: 30 days

6. Complete incident regulatory notification procedure
   Risk: Incomplete procedure = breach notification failure
   Timeline: 14 days
```

---

## SOC Analyst Compliance Responsibilities

```
Daily:
✅ Ensure SIEM logs are collected from all required sources
✅ Document all incidents in ticketing system
✅ Verify alert response times meet SLA (compliance evidence)

Weekly:
✅ Review access control changes new accounts, permission changes
✅ Verify backup completion logs
✅ Check patch compliance dashboard

Monthly:
✅ Produce compliance metrics report
✅ Review user access remove stale accounts
✅ Verify MFA compliance across all accounts

Annually:
✅ Support external compliance audits
✅ Review and update IR playbooks
✅ Participate in DR exercise
```
