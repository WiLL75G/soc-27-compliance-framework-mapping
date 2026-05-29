# Day 27 – SOC Tier 1 Incident Report: Compliance Framework Mapping

---

## Incident Summary

- **Project Type:** Compliance Framework Mapping & Gap Analysis
- **Severity:** Strategic — Critical GDPR Gap Identified (63% Compliance)
- **Frameworks Mapped:** NIST CSF, ISO 27001, SOC 2 Type II, GDPR
- **Scope:** Nexus Corp — All security controls mapped across 4 frameworks
- **Status:** Complete — Gap Analysis Delivered, Remediation Plan Produced

---

## Executive Summary

A full compliance framework mapping was conducted for Nexus Corp across four major security frameworks — NIST CSF, ISO 27001, SOC 2 Type II, and GDPR. NIST CSF compliance scored highest at 91%. A critical GDPR gap was identified at 63% — driven by manual right-to-erasure processes, incomplete privacy-by-design implementation, and partial DPIA coverage. ISO 27001 and SOC 2 both scored in the high 80s with shared gaps in DR testing and change management. A prioritised remediation plan was produced with six actions across two urgency tiers.

---

## Affected System

- **Organisation:** Nexus Corp
- **Frameworks Assessed:** NIST CSF, ISO 27001, SOC 2 Type II, GDPR
- **Total Controls Mapped:** 46 controls across 4 frameworks
- **Compliant Controls:** 38
- **Gap Controls:** 8
- **Critical Gap:** GDPR — 63% compliance

---

## Investigation Methodology

---

### 1. NIST Cybersecurity Framework Assessment

- Mapped all 11 controls across 5 NIST CSF functions — Identify, Protect, Detect, Respond, Recover
- 10 of 11 controls fully implemented
- Single gap: DR/recovery plan exists but has not been tested

#### SOC Observations:

- NIST CSF is the most SOC-friendly framework — Detect and Respond functions map directly to SOC operations
- An untested DR plan is no plan at all — a failed DR exercise is better than discovering failure during a real incident
- SIEM coverage of all log sources is the most critical NIST Detect control

**Score: 10/11 — 91% ✅**

---

### 2. ISO 27001 Assessment

- Mapped 15 controls across 13 ISO 27001 domains
- 13 of 15 controls fully implemented
- Two gaps: DR plan untested, incident regulatory notification procedure incomplete

#### SOC Observations:

- ISO 27001 A.16 (Incident Management) is the domain most relevant to SOC operations
- Incomplete regulatory notification procedure is a compliance risk — GDPR requires 72-hour breach notification
- ISO 27001 certification requires documented evidence — every SOC action must be logged

**Score: 13/15 — 87% ⚠️**

---

### 3. SOC 2 Type II Assessment

- Mapped 12 controls across 5 Trust Service Criteria
- 10 of 12 controls fully implemented
- Two gaps: Change management is informal, DR plan untested

#### SOC Observations:

- SOC 2 Type II is tested over time — not a snapshot — meaning SOC evidence must be consistent
- Informal change management creates audit evidence gaps — auditors cannot accept undocumented changes
- Availability criteria requires DR to be tested — documented but untested fails the audit

**Score: 10/12 — 83% ⚠️**

---

### 4. GDPR Assessment — Critical Gap

- Mapped 8 controls across key GDPR articles
- Only 5 of 8 controls fully implemented
- Three gaps: Manual right-to-erasure, partial privacy by design, incomplete DPIA coverage

#### Critical Findings:
- Right to erasure is a manual process — GDPR requires response within 30 days
- Privacy by design not embedded in SDLC — new systems may not meet GDPR by default
- DPIA not completed for all high-risk processing — unidentified regulatory exposure

#### SOC Observations:

- GDPR Article 33 requires 72-hour breach notification — SOC must have this in IR playbooks
- Data breach = potential €20M fine or 4% of global turnover — GDPR gaps are business-critical
- SOC analysts are the first to identify potential GDPR breaches — they must know the notification triggers

**Score: 5/8 — 63% ❌**

---

## Compliance Gap Summary

| Framework | Controls Mapped | Compliant | Gaps | Score | Status |
|---|---|---|---|---|---|
| NIST CSF | 11 | 10 | 1 | 91% | ✅ |
| ISO 27001 | 15 | 13 | 2 | 87% | ⚠️ |
| SOC 2 Type II | 12 | 10 | 2 | 83% | ⚠️ |
| GDPR | 8 | 5 | 3 | 63% | ❌ |
| **Total** | **46** | **38** | **8** | **83%** | **⚠️** |

---

## Remediation Plan

| Priority | Action | Framework | Timeline |
|---|---|---|---|
| 1 — Critical | Complete DPIA for all high-risk processing | GDPR | 45 days |
| 2 — Critical | Automate right to erasure workflow | GDPR | 60 days |
| 3 — Critical | Embed privacy by design into SDLC | GDPR | 90 days |
| 4 — High | Schedule and complete DR exercise | NIST/ISO/SOC2 | 30 days |
| 5 — High | Formalise change management process | SOC 2 | 30 days |
| 6 — High | Complete incident notification procedure | ISO 27001 | 14 days |

---

## SOC Analyst Findings

- NIST CSF compliance strong at 91% — single gap is DR testing
- ISO 27001 at 87% — incomplete notification procedure is highest risk item
- SOC 2 at 83% — informal change management creates audit evidence risk
- GDPR at 63% — critical gap requiring immediate attention
- Shared gap across 3 frameworks: DR plan exists but has never been tested
- GDPR breach notification procedure confirmed in IR playbooks ✅

---

## SOC Analyst Response

- Mapped 46 controls across 4 major compliance frameworks
- Identified 8 compliance gaps with business risk assessments
- Produced prioritised 6-action remediation plan
- Confirmed GDPR 72-hour breach notification in SOC IR playbooks
- Recommended immediate DPIA completion for high-risk processing
- Flagged DR plan testing as shared gap across 3 frameworks

---

## Analyst Insight

Compliance is not just about passing audits — it is about building the evidence that proves your security controls work. A SOC analyst who understands compliance frameworks knows that every alert they triage, every incident they document, and every log they collect is compliance evidence. The GDPR gap at 63% is the most urgent finding in this assessment — not because of the framework itself, but because a data breach in a non-compliant GDPR environment can cost the business tens of millions. The SOC is on the front line of GDPR — every breach starts as a SOC alert.

---

## Learning Outcome

- Map security controls across NIST CSF, ISO 27001, SOC 2, and GDPR
- Identify compliance gaps and quantify their business risk
- Understand the SOC analyst's role in compliance evidence collection
- Apply GDPR Article 33 — 72-hour breach notification — to IR playbooks
- Produce a prioritised compliance remediation plan
- Understand how SOC operations directly support regulatory compliance
- Connect daily SOC work to compliance framework requirements

---

## Repository Structure

```
soc-27-compliance-framework-mapping/
├── README.md
├── frameworks/
│   └── compliance_mapping.md
└── reports/
```

---

## Conclusion

This project delivers a complete compliance framework mapping for Nexus Corp across NIST CSF, ISO 27001, SOC 2 Type II, and GDPR. Forty-six controls were assessed and eight gaps were identified. A critical GDPR compliance gap at 63% requires immediate remediation. A prioritised six-action remediation plan was produced. This project demonstrates that a SOC analyst understands not just how to detect and respond to threats — but how security operations connect to the regulatory and compliance obligations that protect the business.
