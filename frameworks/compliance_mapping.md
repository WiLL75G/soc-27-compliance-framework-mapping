# Compliance Framework Mapping

Nexus Corp Security Operations Center
Analyst: William
Case ID: COMP-2026-001

Fictional organisation. The frameworks, articles, and control requirements are real. The implementation status and scores are constructed.

---

## Why a SOC Analyst Needs This

Compliance frameworks define the floor. Not the target, the floor.

The reason it lands in the SOC rather than staying with legal:

Every alert triaged is compliance evidence.

Every incident documented is audit trail.

Every log source connected is a mandated control someone signed off on.

Every SLA met is a number that appears in a report to an auditor.

The SOC does not support compliance from a distance. It generates the artefacts compliance is made of, whether anyone in the SOC knows it or not.

---

## Framework 1, NIST CSF

Voluntary framework from the US National Institute of Standards and Technology. Widely adopted as the baseline for cyber risk management.

**Five functions:**

```
IDENTIFY   Know your assets, risks, environment
PROTECT    Safeguards that limit impact
DETECT     Capability to spot incidents
RESPOND    Action when they happen
RECOVER    Restore afterwards
```

Two of those five are the SOC. Detect and Respond are the job description, which means a functioning SOC is delivering 40 percent of NIST by existing.

**Control mapping:**

| Function | Control | Implementation | Status |
|---|---|---|---|
| Identify | Asset management | CMDB, all assets inventoried | Met |
| Identify | Risk assessment | Annual assessment completed | Met |
| Protect | Access control | MFA and RBAC | Met |
| Protect | Awareness training | Annual, mandatory | Met |
| Protect | Data security | AES-256 at rest and in transit | Met |
| Detect | Anomalies and events | Splunk SIEM, 24/7 | Met |
| Detect | Security monitoring | EDR on all endpoints | Met |
| Respond | Response planning | IR playbooks documented | Met |
| Respond | Communications | Incident notification procedure | Met |
| Recover | Recovery planning | BCP and DR documented | **Gap, untested** |
| Recover | Improvements | Post incident reviews conducted | Met |

**Score: 10/11, 91 percent**

The single gap is Recover, which is the function SOCs pay least attention to because it happens after the interesting part. An untested DR plan is a document. The test is what turns it into a capability, and skipping it means the first test is a real incident.

---

## Framework 2, ISO 27001

The international standard for Information Security Management Systems. Certification proves systematic control over sensitive data.

**Domains:**

```
A.5   Information security policies
A.6   Organisation of information security
A.7   Human resource security
A.8   Asset management
A.9   Access control
A.10  Cryptography
A.11  Physical and environmental security
A.12  Operations security
A.13  Communications security
A.14  System acquisition, development, maintenance
A.16  Information security incident management
A.17  Business continuity management
A.18  Compliance
```

A.16 is where the SOC lives.

**Control mapping:**

| Domain | Control | Implementation | Status |
|---|---|---|---|
| A.5 | Information security policy | Documented and approved | Met |
| A.6 | Security roles defined | SOC team roles and responsibilities | Met |
| A.7 | Background checks | Pre employment screening | Met |
| A.8 | Asset inventory | CMDB maintained | Met |
| A.9 | Access control policy | RBAC, MFA, least privilege | Met |
| A.10 | Encryption policy | AES-256, TLS 1.3 | Met |
| A.11 | Physical security | Data centre access controls | Met |
| A.12 | Malware controls | EDR on all endpoints | Met |
| A.12 | Backup policy | Daily, immutable storage | Met |
| A.12 | Audit logging | SIEM collects all sources | Met |
| A.13 | Network segmentation | Micro segmentation | Met |
| A.16 | Incident response | IR playbooks, SOC 24/7 | Met |
| A.16 | Incident reporting | Regulatory notification procedure | **Gap, partial** |
| A.17 | Business continuity | BCP documented, DR untested | **Gap** |
| A.18 | Legal compliance | GDPR and SOX mapped | Met |

**Score: 13/15, 87 percent**

The A.16 reporting gap is the highest risk item on this page relative to effort. It is not really an ISO problem, it is Article 33 wearing an ISO number. GDPR requires notification inside 72 hours and the clock starts at awareness, which happens in the SOC. An incomplete procedure means nobody has decided who declares, who notifies, or when the clock started.

Fourteen days of work sitting under a €20 million exposure.

---

## Framework 3, SOC 2 Type II

An auditing standard for service organisations, evaluated across five Trust Service Criteria.

Type II is the part that matters. Type I is a photograph, Type II is a film. It tests whether controls operated consistently across a period, which means nothing can be tidied up the week before the auditor arrives. The evidence has to have existed the whole time.

**Trust Service Criteria:**

```
Security         Protected against unauthorised access
Availability     Available for operation as agreed
Integrity        Processing is complete, valid, accurate
Confidentiality  Confidential information is protected
Privacy          Personal information handled correctly
```

**Control mapping:**

| Criteria | Control | Implementation | Status |
|---|---|---|---|
| Security | Logical access controls | MFA, RBAC, PAM | Met |
| Security | Incident response | SOC 24/7, IR playbooks | Met |
| Security | Vulnerability management | Monthly scans, patching SLA | Met |
| Security | Change management | Change control process | **Gap, informal** |
| Availability | System monitoring | SIEM and uptime monitoring | Met |
| Availability | Backup and recovery | Daily backups, DR plan | **Gap, DR untested** |
| Integrity | Input validation | Application level controls | Met |
| Integrity | Error detection | Logging and alerting | Met |
| Confidentiality | Data classification | Four tier policy | Met |
| Confidentiality | Encryption | AES-256, TLS 1.3 | Met |
| Privacy | Data retention | Retention policy documented | Met |
| Privacy | Data subject rights | GDPR process implemented | Met |

