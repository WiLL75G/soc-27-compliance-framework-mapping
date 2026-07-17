# Compliance Framework Mapping and Gap Analysis

Four frameworks, 46 controls, 8 gaps. The lowest score is GDPR at 63 percent, and one untested DR plan fails three frameworks at once.

## At a Glance

| Field | Detail |
| --- | --- |
| Work Type | Compliance mapping and gap analysis |
| Frameworks | NIST CSF, ISO 27001, SOC 2 Type II, GDPR |
| Organisation | Nexus Corp, fictional |
| Controls Mapped | 46 |
| Compliant | 38 |
| Gaps | 8 |
| Critical Finding | GDPR at 63 percent |

## What This Is

A compliance assessment against a fictional organisation. The frameworks, articles, and control requirements are real. The scores and the gaps are constructed.

The reason a SOC analyst does this at all: every alert triaged, every incident documented, every log retained is compliance evidence. The SOC does not support compliance from a distance, it produces the artefacts compliance is made of.

## NIST CSF, 91 percent

11 controls across Identify, Protect, Detect, Respond, Recover. 10 implemented.

Gap: DR plan exists, never tested.

NIST is the framework that maps most directly onto SOC work. Detect and Respond are two of the five functions, which means a functioning SOC is already doing 40 percent of the framework by existing.

An untested DR plan is a document, not a capability. Nobody finds out whether it works during a tabletop, they find out during the incident, and by then the answer is expensive.

## ISO 27001, 87 percent

15 controls across 13 domains. 13 implemented.

Gaps: DR plan untested. Incident regulatory notification procedure incomplete.

A.16, incident management, is the domain the SOC lives in.

The notification gap is the one that matters and it is not really an ISO problem. GDPR Article 33 requires breach notification inside 72 hours, and the clock starts at awareness, not at containment. An incomplete notification procedure means nobody knows who decides, who tells the regulator, or when the 72 hours started, and the SOC is the function that becomes aware first.

That gap is 14 days of work and it sits under a €20 million exposure.

## SOC 2 Type II, 83 percent

12 controls across 5 Trust Service Criteria. 10 implemented.

Gaps: Change management is informal. DR plan untested.

Type II is the distinction worth knowing. Type I is a photograph, Type II is a film. It tests whether controls operated consistently over a period, which means the SOC cannot pass by tidying up before the auditor arrives. Evidence has to have existed the whole time.

Informal change management fails on evidence rather than on security. The change might be perfectly sound. If it is undocumented, the auditor cannot verify it happened correctly, and unverifiable is the same as failed.

## GDPR, 63 percent

8 controls across key articles. 5 implemented.

Gaps: Right to erasure is manual. Privacy by design not embedded. DPIA coverage incomplete.

**Right to erasure, manual.** GDPR requires response inside 30 days. A manual process meets that until volume arrives, and then it does not. It is a control that works right up until the day it is tested.

**Privacy by design not in the SDLC.** This is the structural one. It means every new system built from today onward starts non compliant and gets retrofitted, which is the most expensive order to do it in. The gap does not stay the same size, it grows with every release.

**DPIA incomplete for high risk processing.** This is the unknown. The other two gaps are quantified problems. This one means there is high risk processing nobody has assessed, so the actual exposure is not 63 percent, it is 63 percent plus whatever the unassessed processing turns out to be.

The reason GDPR outranks everything else here is not the framework. It is €20 million or 4 percent of global turnover, whichever is larger, and the fact that a breach in a non compliant environment costs the fine and the breach.

## The Shared Gap

One item appears in three frameworks: the DR plan has never been tested.

NIST, ISO, and SOC 2 all fail on it independently. Three findings, one cause, and one 30 day exercise closes all three.

That is the argument for mapping frameworks together rather than one at a time. Assessed separately, this reads as three problems and gets three owners, three budgets, and three timelines. Mapped together, it is one exercise, and it moves three scores at once.

## Compliance Summary

| Framework | Mapped | Compliant | Gaps | Score |
| --- | --- | --- | --- | --- |
| NIST CSF | 11 | 10 | 1 | 91 percent |
| ISO 27001 | 15 | 13 | 2 | 87 percent |
| SOC 2 Type II | 12 | 10 | 2 | 83 percent |
| GDPR | 8 | 5 | 3 | 63 percent |
| Total | 46 | 38 | 8 | 83 percent |

The 83 percent aggregate is the least useful number on this page. It averages a 91 and a 63, which means it describes an organisation that does not exist. Frameworks are not interchangeable and the fine attached to GDPR is not attached to NIST.

Report the breakdown. The total is decoration.

## Remediation Plan

| Priority | Action | Framework | Timeline |
| --- | --- | --- | --- |
| 1 | Complete incident notification procedure | ISO 27001, GDPR Art. 33 | 14 days |
| 2 | Schedule and complete DR exercise | NIST, ISO, SOC 2 | 30 days |
| 3 | Formalise change management | SOC 2 | 30 days |
| 4 | Complete DPIA for all high risk processing | GDPR | 45 days |
| 5 | Automate right to erasure workflow | GDPR | 60 days |
| 6 | Embed privacy by design into SDLC | GDPR | 90 days |

Reordered by leverage rather than by framework severity.

The notification procedure goes first. It is 14 days, it closes the item with the shortest fuse, and until it exists the 72 hour clock is running against an organisation that has not decided who starts it.

The DR exercise goes second because one action moves three frameworks.

The GDPR items are the largest exposure and they are also the slowest. They start now and finish later, which is a different thing from being lower priority.

## Findings

NIST at 91 percent. Strongest, single gap, DR testing.

ISO at 87 percent. The notification gap is the highest risk item on the page relative to effort.

SOC 2 at 83 percent. Change management fails on evidence, not on security.

GDPR at 63 percent. Three gaps, the largest financial exposure, and one gap that grows on its own.

DR testing fails three frameworks from one cause.

GDPR breach notification is present in the IR playbooks. The procedure around it is not.

## The SOC Angle

Article 33 puts the SOC inside the compliance function whether anyone planned it or not.

The 72 hour clock starts at awareness. Awareness happens in the SOC, at 03:00, when an alert fires. The analyst who triages it is the person who starts a regulatory countdown, usually without knowing it.

Which means the notification trigger has to be in the playbook, not in a policy document nobody reads at 03:00. A SOC that detects a breach and does not recognise it as a notifiable event has met its technical obligation and failed the legal one.

## What This Demonstrates

Mapping controls across four frameworks and finding where they overlap.

Identifying a shared root cause behind findings in three separate frameworks.

Prioritising by leverage and time fuse rather than by severity label.

Knowing why SOC 2 Type II changes what evidence has to look like.

Recognising that a gap which grows, privacy by design, is different from a gap that sits still.

Refusing to lead with a meaningless aggregate.

Connecting Article 33 to the alert queue, which is where the obligation actually lands.

## Repository Structure

```
compliance-framework-mapping/
├── README.md
└── frameworks/
    └── compliance_mapping.md
```

---

[![LinkedIn](https://img.shields.io/badge/LinkedIn-WilliamInCyber-blue?style=flat&logo=linkedin)](https://linkedin.com/in/WilliamInCyber)
[![X](https://img.shields.io/badge/X-@WilliamInCyber-black?style=flat&logo=x)](https://x.com/WilliamInCyber)
