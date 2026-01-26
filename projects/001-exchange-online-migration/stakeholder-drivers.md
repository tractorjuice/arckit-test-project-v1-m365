# Stakeholder Drivers & Goals Analysis: Exchange Online Migration to Microsoft 365

> **Template Status**: Live | **Version**: 0.11.1 | **Command**: `/arckit.stakeholders`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-STKE-v1.0 |
| **Document Type** | Stakeholder Drivers & Goals Analysis |
| **Project** | Exchange Online Migration to Microsoft 365 (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-01-26 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Enterprise Architecture Team, Cabinet Office |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Project Steering Committee, Migration Team, Change Management |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-01-26 | ArcKit AI | Initial creation from `/arckit.stakeholders` command | PENDING | PENDING |

---

## Executive Summary

### Purpose
This document identifies key stakeholders for the Cabinet Office Exchange Online Migration project, their underlying drivers (motivations, concerns, needs), how these drivers manifest into goals, and the measurable outcomes that will satisfy those goals. This analysis ensures stakeholder alignment and provides traceability from individual concerns to project success metrics.

### Key Findings
The migration project has strong stakeholder alignment around cost reduction (£800K savings), security enhancement, and compliance objectives. The primary tension exists between the CTO's aggressive timeline (Month 9 deadline due to hardware end-of-support) and Operations/Security teams' desire for thorough testing. A secondary conflict exists between Finance's cost containment and Change Management's request for comprehensive training investment. These conflicts are manageable through phased delivery with adequate pilot periods.

### Critical Success Factors
- **CSF-1**: Zero data loss during migration (100% mailbox content integrity)
- **CSF-2**: SIRO sign-off on OFFICIAL-SENSITIVE controls before go-live
- **CSF-3**: User adoption >80% proficiency within 1 month post-migration
- **CSF-4**: Hardware decommission deadline met (Month 12) to avoid £500K refresh costs
- **CSF-5**: No security incidents during migration period

### Stakeholder Alignment Score
**Overall Alignment**: MEDIUM-HIGH

Strong alignment on strategic objectives (cloud-first, cost savings, security). Minor conflicts between timeline pressure and risk mitigation require active management. Finance and Security alignment achieved through phased approach with early pilot validation.

---

## Stakeholder Identification

### Internal Stakeholders

| Stakeholder | Role/Department | Influence | Interest | Engagement Strategy |
|-------------|-----------------|-----------|----------|---------------------|
| CTO | Executive Sponsor | HIGH | HIGH | Active involvement, decision authority, weekly steering |
| Finance Director | Budget Owner | HIGH | HIGH | Monthly cost tracking, ROI validation |
| SIRO | Senior Information Risk Owner | HIGH | HIGH | Security gate approvals, risk acceptance |
| CISO | Chief Information Security Officer | HIGH | HIGH | Security controls validation, threat assessment |
| DPO | Data Protection Officer | HIGH | MEDIUM | GDPR compliance, PIA sign-off |
| Enterprise Architect | Technical Authority | MEDIUM | HIGH | Architecture decisions, principles alignment |
| Exchange Administrator | Technical Lead | MEDIUM | HIGH | Migration execution, technical validation |
| Change Manager | Change Management Lead | MEDIUM | HIGH | User adoption, training programme |
| Service Desk Manager | Operations | MEDIUM | MEDIUM | Support readiness, ticket volume management |
| Directorate Heads | Business Unit Leaders | MEDIUM | HIGH | Migration scheduling, business continuity |
| End Users (3,500) | Knowledge Workers | LOW | HIGH | Training, feedback, adoption |
| IT Operations | Infrastructure Team | MEDIUM | MEDIUM | On-prem decommission, monitoring |
| Procurement | Contracts Team | LOW | MEDIUM | Vendor management, licensing |

### External Stakeholders

| Stakeholder | Organisation | Relationship | Influence | Interest |
|-------------|--------------|--------------|-----------|----------|
| Microsoft | Cloud Provider | Strategic Partner | HIGH | HIGH |
| NCSC | National Cyber Security Centre | Regulatory Guidance | HIGH | MEDIUM |
| ICO | Information Commissioner's Office | Data Protection Regulator | HIGH | MEDIUM |
| National Archives | Records Authority | Records Guidance | MEDIUM | LOW |
| Other Government Departments | Cross-Government Partners | Federation Partners | LOW | MEDIUM |
| Migration Vendor (BitTitan) | Service Provider | Supplier | MEDIUM | HIGH |
| Microsoft Premier Support | Technical Support | Support Partner | MEDIUM | HIGH |

### Stakeholder Power-Interest Grid

```
HIGH POWER
    │
    │  [Manage Closely]              │  [Keep Satisfied]
    │  - CTO (Executive Sponsor)     │  - Finance Director
    │  - SIRO                        │  - DPO
    │  - CISO                        │  - Procurement
    │  - Enterprise Architect        │
    │                                │
────┼────────────────────────────────┼─────────────────────────
    │  [Keep Informed]               │  [Monitor]
    │  - End Users (3,500)           │  - National Archives
    │  - Directorate Heads           │  - Other Govt Depts
    │  - Change Manager              │
    │  - Exchange Admin              │
    │  - Service Desk                │
    │                                │
LOW POWER                                              HIGH INTEREST
```

---

## Stakeholder Drivers Analysis

### SD-1: CTO - Hardware End-of-Support Deadline

**Stakeholder**: Chief Technology Officer (Executive Sponsor)

**Driver Category**: RISK / FINANCIAL

**Driver Statement**: Avoid £500K unbudgeted hardware refresh by completing migration before Exchange 2016 server hardware fails or requires emergency replacement (Month 12 deadline).

**Context & Background**:
The on-premises Exchange 2016 infrastructure runs on Dell PowerEdge servers purchased in 2016 with 5-year warranty that expired in 2021. Extended support ends Month 12 (October 2026). Hardware failure would require emergency procurement (£500K) with 12-week lead time, causing extended outage. The CTO has committed to the board that cloud migration will avoid this capital expenditure.

**Driver Intensity**: CRITICAL

**Enablers**:
- Pre-approved M365 E5 licenses (3,500 already procured)
- Experienced migration vendor (BitTitan) engaged
- Microsoft Premier Support for hybrid configuration

**Blockers**:
- Complex hybrid configuration could delay pilot
- Large mailboxes (>50GB) may exceed weekend migration windows
- Change freeze Q4 (Jan-Mar 2026) for Budget preparation

**Related Stakeholders**:
- Finance Director (cost avoidance)
- IT Operations (hardware maintenance burden)

---

### SD-2: Finance Director - Cost Reduction and Value for Money

**Stakeholder**: Finance Director (Budget Owner)

**Driver Category**: FINANCIAL

**Driver Statement**: Deliver £800K annual cost savings to meet Spending Review commitments and demonstrate value for money to Treasury and NAO auditors.

**Context & Background**:
Cabinet Office committed to 15% IT cost reduction in the 2024 Spending Review. On-premises Exchange infrastructure costs £2.95M annually (licensing, hardware, support, staff). Cloud migration reduces this to £2.15M (£800K savings). Treasury monitors departmental savings commitments. NAO may audit this migration as part of government digital transformation value-for-money assessment.

**Driver Intensity**: HIGH

**Enablers**:
- Clear cost baseline documented
- Microsoft CSP pricing locked for 3 years
- On-prem decommission plan eliminates ongoing costs

**Blockers**:
- Scope creep adding features increases costs
- Extended parallel running (hybrid) doubles licensing temporarily
- Contingency overrun would reduce net savings

**Related Stakeholders**:
- CTO (budget owner for IT)
- Procurement (vendor negotiations)
- NAO (potential external audit)

---

### SD-3: SIRO - Risk Acceptance for OFFICIAL Data in Cloud

**Stakeholder**: Senior Information Risk Owner

**Driver Category**: COMPLIANCE / RISK

**Driver Statement**: Obtain assurance that OFFICIAL and OFFICIAL-SENSITIVE data can be processed in Microsoft cloud with acceptable residual risk, enabling SIRO sign-off required for go-live.

**Context & Background**:
As SIRO, this stakeholder is personally accountable for information risk to the Permanent Secretary and ultimately to Ministers. A data breach involving Cabinet papers or OFFICIAL-SENSITIVE policy documents would be a ministerial-level incident potentially requiring parliamentary statement. The SIRO needs documented evidence that cloud controls meet or exceed on-premises security. Previous cloud migrations in other departments have received NAO scrutiny.

**Driver Intensity**: CRITICAL

**Enablers**:
- Microsoft UK data residency guarantee
- NCSC Cloud Security Principles mapping completed
- Customer Lockbox prevents unauthorised Microsoft access
- Sensitivity labels enforce classification controls

**Blockers**:
- DLP policy misconfiguration could leak sensitive data
- Incomplete threat model
- Insufficient penetration testing evidence
- Unclear incident response for cloud-specific threats

**Related Stakeholders**:
- CISO (security controls implementation)
- DPO (personal data protection)
- IAO (Information Asset Owner per directorate)

---

### SD-4: CISO - Enhanced Security Posture

**Stakeholder**: Chief Information Security Officer

**Driver Category**: RISK / COMPLIANCE

**Driver Statement**: Leverage cloud migration to significantly improve security posture through Zero Trust controls, advanced threat protection, and consolidated security monitoring - addressing audit findings from last year's CHECK assessment.

**Context & Background**:
The 2025 NCSC CHECK penetration test identified 3 high-severity findings related to legacy Exchange: lack of MFA for OWA, insufficient email threat protection, and gaps in audit logging. The CISO has committed to the Security Board that cloud migration will remediate all findings. Additionally, the CISO sees opportunity to implement Zero Trust architecture (Conditional Access, device compliance) that would be prohibitively expensive on-premises.

**Driver Intensity**: HIGH

**Enablers**:
- M365 E5 includes Defender for Office 365 Plan 2
- Conditional Access enables Zero Trust without additional cost
- Unified Audit Log provides 7-year retention
- Microsoft Sentinel integration for SIEM

**Blockers**:
- Aggressive timeline may compress security testing
- Staff need training on new security tools
- Conditional Access policies require careful tuning to avoid user lockouts

**Related Stakeholders**:
- SIRO (risk acceptance authority)
- IT Operations (security monitoring)
- End Users (MFA adoption)

---

### SD-5: DPO - GDPR Compliance and Data Subject Rights

**Stakeholder**: Data Protection Officer

**Driver Category**: COMPLIANCE

**Driver Statement**: Ensure migration maintains GDPR compliance, enables efficient Subject Access Request (SAR) processing, and documents lawful basis for Microsoft as data processor.

**Context & Background**:
Cabinet Office processes personal data of citizens, staff, and ministers. The DPO must ensure Microsoft's role as data processor is documented in a compliant Data Processing Agreement. SAR requests must be fulfilled within 30 days (20 working days). eDiscovery capabilities in M365 should improve SAR response times from current 15-day average. ICO has increased scrutiny of public sector data sharing.

**Driver Intensity**: HIGH

**Enablers**:
- Microsoft DPA already reviewed and accepted by legal
- eDiscovery (Premium) enables faster SAR searches
- Retention labels support data minimisation
- Privacy Impact Assessment template available

**Blockers**:
- Migration could temporarily duplicate data (on-prem + cloud)
- Staff need training on eDiscovery for SAR
- Retention labels must be configured correctly before migration

**Related Stakeholders**:
- SIRO (information risk)
- Legal (DPA review)
- Records Manager (retention schedules)

---

### SD-6: Directorate Heads - Business Continuity During Migration

**Stakeholder**: Directorate Heads (8 directorates)

**Driver Category**: OPERATIONAL / RISK

**Driver Statement**: Ensure email service remains available during migration with minimal disruption to business operations, particularly during critical periods (Budget, parliamentary sessions, ministerial activities).

**Context & Background**:
Each directorate has different operational rhythms. Finance cannot migrate during Budget preparation (Jan-Mar). Policy teams have parliamentary questions cycles. Ministerial offices have high-profile correspondence that cannot be disrupted. Previous IT changes have caused directorate complaints when poorly scheduled. Directorate heads are accountable to their Directors General for operational continuity.

**Driver Intensity**: HIGH

**Enablers**:
- Phased migration allows directorate-by-directorate scheduling
- Weekend migrations minimise business impact
- Hybrid coexistence means gradual transition
- Directorate liaison officers appointed

**Blockers**:
- Multiple directorates want to be "last" (nobody wants to be pilot)
- Conflicting blackout periods reduce available migration windows
- Ministerial offices require special handling

**Related Stakeholders**:
- Change Manager (scheduling coordination)
- CTO (timeline pressure)
- End Users (direct impact)

---

### SD-7: End Users - Minimal Disruption and Easy Transition

**Stakeholder**: End Users (3,500 staff)

**Driver Category**: OPERATIONAL / PERSONAL

**Driver Statement**: Continue working productively with minimal learning curve, reliable email access, and clear guidance - avoiding frustration that impacts job performance and wellbeing.

**Context & Background**:
Users range from digitally confident to digitally anxious. Many have worked with on-premises Outlook for 10+ years and resist change. Post-COVID, staff expect reliable remote access. Poor IT changes generate complaints to HR and union representatives. User satisfaction surveys influence IT budget decisions. Staff wellbeing is a Cabinet Office HR priority.

**Driver Intensity**: HIGH

**Enablers**:
- Outlook desktop interface largely unchanged
- OWA provides anywhere access
- Mobile email enables flexible working
- Training materials in multiple formats (video, written, drop-in sessions)

**Blockers**:
- New MFA requirement adds friction
- Conditional Access may block access unexpectedly
- Some users have complex mailbox setups (rules, categories)
- Union may raise concerns about monitoring

**Related Stakeholders**:
- Change Manager (training delivery)
- Service Desk (support volume)
- HR (staff wellbeing)
- Trade Unions (staff concerns)

---

### SD-8: Change Manager - Successful User Adoption

**Stakeholder**: Change Manager

**Driver Category**: OPERATIONAL / PERSONAL

**Driver Statement**: Achieve measurable user adoption success (80%+ proficiency) to demonstrate change management value and avoid repeat of previous IT project adoption failures.

**Context & Background**:
The previous SharePoint migration had 40% adoption at 6 months, causing senior management criticism of change management function. The Change Manager's performance objectives include adoption metrics for this migration. A successful M365 migration would validate the ADKAR methodology investment and secure future change management budget.

**Driver Intensity**: HIGH

**Enablers**:
- Executive sponsorship from CTO
- Budget allocated for training (£150K)
- M365 Champions network established
- Microsoft provides free learning content

**Blockers**:
- Compressed timeline limits training lead time
- Some directorates resistant to mandatory training
- Training competes with operational priorities
- Measuring "proficiency" is subjective

**Related Stakeholders**:
- End Users (training recipients)
- Directorate Heads (release staff for training)
- Service Desk (post-training support)

---

### SD-9: Service Desk Manager - Manageable Support Volume

**Stakeholder**: Service Desk Manager

**Driver Category**: OPERATIONAL / PERSONAL

**Driver Statement**: Maintain service desk performance SLAs during and after migration without requiring additional headcount, avoiding the support surge that occurred during Teams rollout.

**Context & Background**:
Teams rollout in 2024 caused 300% increase in tickets for 3 months, resulting in SLA breaches and staff overtime. The Service Desk Manager committed to management that lessons learned would prevent recurrence. Current baseline is 80 email-related tickets/week. Target is return to baseline within 4 weeks post-migration. KPIs are tied to bonus.

**Driver Intensity**: MEDIUM

**Enablers**:
- Pre-migration training reduces user confusion
- Self-service knowledge base articles
- Tiered support with M365 Champions handling Tier 0
- Microsoft FastTrack for complex issues

**Blockers**:
- Big-bang migration would create ticket surge
- Inadequate training creates support debt
- New features (sensitivity labels) generate queries
- Staff holidays reduce service desk capacity

**Related Stakeholders**:
- Change Manager (training effectiveness)
- End Users (support requesters)
- IT Operations (escalation path)

---

### SD-10: Exchange Administrator - Technical Success and Career Development

**Stakeholder**: Exchange Administrator (Technical Lead)

**Driver Category**: PERSONAL / OPERATIONAL

**Driver Statement**: Deliver technically successful migration demonstrating cloud expertise, positioning for career advancement into Cloud Architect role while avoiding blame for any migration failures.

**Context & Background**:
The Exchange Admin has 15 years on-premises experience but limited cloud exposure. This migration is an opportunity to build M365 skills highly valued in the job market. However, migration failures would be career-damaging. The admin wants adequate testing time and authority to halt migration if issues arise. There's also concern about job security post-migration (reduced on-prem workload).

**Driver Intensity**: MEDIUM

**Enablers**:
- Microsoft certification training approved
- Pilot phase allows learning in controlled environment
- Clear escalation path to Microsoft Premier Support
- Role evolution plan to Cloud Operations

**Blockers**:
- Timeline pressure reduces testing time
- Blame culture if issues arise
- Unclear career path post-migration
- Knowledge transfer to wider team incomplete

**Related Stakeholders**:
- CTO (career sponsor)
- IT Operations (team structure)
- Migration Vendor (technical partnership)

---

## Driver-to-Goal Mapping

### Goal G-1: Complete Migration Within 9-Month Timeline

**Derived From Drivers**: SD-1 (CTO deadline), SD-2 (cost savings start date)

**Goal Owner**: CTO (Executive Sponsor)

**Goal Statement**: Migrate 100% of 3,500 user mailboxes to Exchange Online by Month 9 (August 2026) with zero data loss, enabling hardware decommission by Month 12.

**Why This Matters**: Missing the deadline triggers £500K hardware refresh (SD-1) and delays £800K annual savings by 12 months (SD-2). The CTO has committed this timeline to the board.

**Success Metrics**:
- **Primary Metric**: Percentage of mailboxes migrated (target: 100%)
- **Secondary Metrics**:
  - Data integrity validation (target: 100% item count match)
  - Migration velocity (target: 300 mailboxes per weekend)
  - Rollback rate (target: <2%)

**Baseline**: 0% migrated (current state)

**Target**: 100% migrated by Month 9

**Measurement Method**: Exchange Admin Center migration dashboard, weekly migration batch reports

**Dependencies**:
- Azure AD Connect operational (Month 1)
- Exchange Hybrid configured (Month 2)
- Pilot successful (Month 3)
- Directorate migration scheduling agreed (Month 4)

**Risks to Achievement**:
- R-001: Hybrid configuration complexity delays pilot
- R-004: Large mailboxes exceed weekend windows
- BC-005: Change freeze reduces available windows

---

### Goal G-2: Achieve £800K Annual Cost Savings

**Derived From Drivers**: SD-2 (Finance cost reduction)

**Goal Owner**: Finance Director

**Goal Statement**: Reduce email infrastructure TCO from £2.95M to £2.15M annually (£800K savings) by eliminating on-premises Exchange costs within 12 months of go-live.

**Why This Matters**: Spending Review commitment to Treasury. NAO will audit value for money. Finance Director's performance objectives include IT cost reduction.

**Success Metrics**:
- **Primary Metric**: Annual TCO (target: £2.15M)
- **Secondary Metrics**:
  - Hardware maintenance eliminated (target: £0)
  - On-prem Exchange licensing terminated (target: £0)
  - Staff reallocation (target: 2.5 FTE to cloud ops)

**Baseline**: £2.95M annual TCO

**Target**: £2.15M annual TCO (27% reduction)

**Measurement Method**: Monthly financial reports, cost centre analysis, vendor invoices

**Dependencies**:
- Migration complete (G-1)
- On-premises hardware decommissioned (Month 11)
- Staff redeployed to cloud operations (Month 10)

**Risks to Achievement**:
- Extended parallel running increases temporary costs
- Scope creep adds features and costs
- Contingency overrun (budget £87.5K reserve)

---

### Goal G-3: Obtain SIRO Sign-Off for OFFICIAL-SENSITIVE Processing

**Derived From Drivers**: SD-3 (SIRO risk acceptance), SD-4 (CISO security posture)

**Goal Owner**: SIRO

**Goal Statement**: Document and implement security controls sufficient for SIRO to accept residual risk of processing OFFICIAL and OFFICIAL-SENSITIVE data in Microsoft cloud, with sign-off obtained before Phase 1 go-live.

**Why This Matters**: SIRO sign-off is a hard gate for production use of cloud services for OFFICIAL-SENSITIVE data. Without it, migration cannot proceed for sensitive directorates (Policy, Ministerial).

**Success Metrics**:
- **Primary Metric**: SIRO approval obtained (Yes/No)
- **Secondary Metrics**:
  - NCSC Cloud Security Principles compliance (target: 14/14)
  - Threat model complete (target: Yes)
  - Penetration test passed (target: No critical/high findings)
  - DLP policies validated (target: 100% OFFICIAL-SENSITIVE blocked externally)

**Baseline**: No cloud approval for OFFICIAL-SENSITIVE

**Target**: Full approval for OFFICIAL and OFFICIAL-SENSITIVE

**Measurement Method**: SIRO approval document signed, security control evidence pack

**Dependencies**:
- Sensitivity labels configured and tested (Month 2)
- DLP policies implemented (Month 2)
- CHECK penetration test completed (Month 3)
- Incident response playbook approved (Month 3)

**Risks to Achievement**:
- DLP misconfiguration in testing
- Penetration test finds critical issues
- SIRO requests additional controls delaying sign-off

---

### Goal G-4: Achieve 80%+ User Adoption Within 1 Month Post-Migration

**Derived From Drivers**: SD-7 (User minimal disruption), SD-8 (Change Manager adoption)

**Goal Owner**: Change Manager

**Goal Statement**: Achieve 80% user proficiency (measured by training completion and competency assessment) within 1 month of each migration phase, with user satisfaction NPS >70.

**Why This Matters**: Low adoption creates shadow IT, support burden, and reputational damage. Change Manager's performance objectives depend on adoption metrics. Previous SharePoint migration's 40% adoption is the benchmark to exceed.

**Success Metrics**:
- **Primary Metric**: User proficiency rate (target: 80%)
- **Secondary Metrics**:
  - Training completion (target: 100%)
  - M365 Champions active (target: 50)
  - User satisfaction NPS (target: 70)
  - Service desk ticket volume (target: <100/week within 4 weeks)

**Baseline**: N/A (new capability)

**Target**: 80% proficiency, NPS 70

**Measurement Method**: LMS completion reports, competency assessments, user surveys, ServiceNow ticket volume

**Dependencies**:
- Training materials developed (Month 2)
- M365 Champions recruited and trained (Month 2)
- Directorate release time for training (each phase)
- Executive communications sent (each phase)

**Risks to Achievement**:
- Compressed timeline limits training lead time
- Directorate resistance to mandatory training
- User anxiety about MFA

---

### Goal G-5: Zero Security Incidents During Migration

**Derived From Drivers**: SD-3 (SIRO), SD-4 (CISO), SD-6 (Business continuity)

**Goal Owner**: CISO

**Goal Statement**: Complete migration with zero security incidents (data breach, account compromise, service disruption from attack) through implementation of Zero Trust controls and enhanced threat protection.

**Why This Matters**: Security incident during migration would be career-ending for CISO and SIRO, trigger ICO investigation, potential parliamentary questions, and media coverage. Migration is high-risk period with temporary dual-environment complexity.

**Success Metrics**:
- **Primary Metric**: Security incidents (target: 0)
- **Secondary Metrics**:
  - MFA adoption (target: 100%)
  - Conditional Access policy compliance (target: 100%)
  - Phishing simulation success (target: <5% click rate)
  - DLP violations (target: 0 external OFFICIAL-SENSITIVE)

**Baseline**: 12 email security incidents in past year

**Target**: Zero incidents during migration (9 months)

**Measurement Method**: Security incident register, Defender for Office 365 dashboard, DLP reports

**Dependencies**:
- Defender for Office 365 enabled (Month 1)
- Conditional Access policies deployed (Month 2)
- User security awareness training (each phase)
- SOC monitoring configured (Month 2)

**Risks to Achievement**:
- Phishing campaign during migration
- Misconfigured Conditional Access causes gaps
- Temporary hybrid complexity creates attack surface

---

### Goal G-6: Maintain 99.9% Email Availability

**Derived From Drivers**: SD-6 (Business continuity), SD-7 (User minimal disruption)

**Goal Owner**: Exchange Administrator

**Goal Statement**: Maintain 99.9% email service availability throughout migration and post-go-live, with no unplanned outages exceeding 30 minutes during business hours.

**Why This Matters**: Email is critical communication channel. Previous IT changes caused outages that generated DG-level complaints. Directorate Heads are accountable for operational continuity. Microsoft SLA provides financial credits but reputation damage is unrecoverable.

**Success Metrics**:
- **Primary Metric**: Availability (target: 99.9%)
- **Secondary Metrics**:
  - Unplanned outages (target: 0 >30 min during business hours)
  - Migration-caused incidents (target: 0)
  - Rollback execution (target: <4 hours if needed)

**Baseline**: 98.5% (on-premises, last 12 months)

**Target**: 99.9% (Microsoft SLA)

**Measurement Method**: M365 Service Health dashboard, synthetic monitoring, user incident reports

**Dependencies**:
- Hybrid coexistence stable (Months 2-9)
- Weekend migration windows (minimal business impact)
- Rollback procedures tested (Month 3)
- DR procedures documented (Month 2)

**Risks to Achievement**:
- Microsoft service outage (beyond our control)
- Hybrid mail flow misconfiguration
- DNS/Autodiscover issues post-migration

---

## Goal-to-Outcome Mapping

### Outcome O-1: £800K Annual Cost Savings Realised

**Supported Goals**: G-1 (Migration complete), G-2 (Cost savings)

**Outcome Statement**: Achieve verified £800K annual cost reduction in email infrastructure TCO, validated by Finance and auditable by NAO.

**Measurement Details**:
- **KPI**: Annual TCO for email services
- **Current Value**: £2.95M/year
- **Target Value**: £2.15M/year
- **Measurement Frequency**: Monthly tracking, annual validation
- **Data Source**: Finance cost centre reports, vendor invoices, HR FTE records
- **Report Owner**: Finance Business Partner

**Business Value**:
- **Financial Impact**: £800K annual savings, £2.4M over 3 years
- **Strategic Impact**: Demonstrates value for money, supports Spending Review commitments
- **Operational Impact**: Eliminates hardware maintenance burden, reduces operational risk
- **Customer Impact**: None directly (internal infrastructure)

**Timeline**:
- **Phase 1 (Months 1-3)**: Investment phase (negative savings due to parallel running)
- **Phase 2 (Months 4-9)**: Migration phase (gradual cost reduction as phases complete)
- **Phase 3 (Months 10-12)**: Full savings (on-prem decommissioned)
- **Sustainment (Year 2+)**: £800K annual ongoing savings

**Stakeholder Benefits**:
- **Finance Director**: Meets Spending Review commitment, career success
- **CTO**: Avoids £500K hardware refresh, demonstrates cloud value
- **Treasury/NAO**: Evidence of efficient public spending

**Leading Indicators**:
- Migration phases completing on schedule
- On-prem infrastructure costs declining
- Staff redeployment progressing

**Lagging Indicators**:
- Annual TCO report showing £2.15M
- NAO audit confirmation
- Hardware disposal completed

---

### Outcome O-2: Enhanced Security Posture Validated

**Supported Goals**: G-3 (SIRO sign-off), G-4 (User adoption of security), G-5 (Zero incidents)

**Outcome Statement**: Achieve measurable improvement in security posture with zero security incidents, 100% MFA adoption, and successful CHECK assessment remediation.

**Measurement Details**:
- **KPI**: Microsoft Secure Score
- **Current Value**: 45/100 (estimated for on-prem equivalent)
- **Target Value**: 80/100
- **Measurement Frequency**: Weekly during migration, monthly post-migration
- **Data Source**: Microsoft Secure Score dashboard, Defender reports
- **Report Owner**: CISO

**Business Value**:
- **Financial Impact**: Avoided breach costs (average public sector breach: £3.2M)
- **Strategic Impact**: Enables future cloud adoption, builds trust
- **Operational Impact**: Reduced security incident response burden
- **Customer Impact**: Citizen data better protected

**Timeline**:
- **Phase 1 (Months 1-3)**: Baseline security controls deployed, Secure Score 60
- **Phase 2 (Months 4-6)**: Advanced controls tuned, Secure Score 70
- **Phase 3 (Months 7-12)**: Full Zero Trust, Secure Score 80
- **Sustainment (Year 2+)**: Maintain 80+ with continuous improvement

**Stakeholder Benefits**:
- **CISO**: CHECK findings remediated, career advancement
- **SIRO**: Acceptable residual risk, ministerial confidence
- **End Users**: Secure anywhere access, reduced phishing success

**Leading Indicators**:
- MFA enrollment rate increasing
- Phishing simulation click rates decreasing
- Conditional Access policy blocks (showing controls working)

**Lagging Indicators**:
- CHECK assessment passed (no high/critical findings)
- Zero security incidents over 12 months
- SIRO renewal of cloud approval

---

### Outcome O-3: User Satisfaction and Productivity Maintained

**Supported Goals**: G-4 (User adoption), G-6 (Availability)

**Outcome Statement**: Achieve user satisfaction NPS >70 and demonstrate productivity maintained or improved through adoption metrics and support volume normalisation.

**Measurement Details**:
- **KPI**: User Satisfaction NPS
- **Current Value**: 45 (baseline from annual IT survey)
- **Target Value**: 70
- **Measurement Frequency**: Monthly during migration, quarterly post-migration
- **Data Source**: User surveys, LMS reports, ServiceNow tickets
- **Report Owner**: Change Manager

**Business Value**:
- **Financial Impact**: Avoided productivity loss (estimated £2M if adoption fails)
- **Strategic Impact**: Builds confidence for future digital transformation
- **Operational Impact**: Reduced support burden, empowered users
- **Customer Impact**: Better internal service delivery to citizens

**Timeline**:
- **Phase 1 (Months 1-3)**: Pilot feedback positive (NPS 60)
- **Phase 2 (Months 4-6)**: Phase 1 users proficient (NPS 65)
- **Phase 3 (Months 7-9)**: All users migrated, training complete (NPS 70)
- **Sustainment (Year 2+)**: Continuous improvement (NPS 75+)

**Stakeholder Benefits**:
- **End Users**: Reliable email, mobile access, minimal disruption
- **Change Manager**: Adoption success, career validation
- **Directorate Heads**: Operational continuity, happy staff

**Leading Indicators**:
- Training completion rates
- OWA/mobile login adoption
- Service desk ticket trends

**Lagging Indicators**:
- NPS survey results
- Annual IT satisfaction survey improvement
- HR wellbeing survey (IT stress questions)

---

### Outcome O-4: Compliance Requirements Fully Met

**Supported Goals**: G-3 (SIRO sign-off)

**Outcome Statement**: Achieve and maintain compliance with all applicable regulations (GDPR, GSC, Public Records Act, WCAG) with zero compliance findings.

**Measurement Details**:
- **KPI**: Compliance audit findings
- **Current Value**: 3 findings (2024 CHECK assessment)
- **Target Value**: 0 critical/high findings
- **Measurement Frequency**: Annual CHECK, quarterly internal audit
- **Data Source**: Audit reports, Purview Compliance Score, accessibility audits
- **Report Owner**: SIRO

**Business Value**:
- **Financial Impact**: Avoided regulatory fines (ICO: up to £17.5M for GDPR breach)
- **Strategic Impact**: Trusted data handler, enables cross-government collaboration
- **Operational Impact**: Streamlined SAR processing, automated retention
- **Customer Impact**: Citizen data rights protected

**Timeline**:
- **Phase 1 (Months 1-3)**: Sensitivity labels and DLP configured
- **Phase 2 (Months 4-6)**: Retention policies applied, eDiscovery operational
- **Phase 3 (Months 7-12)**: Full compliance, CHECK assessment passed
- **Sustainment (Year 2+)**: Continuous compliance monitoring

**Stakeholder Benefits**:
- **DPO**: GDPR compliance assured, efficient SAR processing
- **SIRO**: Demonstrable compliance, ministerial confidence
- **Records Manager**: Automated retention, National Archives alignment

**Leading Indicators**:
- Purview Compliance Score trending up
- SAR response times improving
- DLP policy matches (showing detection working)

**Lagging Indicators**:
- CHECK assessment passed
- ICO no concerns
- Internal audit clean

---

## Complete Traceability Matrix

### Stakeholder → Driver → Goal → Outcome

| Stakeholder | Driver ID | Driver Summary | Goal ID | Goal Summary | Outcome ID | Outcome Summary |
|-------------|-----------|----------------|---------|--------------|------------|-----------------|
| CTO | SD-1 | Hardware deadline | G-1 | Complete migration Month 9 | O-1 | £800K savings |
| CTO | SD-1 | Hardware deadline | G-6 | 99.9% availability | O-3 | User satisfaction |
| Finance Director | SD-2 | Cost reduction | G-2 | £800K savings | O-1 | £800K savings |
| SIRO | SD-3 | Risk acceptance | G-3 | SIRO sign-off | O-2 | Security validated |
| SIRO | SD-3 | Risk acceptance | G-5 | Zero incidents | O-4 | Compliance met |
| CISO | SD-4 | Security posture | G-3 | SIRO sign-off | O-2 | Security validated |
| CISO | SD-4 | Security posture | G-5 | Zero incidents | O-2 | Security validated |
| DPO | SD-5 | GDPR compliance | G-3 | SIRO sign-off | O-4 | Compliance met |
| Directorate Heads | SD-6 | Business continuity | G-6 | 99.9% availability | O-3 | User satisfaction |
| End Users | SD-7 | Minimal disruption | G-4 | 80% adoption | O-3 | User satisfaction |
| End Users | SD-7 | Minimal disruption | G-6 | 99.9% availability | O-3 | User satisfaction |
| Change Manager | SD-8 | Adoption success | G-4 | 80% adoption | O-3 | User satisfaction |
| Service Desk | SD-9 | Manageable volume | G-4 | 80% adoption | O-3 | User satisfaction |
| Exchange Admin | SD-10 | Technical success | G-1 | Complete migration | O-1 | £800K savings |
| Exchange Admin | SD-10 | Technical success | G-6 | 99.9% availability | O-3 | User satisfaction |

### Conflict Analysis

**Competing Drivers**:

- **Conflict 1**: CTO (SD-1) wants aggressive timeline vs CISO (SD-4) wants thorough security testing
  - **Resolution Strategy**: Dedicated pilot phase (Month 3) with full security validation before Phase 1. Security sign-off is hard gate - timeline adjusts if needed. Accept 2-week buffer in schedule.

- **Conflict 2**: Finance (SD-2) wants cost containment vs Change Manager (SD-8) wants comprehensive training investment
  - **Resolution Strategy**: Training budget (£150K) already approved and non-negotiable. Demonstrate ROI through adoption metrics. Poor adoption is more expensive than training.

- **Conflict 3**: Directorate Heads (SD-6) want to be migrated last vs CTO (SD-1) needs to complete on schedule
  - **Resolution Strategy**: Finance pilots first (validates financial integrations). Ministerial offices last (as required). Middle phases negotiated with directorates based on blackout periods.

- **Conflict 4**: Exchange Admin (SD-10) wants extended testing vs CTO (SD-1) deadline pressure
  - **Resolution Strategy**: Pilot phase is non-negotiable testing time. Exchange Admin has authority to halt migration batch if issues arise. Career development plan agreed to address job security concerns.

**Synergies**:

- **Synergy 1**: SIRO (SD-3) and CISO (SD-4) drivers perfectly aligned - both want enhanced security controls. Achieving G-3 satisfies both.

- **Synergy 2**: End Users (SD-7) and Change Manager (SD-8) drivers aligned - good adoption satisfies both. Achieving G-4 creates win-win.

- **Synergy 3**: Finance (SD-2) and CTO (SD-1) drivers aligned - timely completion enables cost savings. G-1 and G-2 are interdependent.

- **Synergy 4**: Directorate Heads (SD-6), Service Desk (SD-9), and End Users (SD-7) all want smooth transition - G-4 and G-6 address all three.

---

## Communication & Engagement Plan

### CTO (Executive Sponsor)

**Primary Message**: Migration is on track to meet Month 9 deadline and avoid hardware refresh costs. Key risks are being actively managed.

**Key Talking Points**:
- Pilot success validates approach and timeline
- £800K savings will begin Month 10 as planned
- Security sign-off on track, no blockers anticipated
- Board update ready for monthly steering committee

**Communication Frequency**: Weekly (steering committee), Daily (during critical phases)

**Preferred Channel**: Steering committee meetings, 1:1 briefings, executive dashboard

**Success Story**: "Pilot completed on time with zero data loss, SIRO signed off on security controls, first £200K savings already visible in budget."

---

### Finance Director

**Primary Message**: Migration will deliver committed £800K savings. Costs are within budget with contingency intact.

**Key Talking Points**:
- Monthly cost tracking shows project within £962.5K budget
- On-prem costs declining as phases complete
- NAO audit-ready documentation being maintained
- Savings realisation timeline confirmed

**Communication Frequency**: Monthly (cost review), Quarterly (board finance report)

**Preferred Channel**: Monthly financial reports, cost dashboard, 1:1 briefings

**Success Story**: "Migration delivered £823K savings (3% above target), NAO acknowledged value for money in digital transformation audit."

---

### SIRO

**Primary Message**: Security controls meet or exceed on-premises protection. Residual risk is acceptable for OFFICIAL and OFFICIAL-SENSITIVE processing.

**Key Talking Points**:
- All 14 NCSC Cloud Security Principles addressed
- CHECK penetration test passed with no critical findings
- DLP preventing OFFICIAL-SENSITIVE external disclosure (tested)
- Incident response playbook aligned with NCSC guidance

**Communication Frequency**: Monthly (risk review), Ad-hoc (significant findings)

**Preferred Channel**: Risk committee, security briefings, SIRO pack

**Success Story**: "Zero security incidents during migration. CHECK assessment shows improved security posture. ICO satisfied with GDPR controls."

---

### End Users

**Primary Message**: Email is getting better - more reliable, accessible anywhere, with the same familiar Outlook interface. Training will help you get the most from new features.

**Key Talking Points**:
- Outlook looks and works the same
- Access email from any device, anywhere
- MFA keeps your account secure (one-time setup)
- Help is available: Champions, Service Desk, guides

**Communication Frequency**: Pre-migration (2 weeks), During (daily tips), Post (weekly for 1 month)

**Preferred Channel**: Intranet, email, Teams, digital signage, drop-in sessions

**Success Story**: "I can now check emails on my phone when working from home, and the new security features stopped a phishing email that would have got through before."

---

## Change Impact Assessment

### Impact on Stakeholders

| Stakeholder | Current State | Future State | Change Magnitude | Resistance Risk | Mitigation Strategy |
|-------------|---------------|--------------|------------------|-----------------|---------------------|
| End Users | On-prem Outlook, no MFA, limited mobile | Cloud Outlook, MFA, full mobile | MEDIUM | MEDIUM | Training, Champions, gradual rollout |
| Exchange Admin | On-prem management, server maintenance | Cloud admin, no servers, new tools | HIGH | MEDIUM | Certification training, career path |
| Service Desk | Exchange troubleshooting, on-prem tools | M365 admin, cloud tools, new issues | MEDIUM | LOW | Training, runbooks, escalation paths |
| IT Operations | Server maintenance, patching, backups | Cloud monitoring, IaC, no hardware | HIGH | MEDIUM | Redeployment to cloud ops, training |
| Directorate Heads | Status quo, known processes | Scheduling disruption, staff training | LOW | LOW | Early engagement, flexible scheduling |
| CISO | On-prem security tools | New security stack, more visibility | MEDIUM | LOW | Training, Microsoft engagement |

### Change Readiness

**Champions** (Enthusiastic supporters):
- **CTO**: Driving cloud transformation, career legacy
- **CISO**: Sees security improvement opportunity
- **M365 Champions (50)**: Early adopters, peer influence

**Fence-sitters** (Neutral, need convincing):
- **Directorate Heads**: Will support if disruption minimised
- **Finance Director**: Will support if costs controlled
- **End Users (majority)**: Will adapt with adequate training and support

**Resisters** (Opposed or sceptical):
- **Some End Users**: Fear of change, MFA friction - address through training and patience
- **IT Operations (some)**: Job security concerns - address through redeployment plan and training
- **Exchange Admin (initial)**: Testing time concerns - addressed through pilot phase commitment

---

## Risk Register (Stakeholder-Related)

### Risk R-STK-1: SIRO Withholds Sign-Off

**Related Stakeholders**: SIRO, CISO, CTO

**Risk Description**: SIRO refuses to accept residual risk for OFFICIAL-SENSITIVE in cloud, blocking migration of sensitive directorates.

**Impact on Goals**: G-1 (timeline), G-3 (sign-off)

**Probability**: LOW (controls are strong)

**Impact**: HIGH (blocks Phase 2-3)

**Mitigation Strategy**: Early engagement with SIRO, security evidence pack, pilot demonstrates controls, Microsoft security assurance materials.

**Contingency Plan**: Migrate OFFICIAL-only users first, continue remediation, escalate to CTO for risk acceptance decision.

---

### Risk R-STK-2: User Resistance Causes Adoption Failure

**Related Stakeholders**: End Users, Change Manager, Service Desk

**Risk Description**: Users resist MFA/change, adoption falls below 50%, shadow IT emerges, support overwhelmed.

**Impact on Goals**: G-4 (adoption), O-3 (satisfaction)

**Probability**: MEDIUM

**Impact**: MEDIUM

**Mitigation Strategy**: Executive communications, M365 Champions, extensive training, address concerns proactively, feedback loops.

**Contingency Plan**: Extended training period, additional Service Desk resources, directorate-by-directorate remediation.

---

### Risk R-STK-3: Directorate Scheduling Conflicts

**Related Stakeholders**: Directorate Heads, CTO

**Risk Description**: Conflicting blackout periods leave insufficient migration windows, timeline slips.

**Impact on Goals**: G-1 (timeline)

**Probability**: MEDIUM

**Impact**: MEDIUM

**Mitigation Strategy**: Early scheduling negotiation (Month 2), flexible weekend windows, accept some directorates' preferences.

**Contingency Plan**: Extend weekday evening migrations (with overtime), add additional parallel migration streams.

---

### Risk R-STK-4: Exchange Admin Knowledge Gap

**Related Stakeholders**: Exchange Admin, CTO

**Risk Description**: Technical lead lacks cloud expertise, migration errors occur, timeline slips.

**Impact on Goals**: G-1 (timeline), G-6 (availability)

**Probability**: LOW (training planned)

**Impact**: HIGH

**Mitigation Strategy**: Microsoft certification training (Month 1), vendor technical support, Microsoft Premier Support engaged, peer review of configurations.

**Contingency Plan**: Escalate to migration vendor for hands-on delivery, Microsoft FastTrack engagement.

---

### Risk R-STK-5: Finance Cuts Training Budget

**Related Stakeholders**: Finance Director, Change Manager

**Risk Description**: Mid-project budget pressure causes training budget reduction, adoption suffers.

**Impact on Goals**: G-4 (adoption)

**Probability**: LOW (budget approved)

**Impact**: HIGH

**Mitigation Strategy**: Training budget ring-fenced, demonstrate ROI through pilot metrics, escalate to CTO if threatened.

**Contingency Plan**: Shift to more self-service training (Microsoft Learn), rely more heavily on Champions network.

---

## Governance & Decision Rights

### Decision Authority Matrix (RACI)

| Decision Type | Responsible | Accountable | Consulted | Informed |
|---------------|-------------|-------------|-----------|----------|
| Project budget approval | Finance Director | CTO | PMO | All stakeholders |
| Migration timeline | Project Manager | CTO | Directorate Heads, Exchange Admin | All |
| Security architecture | CISO | SIRO | Enterprise Architect, DPO | CTO |
| Security sign-off | SIRO | SIRO | CISO, DPO | CTO, Directorate Heads |
| DLP/Sensitivity label config | InfoGov Lead | SIRO | CISO, DPO | Directorate Heads |
| Migration phase schedule | Change Manager | CTO | Directorate Heads | End Users |
| Training approach | Change Manager | CTO | HR, Directorate Heads | End Users |
| Technical configuration | Exchange Admin | Enterprise Architect | CISO, IT Ops | Migration Vendor |
| Go/No-go for each phase | CTO | CTO | SIRO, CISO, Change Manager | All |
| Rollback decision | Exchange Admin | CTO | CISO, Directorate Heads | All |
| On-prem decommission | IT Operations | CTO | Finance, Exchange Admin | All |

### Escalation Path

1. **Level 1**: Project Manager / Exchange Admin (day-to-day decisions, technical issues)
2. **Level 2**: Steering Committee (scope changes, timeline variances, resource conflicts)
3. **Level 3**: CTO (strategic direction, major conflicts, budget overruns >10%)
4. **Level 4**: Permanent Secretary (cross-departmental issues, ministerial involvement)

---

## Validation & Sign-off

### Stakeholder Review

| Stakeholder | Review Date | Comments | Status |
|-------------|-------------|----------|--------|
| CTO | PENDING | | PENDING |
| Finance Director | PENDING | | PENDING |
| SIRO | PENDING | | PENDING |
| CISO | PENDING | | PENDING |
| DPO | PENDING | | PENDING |
| Enterprise Architect | PENDING | | PENDING |
| Change Manager | PENDING | | PENDING |

### Document Approval

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Executive Sponsor (CTO) | | | |
| SIRO | | | |
| Enterprise Architect | | | |

---

## Appendices

### Appendix A: Stakeholder Interview Summaries

#### Interview with CTO - 2026-01-15

**Key Points**:
- Hardware deadline is hard constraint, cannot extend
- Board has approved cloud strategy, expects delivery
- Willing to provide executive air cover for difficult decisions

**Quotes**:
- "We cannot under any circumstances end up buying new Exchange servers. That's £500K we don't have and sends completely the wrong message about our cloud strategy."

**Follow-up Actions**:
- Weekly steering committee meetings established
- Escalation path confirmed

---

#### Interview with SIRO - 2026-01-16

**Key Points**:
- Needs documented evidence for risk acceptance
- Concerned about OFFICIAL-SENSITIVE in shared cloud infrastructure
- Wants DLP tested extensively before sign-off

**Quotes**:
- "I need to be able to look a Minister in the eye and say we've done everything reasonable to protect their communications."

**Follow-up Actions**:
- Security evidence pack to be prepared
- DLP testing plan agreed

---

#### Interview with Finance Director - 2026-01-17

**Key Points**:
- £800K savings committed to Treasury
- Contingency must remain intact
- Wants monthly cost visibility

**Quotes**:
- "The NAO will audit this. I need to be able to demonstrate value for money with clear documentation."

**Follow-up Actions**:
- Monthly cost reporting established
- Benefits realisation tracking agreed

---

### Appendix B: Survey Results

**Pre-Migration User Survey (n=350, 10% sample)**

| Question | Result |
|----------|--------|
| Comfort with current email system | 78% satisfied |
| Interest in mobile email access | 65% want mobile |
| Concerns about change | 45% have concerns |
| Top concern | "Learning new system" (32%) |
| Preferred training format | Video tutorials (40%), Written guides (30%), Drop-in sessions (30%) |

---

### Appendix C: References

- Cabinet Office M365 Architecture Principles v1.1 (.arckit/memory/architecture-principles.md)
- Exchange Online Migration Requirements (projects/001/requirements.md)
- UK Government Technology Code of Practice (TCoP)
- GDS Service Standard (14 points)
- NCSC Cloud Security Principles
- Government Security Classifications Policy
- Microsoft M365 Security and Compliance Documentation

---

**Generated by**: ArcKit `/arckit.stakeholders` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.1
**Project**: Exchange Online Migration to Microsoft 365 (Project 001)
**AI Model**: Claude Opus 4.5

---

*This document is OFFICIAL and should be handled in accordance with Government Security Classifications Policy.*