**Score: 10/12, 83 percent**

Change management fails on evidence, not on security. The changes may all be sound. If they are undocumented, an auditor cannot verify that, and unverifiable is indistinguishable from failed.

---

## Framework 4, GDPR

EU law governing personal data of EU citizens. Fines up to €20 million or 4 percent of global annual turnover, whichever is larger.

**Articles that reach the SOC:**

```
Art 5   Principles of processing
Art 17  Right to erasure
Art 25  Data protection by design and default
Art 32  Security of processing, encryption, pseudonymisation
Art 33  Breach notification to the authority, 72 hours
Art 34  Communication of breach to data subjects
Art 35  Data Protection Impact Assessment
```

**Control mapping:**

| Article | Requirement | Implementation | Status |
|---|---|---|---|
| Art 5 | Lawful processing | Data processing register | Met |
| Art 17 | Right to erasure | Deletion workflow exists | **Gap, manual** |
| Art 25 | Privacy by design | Security built into SDLC | **Gap, partial** |
| Art 32 | Encryption | AES-256, TLS 1.3 | Met |
| Art 32 | Pseudonymisation | PII fields pseudonymised | Met |
| Art 33 | 72 hour breach notification | Notification in IR procedure | Met |
| Art 34 | Subject notification | Communication template ready | Met |
| Art 35 | DPIA completed | High risk processing activities | **Gap, partial** |

**Score: 5/8, 63 percent**

Three gaps, and they are three different kinds of problem.

**Art 17, manual erasure.** Works until volume arrives. A control that passes right up until it is tested.

**Art 25, privacy by design not embedded.** This one grows. Every system built from today starts non compliant and gets retrofitted later, which is the most expensive order to do anything in. The other gaps sit still. This one compounds with every release.

**Art 35, DPIA partial.** This is the unknown. The other two are quantified. This one means high risk processing exists that nobody has assessed, so the real exposure is 63 percent plus whatever is in the unassessed set.

---

## Gap Summary

| Framework | Score | Gaps |
|---|---|---|
| NIST CSF | 91 percent | DR untested |
| ISO 27001 | 87 percent | DR untested, incident reporting partial |
| SOC 2 Type II | 83 percent | Change management informal, DR untested |
| GDPR | 63 percent | Privacy by design, manual erasure, DPIA partial |

**Total: 38 of 46 controls, 83 percent**

The aggregate is the least useful number here. It averages a 91 and a 63 across frameworks that carry entirely different consequences, and it describes an organisation that does not exist. The 63 is what a regulator would look at.

---

## The Shared Gap

One item fails three frameworks: **the DR plan has never been tested.**

NIST Recover. ISO A.17. SOC 2 Availability.

Three findings, one cause, one 30 day exercise.

That is the argument for mapping frameworks together rather than sequentially. Assessed separately this reads as three problems with three owners and three budgets. Mapped together it is one exercise that moves three scores at once, and it is the cheapest item on the remediation list.

---

## Remediation, Ordered by Leverage

```
1. Complete incident regulatory notification procedure
   Framework:  ISO A.16, GDPR Art 33
   Risk:       72 hour clock running with nobody assigned to start it
   Timeline:   14 days
   Why first:  Shortest fuse, largest penalty, least work

2. Test the DR plan
   Framework:  NIST, ISO A.17, SOC 2 Availability
   Risk:       Documented but unproven is false confidence
   Timeline:   30 days
   Why second: One action, three frameworks

3. Formalise change management
   Framework:  SOC 2 Security
   Risk:       Undocumented changes fail Type II on evidence
   Timeline:   30 days

4. Complete DPIA for all high risk processing
   Framework:  GDPR Art 35
   Risk:       Unassessed processing is unquantified exposure
   Timeline:   45 days

5. Automate right to erasure
   Framework:  GDPR Art 17
   Risk:       Manual process fails at volume against a 30 day duty
   Timeline:   60 days

6. Embed privacy by design into the SDLC
   Framework:  GDPR Art 25
   Risk:       Gap grows with every release until closed
   Timeline:   90 days
```

Ordered by leverage and fuse length rather than by framework score. The GDPR items carry the largest exposure and they are also the slowest, so they start now and land later. That is not the same as being lower priority.

---

## The SOC's Compliance Work

Most of this is already happening. Naming it as compliance is what turns it into evidence.

```
DAILY
  Verify SIEM is collecting from every required source
  Document every incident in the ticketing system
  Track response times against SLA

WEEKLY
  Review access control changes, new accounts, permission changes
  Verify backup completion logs
  Check patch compliance

MONTHLY
  Produce compliance metrics
  Review user access, remove stale accounts
  Verify MFA coverage

ANNUALLY
  Support external audits
  Review and update IR playbooks
  Participate in the DR exercise
```

The daily items are the ones that carry the weight. An auditor does not ask whether the SOC responds to incidents. They ask for the evidence, from a period, consistently, and the SOC either has it or it does not. There is no retrofitting a ticket queue.

---

## Article 33 and the Alert Queue

The 72 hour clock starts at awareness.

Awareness happens in the SOC, at 03:00, when an alert fires and a Tier 1 analyst reads it. That analyst is the person who starts a regulatory countdown, usually without knowing they have done it.

Which means the notification trigger belongs in the playbook, not in a policy document nobody opens at 03:00. A SOC that detects a breach and does not recognise it as notifiable has met its technical obligation and missed the legal one, and the fine does not care about the distinction.
