# Vendor Evaluation Criteria: Exchange Online Migration to Microsoft 365

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.evaluate`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-EVAL-v1.1 |
| **Document Type** | Vendor Evaluation Criteria |
| **Project** | Exchange Online Migration to Microsoft 365 (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2026-01-23 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | On-Demand |
| **Next Review Date** | Prior to vendor selection |
| **Owner** | Cabinet Office IT Directorate |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Evaluation Committee, Procurement Team |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-01-23 | ArcKit AI | Initial creation from `/arckit.evaluate` command | PENDING | PENDING |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to align with ArcKit template v0.11.2 | PENDING | PENDING |

## Document Purpose

This document defines the evaluation criteria, scoring methodology, and process for assessing vendor proposals responding to RFP-CAB-2025-001 for the Exchange Online Migration project. The framework ensures objective, transparent, and auditable selection of the migration partner that provides best value while meeting Cabinet Office security, compliance, and delivery requirements.

---

## 1. Evaluation Overview

### 1.1 Purpose

This document establishes the vendor evaluation framework for the Cabinet Office Exchange Online Migration project. The goal is to select a migration partner that:
- Delivers zero-data-loss migration of 3,500 mailboxes to Exchange Online
- Meets UK Government security and compliance requirements (OFFICIAL/OFFICIAL-SENSITIVE)
- Complies with UK data sovereignty requirements (UK South/UK West regions only)
- Provides best value for public money
- Demonstrates proven M365 migration expertise in UK Government context

### 1.2 Evaluation Principles

- **Objective**: All criteria are measurable and consistently applied across vendors
- **Transparent**: Vendors understand evaluation criteria via published RFP (SOW Section 6)
- **Fair**: All compliant vendors evaluated against identical criteria
- **Documented**: All scores and rationale captured for audit and debrief purposes
- **Value-Based**: Best value for public money, not necessarily lowest cost
- **Aligned**: Evaluation aligns with Cabinet Office Architecture Principles and TCoP

### 1.3 Evaluation Team

| Name | Role | Department | Evaluation Focus |
|------|------|------------|------------------|
| [Name] | Evaluation Lead | Procurement | Process orchestration, compliance, final scoring |
| [Name] | Technical Evaluator | Enterprise Architecture | Architecture alignment, technical solution design |
| [Name] | Technical Evaluator | IT Security / CISO Office | Security controls, NCSC compliance, threat assessment |
| [Name] | Technical Evaluator | Exchange Administration | Migration methodology, Exchange expertise |
| [Name] | Business Evaluator | IT Directorate (Business Owner) | Requirements understanding, user impact |
| [Name] | Business Evaluator | Finance | Cost evaluation, value for money assessment |
| [Name] | Observer (non-voting) | Legal | Contract terms, DPA compliance, liability review |
| [Name] | Observer (non-voting) | Information Governance | Data classification, retention, GDPR compliance |

### 1.4 Conflict of Interest Declaration

All evaluators MUST complete a conflict of interest declaration before participating:

- [ ] No personal relationships with vendor employees
- [ ] No financial interests in vendor companies (shares, benefits)
- [ ] No prior employment with vendor (within 3 years)
- [ ] No concurrent consulting or advisory arrangements
- [ ] No family members employed by vendor

Evaluators with conflicts MUST recuse themselves from evaluation of that vendor. Declarations retained for 7 years per OFFICIAL records retention.

---

## 2. Evaluation Process

### 2.1 Process Flow

```
1. Proposals Received (Due: 2025-12-15 at 17:00 GMT)
   |
2. Mandatory Qualifications Check (Pass/Fail)
   | (Qualified vendors proceed)
3. Individual Technical Scoring (Blind to Cost)
   |
4. Consensus Technical Scoring Meeting
   |
5. Shortlist Top 3 Vendors (Minimum Technical Score: 70/100)
   |
6. Cost Proposals Opened (Shortlisted only)
   |
7. Cost Scoring and Value Assessment
   |
8. Combined Technical + Cost Scoring (70/30 weighting)
   |
9. Vendor Presentations & Demo (Shortlisted vendors)
   |
10. Reference Checks (All 3 required references contacted)
    |
11. Final Scoring & Selection Recommendation
    |
12. Approval (CTO, SIRO, Executive Sponsor)
    |
13. Contract Award & Unsuccessful Vendor Notification
```

### 2.2 Timeline

| Phase | Duration | Target Date | Responsible |
|-------|----------|-------------|-------------|
| Proposals Due | - | 2025-12-15 | Vendors |
| Mandatory Qualifications Check | 3 days | 2025-12-18 | Procurement |
| Individual Technical Scoring | 10 days | 2026-01-03 | All evaluators |
| Consensus Meeting | 1 day | 2026-01-06 | Evaluation committee |
| Shortlist Decision | 1 day | 2026-01-07 | Evaluation Lead |
| Cost Evaluation | 3 days | 2026-01-10 | Finance |
| Combined Scoring | 2 days | 2026-01-14 | Evaluation committee |
| Vendor Presentations | 1 week | 2026-01-17 to 2026-01-24 | Shortlisted vendors |
| Reference Checks | 1 week | 2026-01-24 to 2026-01-31 | Evaluation team |
| Final Scoring | 2 days | 2026-02-03 | Evaluation committee |
| Selection Decision | 1 day | 2026-02-04 | CTO, Executive Sponsor |
| Approval & Contract Award | 5 days | 2026-02-11 | Procurement, Legal |
| Vendor Notification | 2 days | 2026-02-13 | Procurement |

---

## 3. Mandatory Qualifications (Pass/Fail)

Before scoring, vendors MUST meet ALL mandatory qualifications. Failure on ANY item results in immediate disqualification. No exceptions.

### 3.1 Company Qualifications

| ID | Qualification | Verification Method | Pass/Fail |
|----|---------------|---------------------|-----------|
| **MQ-001** | Microsoft Gold/Solutions Partner for Modern Work (Cloud Productivity competency) | Microsoft Partner Portal verification | [ ] Pass [ ] Fail |
| **MQ-002** | Minimum 5 years experience delivering Exchange Online migrations | Company history, case studies | [ ] Pass [ ] Fail |
| **MQ-003** | Minimum 3 UK Government/Public Sector migration projects of similar scale (2,000+ mailboxes) | Reference projects with client names | [ ] Pass [ ] Fail |
| **MQ-004** | Cyber Essentials Plus certification (current) | NCSC certificate verification | [ ] Pass [ ] Fail |
| **MQ-005** | ISO 27001 certification (current) | Certificate copy, UKAS verification | [ ] Pass [ ] Fail |
| **MQ-006** | UK-registered company or UK subsidiary with UK-based delivery team | Companies House registration | [ ] Pass [ ] Fail |
| **MQ-007** | Financial stability (3 years audited accounts, positive net assets) | Financial statements review | [ ] Pass [ ] Fail |
| **MQ-008** | Professional Indemnity Insurance minimum GBP 5M | Insurance certificate | [ ] Pass [ ] Fail |
| **MQ-009** | All key personnel BPSS clearable (UK nationals or residents with right to work) | Personnel declarations | [ ] Pass [ ] Fail |

### 3.2 Proposal Compliance

| ID | Qualification | Verification Method | Pass/Fail |
|----|---------------|---------------------|-----------|
| **MQ-010** | Proposal submitted by deadline (2025-12-15 17:00 GMT) | Submission timestamp | [ ] Pass [ ] Fail |
| **MQ-011** | Proposal follows required format (Annexes A-F as specified in SOW) | Format compliance check | [ ] Pass [ ] Fail |
| **MQ-012** | All required sections completed (no blank sections) | Completeness review | [ ] Pass [ ] Fail |
| **MQ-013** | Cost proposal submitted separately from technical proposal | Sealed/separate submission | [ ] Pass [ ] Fail |
| **MQ-014** | Key personnel CVs included (Project Manager, Technical Lead, Security Lead) | CV presence and completeness | [ ] Pass [ ] Fail |
| **MQ-015** | Three client references provided with contact details | Reference section complete | [ ] Pass [ ] Fail |
| **MQ-016** | Signed acceptance of Cabinet Office General Terms and Conditions | Signed declaration | [ ] Pass [ ] Fail |
| **MQ-017** | Signed Data Processing Agreement (DPA) and GDPR compliance declaration | Signed DPA | [ ] Pass [ ] Fail |

### 3.3 Disqualification Procedure

1. Evaluator identifies mandatory qualification failure
2. Evaluation Lead confirms failure with second reviewer
3. Vendor notified of disqualification with specific reason within 5 business days
4. Vendor may provide clarification within 48 hours ONLY if failure was due to ambiguity or omission (not substantive non-compliance)
5. Final determination by Evaluation Lead (decision is final)
6. Disqualification documented and retained for audit

---

## 4. Technical Evaluation Criteria (100 Points)

Technical proposals are scored **blind to cost** to ensure unbiased evaluation. Technical score minimum threshold: **70/100** required to proceed to cost evaluation.

### 4.1 Criteria Summary

| Category | Weight | Max Points | Primary Evaluator(s) |
|----------|--------|------------|----------------------|
| **1. Migration Methodology and Technical Approach** | 35% | 35 | Technical evaluators |
| **2. Security, Compliance, and Data Protection** | 25% | 25 | Security evaluator |
| **3. Team Qualifications and Experience** | 20% | 20 | All evaluators |
| **4. Project Management and Risk Approach** | 10% | 10 | Business evaluators |
| **5. Relevant Experience and References** | 10% | 10 | Business evaluators |
| **TOTAL** | **100%** | **100** | |

---

### 4.2 Category 1: Migration Methodology and Technical Approach (35 points)

**Purpose**: Evaluate the proposed migration approach, Exchange Online expertise, and alignment with Cabinet Office architecture principles.

#### Subcriteria

| ID | Subcriterion | Points | Evaluation Questions |
|----|--------------|--------|---------------------|
| **1.1** | **Hybrid Migration Strategy** | 10 | - Is the Exchange Hybrid configuration approach sound (certificate management, MRS endpoint, Organization Config)?<br>- Does the proposal demonstrate understanding of co-existence requirements (6-month hybrid period)?<br>- Is the Autodiscover cutover plan clear and tested?<br>- Is cross-premises mailbox move experience demonstrated? |
| **1.2** | **Data Integrity and Validation** | 8 | - How will 100% data integrity (zero data loss) be achieved and validated?<br>- What validation tools and methodology will be used (item count, folder structure, calendar accuracy)?<br>- How are edge cases handled (corrupted items, oversized items, calendar conflicts)?<br>- What is the post-migration validation process and SLA? |
| **1.3** | **Migration Tooling and Performance** | 7 | - What migration tools are proposed (native MRS, BitTitan, Quest, other)?<br>- How will 300 mailboxes/weekend throughput target be achieved?<br>- How are large mailboxes (>50GB) handled within weekend windows?<br>- What bandwidth management approach is proposed (throttling, scheduling)? |
| **1.4** | **Azure AD and Identity Integration** | 5 | - Is Azure AD Connect implementation approach sound?<br>- How are Conditional Access policies migrated/configured?<br>- Is MFA and device compliance rollout planned?<br>- How is hybrid identity transition managed (UPN, password sync)? |
| **1.5** | **Rollback and Contingency Planning** | 5 | - Is rollback procedure credible (30-day mailbox retention)?<br>- What triggers rollback and who makes the decision?<br>- How is partial migration failure handled (individual mailbox vs batch)?<br>- What contingency exists for Microsoft service outages during migration windows? |

#### Architecture Principle Alignment (Bonus: +3 points)

Bonus points awarded for explicit demonstration of alignment with Cabinet Office Architecture Principles:
- **Principle 1** (Cloud-First with UK Sovereignty): UK data residency approach
- **Principle 10** (Infrastructure as Code): M365DSC or equivalent configuration management
- **Principle 11** (Zero Trust): Conditional Access and MFA approach

#### Scoring Rubric

| Score | Description |
|-------|-------------|
| **Excellent (90-100%)** | Exceeds expectations; innovative approach; demonstrates deep M365 migration expertise; minimal risks; clearly meets all requirements |
| **Good (75-89%)** | Meets all expectations; sound methodology; minor concerns or areas requiring clarification |
| **Adequate (60-74%)** | Meets most expectations; workable approach; some gaps or concerns requiring discussion |
| **Weak (40-59%)** | Meets minimum expectations; significant concerns; substantial gaps or unproven methodology |
| **Unacceptable (0-39%)** | Does not meet expectations; major flaws; unworkable approach; critical requirements not addressed |

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 1.1 Hybrid Migration Strategy | 10 | ___ | |
| 1.2 Data Integrity and Validation | 8 | ___ | |
| 1.3 Migration Tooling and Performance | 7 | ___ | |
| 1.4 Azure AD and Identity Integration | 5 | ___ | |
| 1.5 Rollback and Contingency Planning | 5 | ___ | |
| Architecture Principle Alignment (Bonus) | +3 | ___ | |
| **Category 1 Total** | **35 (+3)** | **___** | |

---

### 4.3 Category 2: Security, Compliance, and Data Protection (25 points)

**Purpose**: Evaluate the vendor's approach to security controls, UK Government compliance requirements, and data protection. This category reflects the NON-NEGOTIABLE nature of security requirements.

#### Subcriteria

| ID | Subcriterion | Points | Evaluation Questions |
|----|--------------|--------|---------------------|
| **2.1** | **OFFICIAL/OFFICIAL-SENSITIVE Data Handling** | 8 | - Does vendor demonstrate understanding of UK Government Security Classifications?<br>- How will sensitivity labels (OFFICIAL, OFFICIAL-SENSITIVE) be configured and tested?<br>- How is OFFICIAL-SENSITIVE data protected during migration (encryption in transit)?<br>- What controls prevent unauthorized disclosure during migration? |
| **2.2** | **Microsoft Purview Configuration (DLP, Labels)** | 6 | - Is DLP policy configuration approach comprehensive?<br>- How are sensitivity labels tested before go-live?<br>- What approach for auto-labeling rules?<br>- How are DLP incidents monitored and responded to? |
| **2.3** | **Defender for Office 365 Configuration** | 4 | - Is Safe Links/Safe Attachments configuration approach sound?<br>- How is anti-phishing/impersonation protection configured?<br>- How are threat policies tested and validated?<br>- What security monitoring is proposed during migration? |
| **2.4** | **Audit Logging and SIEM Integration** | 4 | - How is 7-year UAL retention configured?<br>- Is Microsoft Sentinel integration approach credible?<br>- What security monitoring is active during migration windows?<br>- How are security incidents escalated during migration? |
| **2.5** | **Vendor Security Practices** | 3 | - What security clearances do vendor staff hold (BPSS/SC)?<br>- How does vendor secure their own systems and access to Cabinet Office tenant?<br>- What data handling procedures during migration (no local copies, encrypted connections)?<br>- How are privileged credentials managed (no password sharing, PIM)? |

#### Mandatory Security Requirements Verification

The following requirements from NFR-SEC-001 through NFR-SEC-005 must be explicitly addressed:

- [ ] MFA enforcement for all migration activities
- [ ] TLS 1.3 for all data in transit
- [ ] No data stored outside UK regions (UK South/UK West)
- [ ] All vendor access via Azure AD with Conditional Access
- [ ] Privileged access via PIM with audit trail
- [ ] CHECK penetration testing support (if required)

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 2.1 OFFICIAL/OFFICIAL-SENSITIVE Data Handling | 8 | ___ | |
| 2.2 Microsoft Purview Configuration (DLP, Labels) | 6 | ___ | |
| 2.3 Defender for Office 365 Configuration | 4 | ___ | |
| 2.4 Audit Logging and SIEM Integration | 4 | ___ | |
| 2.5 Vendor Security Practices | 3 | ___ | |
| **Category 2 Total** | **25** | **___** | |

---

### 4.4 Category 3: Team Qualifications and Experience (20 points)

**Purpose**: Evaluate the vendor's team expertise, certifications, and ability to deliver this specific migration.

#### Subcriteria

| ID | Subcriterion | Points | Evaluation Questions |
|----|--------------|--------|---------------------|
| **3.1** | **Key Personnel Qualifications** | 8 | - Does Project Manager have PMP/PRINCE2 and 5+ years PM experience?<br>- Does Technical Lead have Microsoft certifications (MS-100, MS-101, MS-203)?<br>- Does Security Lead have security certifications (CISSP, CISM, or equivalent)?<br>- Are CVs comprehensive with relevant M365 migration experience? |
| **3.2** | **UK Government Experience** | 5 | - Has team delivered UK Government M365 migrations (not just private sector)?<br>- Do team members understand Government Security Classifications?<br>- Is there experience with GDS Service Standard and TCoP?<br>- Have team members worked at OFFICIAL or OFFICIAL-SENSITIVE level? |
| **3.3** | **Team Size and Allocation** | 4 | - Is team size adequate for migration scope (3,500 mailboxes)?<br>- Are key personnel dedicated (not spread across multiple projects)?<br>- Is on-site vs remote split appropriate?<br>- Are weekend/out-of-hours resources committed for migration windows? |
| **3.4** | **Knowledge Transfer and Handover** | 3 | - Is knowledge transfer plan credible?<br>- How will Cabinet Office IT team be trained?<br>- What documentation will be provided (runbooks, configuration guides)?<br>- Is there a warranty/support period post-migration? |

#### Required Certifications Verification

| Role | Required Certifications | Verification |
|------|------------------------|--------------|
| Project Manager | PMP or PRINCE2 Practitioner | Certificate copy |
| Technical Lead | MS-100, MS-101, MS-203 or equivalent | Microsoft certification transcript |
| Security Lead | CISSP, CISM, CompTIA Security+, or equivalent | Certificate copy |
| Migration Engineer(s) | MS-203 (Messaging Administrator) | Microsoft certification transcript |

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 3.1 Key Personnel Qualifications | 8 | ___ | |
| 3.2 UK Government Experience | 5 | ___ | |
| 3.3 Team Size and Allocation | 4 | ___ | |
| 3.4 Knowledge Transfer and Handover | 3 | ___ | |
| **Category 3 Total** | **20** | **___** | |

---

### 4.5 Category 4: Project Management and Risk Approach (10 points)

**Purpose**: Evaluate the vendor's project management methodology, risk management, and governance approach.

#### Subcriteria

| ID | Subcriterion | Points | Evaluation Questions |
|----|--------------|--------|---------------------|
| **4.1** | **Project Methodology and Timeline** | 4 | - Is proposed methodology (Agile/Waterfall/Hybrid) appropriate for phased migration?<br>- Is 9-month timeline achievable with proposed approach?<br>- Are milestones meaningful and aligned with SOW phases (Pilot, Phase 1-3)?<br>- Is change freeze (Q4 Jan-Mar 2026) accommodated? |
| **4.2** | **Risk Management** | 3 | - Are key migration risks identified proactively (R-001 to R-008 from requirements)?<br>- Are mitigation strategies credible and specific?<br>- How are risks monitored and escalated?<br>- What risk contingency is built into timeline? |
| **4.3** | **Governance and Communication** | 3 | - Is governance structure appropriate (steering committee, working groups)?<br>- Is communication plan clear (weekly status, escalation path)?<br>- How is executive stakeholder engagement managed?<br>- What RAID log and reporting tools are proposed? |

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 4.1 Project Methodology and Timeline | 4 | ___ | |
| 4.2 Risk Management | 3 | ___ | |
| 4.3 Governance and Communication | 3 | ___ | |
| **Category 4 Total** | **10** | **___** | |

---

### 4.6 Category 5: Relevant Experience and References (10 points)

**Purpose**: Evaluate the vendor's track record delivering similar UK Government M365 migrations.

#### Subcriteria

| ID | Subcriterion | Points | Evaluation Questions |
|----|--------------|--------|---------------------|
| **5.1** | **Reference Project Relevance** | 6 | - Are reference projects similar in scale (2,000+ mailboxes)?<br>- Are reference projects UK Government/Public Sector?<br>- Do references demonstrate OFFICIAL data handling?<br>- Were projects delivered on time and within budget? |
| **5.2** | **UK Government and Public Sector Experience** | 4 | - Does vendor have significant UK Government client base?<br>- Do they understand Cabinet Office operating context?<br>- Is there experience with cross-government collaboration (gov.uk)?<br>- Do they have existing G-Cloud framework agreements? |

#### Reference Project Evaluation Matrix

For each reference project, evaluate:

| Reference | Project Scale | Government/Public Sector? | Data Classification | On Time? | On Budget? | Would Rehire? |
|-----------|--------------|---------------------------|---------------------|----------|------------|---------------|
| Reference 1 | [X] mailboxes | [ ] Gov [ ] Public [ ] Private | [ ] OFFICIAL [ ] OFFICIAL-SENSITIVE | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] Maybe [ ] No |
| Reference 2 | [X] mailboxes | [ ] Gov [ ] Public [ ] Private | [ ] OFFICIAL [ ] OFFICIAL-SENSITIVE | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] Maybe [ ] No |
| Reference 3 | [X] mailboxes | [ ] Gov [ ] Public [ ] Private | [ ] OFFICIAL [ ] OFFICIAL-SENSITIVE | [ ] Yes [ ] No | [ ] Yes [ ] No | [ ] Yes [ ] Maybe [ ] No |

#### Scoring Template

**Vendor Name**: _______________

| Subcriterion | Max Points | Score | Justification |
|--------------|------------|-------|---------------|
| 5.1 Reference Project Relevance | 6 | ___ | |
| 5.2 UK Government and Public Sector Experience | 4 | ___ | |
| **Category 5 Total** | **10** | **___** | |

---

### 4.7 Technical Scoring Summary

**Vendor Name**: _______________

| Category | Max Points | Score | Percentage |
|----------|------------|-------|------------|
| 1. Migration Methodology and Technical Approach | 35 (+3 bonus) | ___ | ___% |
| 2. Security, Compliance, and Data Protection | 25 | ___ | ___% |
| 3. Team Qualifications and Experience | 20 | ___ | ___% |
| 4. Project Management and Risk Approach | 10 | ___ | ___% |
| 5. Relevant Experience and References | 10 | ___ | ___% |
| **TOTAL TECHNICAL SCORE** | **100 (+3)** | **___** | **___%** |

**Minimum Technical Threshold**: 70/100 required to proceed to cost evaluation.

**Technical Evaluation Outcome**:
- [ ] QUALIFIED (Score >= 70): Proceed to cost evaluation
- [ ] NOT QUALIFIED (Score < 70): Eliminated from consideration

---

## 5. Cost Evaluation

Cost proposals are opened ONLY for vendors achieving technical score >= 70/100.

### 5.1 Cost Scoring Methodology

**Method**: Lowest Price Technically Acceptable (LPTA) variant with Value Assessment

**Formula**:
```
Cost Score = (Lowest Compliant Price / Vendor Price) x 100
```

- Lowest cost proposal among qualified vendors receives 100 points
- Other proposals scaled proportionally
- Proposals exceeding budget cap (GBP 1.2M) are non-compliant

### 5.2 Cost Breakdown Requirements

Vendors must provide cost breakdown per SOW Section 5:

| Cost Category | Vendor Proposal | Budget Allocation | Notes |
|---------------|-----------------|-------------------|-------|
| Professional Services (Migration) | GBP ___ | GBP 300,000 | |
| Project Management | GBP ___ | GBP 200,000 | |
| Training and Change Management | GBP ___ | GBP 150,000 | |
| Testing and Validation | GBP ___ | GBP 50,000 | |
| Security and Compliance | GBP ___ | GBP 100,000 | |
| Tools and Licensing | GBP ___ | Included | e.g., BitTitan |
| Contingency | GBP ___ | GBP 87,500 | 10% reserve |
| **TOTAL** | **GBP ___** | **GBP 962,500** | Cap: GBP 1.2M |

### 5.3 Value for Money Assessment

Beyond lowest price, evaluate:

| Criterion | Weight | Assessment |
|-----------|--------|------------|
| Total Cost vs Budget | 40% | How does total compare to GBP 962.5K estimate? |
| Cost Breakdown Transparency | 20% | Is pricing detailed and justified? |
| Value Alignment | 30% | Does price reflect technical quality and team strength? |
| Payment Terms | 10% | Milestone-based? Retention? Final payment conditions? |

### 5.4 Cost Comparison Template

| Vendor | Total Cost | % of Budget | Cost Score | Cost Rank | Notes |
|--------|------------|-------------|------------|-----------|-------|
| Vendor A | GBP ___ | ___% | ___ | | |
| Vendor B | GBP ___ | ___% | ___ | | |
| Vendor C | GBP ___ | ___% | ___ | | |

---

## 6. Combined Scoring

### 6.1 Final Scoring Formula

**Final Score = (Technical Score x 0.70) + (Cost Score x 0.30)**

Weighting rationale:
- Technical quality (70%): Security and compliance are critical for UK Government migration
- Cost (30%): Value for money is important but secondary to capability and security

### 6.2 Combined Scoring Summary

| Vendor | Technical Score (100) | Technical Weighted (70%) | Cost Score (100) | Cost Weighted (30%) | **Final Score** | Rank |
|--------|-----------------------|--------------------------|------------------|--------------------|-----------------|------|
| Vendor A | ___ | ___ | ___ | ___ | **___** | |
| Vendor B | ___ | ___ | ___ | ___ | **___** | |
| Vendor C | ___ | ___ | ___ | ___ | **___** | |

---

## 7. Vendor Presentations

Shortlisted vendors (top 3) present their proposals to the evaluation committee.

### 7.1 Presentation Format

**Duration**: 2.5 hours
- Vendor presentation: 60 minutes
- Technical demonstration: 30 minutes
- Q&A: 60 minutes

**Attendees**:
- Full evaluation committee
- Executive Sponsor (observer)
- IT Directorate stakeholders (observers)
- Note-taker (non-voting)

**Presentation Content**:
1. Company overview and UK Government credentials (10 min)
2. Proposed team introductions with key personnel present (10 min)
3. Migration methodology overview (15 min)
4. Security and compliance approach (15 min)
5. Timeline and risk management (10 min)
6. Technical demonstration: Exchange Hybrid walkthrough or past migration artifacts (30 min)
7. Q&A (60 min)

### 7.2 Demonstration Requirements

Vendors should demonstrate:
- [ ] Exchange Hybrid configuration approach (lab or production screenshots)
- [ ] Migration batch creation and monitoring
- [ ] Validation tooling and reporting
- [ ] Sensitivity label configuration
- [ ] Post-migration validation process

### 7.3 Presentation Evaluation

Presentations do NOT add new points but may adjust existing scores:
- Clarifications that resolve technical concerns: May increase subcriteria scores
- Red flags or concerning responses: May decrease subcriteria scores
- Team chemistry and communication effectiveness: Qualitative assessment documented

**Post-Presentation Actions**:
1. Evaluation committee debrief within 24 hours
2. Scores adjusted with documented rationale
3. Updated scores captured in evaluation record

---

## 8. Reference Checks

### 8.1 Reference Check Process

For each shortlisted vendor, contact ALL 3 provided references via telephone.

**Reference Check Template**:

**Reference Information**:
- Client Organization: _______________
- Contact Name: _______________
- Contact Role: _______________
- Project Name: _______________
- Project Timeframe: _______________
- Mailbox Count: _______________

**Questions**:

1. **Project Overview**: Can you describe the Exchange Online migration project [Vendor] delivered for you?
   - Notes: _______________

2. **On-Time Delivery**: Was the migration delivered on schedule? If delays, what caused them?
   - [ ] On time  [ ] Minor delays (<2 weeks)  [ ] Significant delays (>2 weeks)
   - Notes: _______________

3. **On-Budget Delivery**: Was the project within budget? Were there change orders?
   - [ ] On budget  [ ] Minor overruns (<10%)  [ ] Significant overruns (>10%)
   - Notes: _______________

4. **Data Integrity**: Was there any data loss during migration? How was validation handled?
   - [ ] Zero data loss  [ ] Minor issues resolved  [ ] Significant issues
   - Notes: _______________

5. **Security Handling**: Did the vendor handle security and data classification appropriately?
   - [ ] Excellent  [ ] Adequate  [ ] Concerns
   - Notes: _______________

6. **Team Effectiveness**: How effective was the vendor's team? Communication? Responsiveness?
   - [ ] Excellent  [ ] Good  [ ] Adequate  [ ] Poor
   - Notes: _______________

7. **Issue Resolution**: How did the vendor handle problems during migration?
   - [ ] Very well  [ ] Adequately  [ ] Poorly
   - Notes: _______________

8. **Post-Migration Support**: How was support during stabilization period?
   - [ ] Excellent  [ ] Good  [ ] Adequate  [ ] Poor
   - Notes: _______________

9. **Would You Rehire?**: Would you engage this vendor for another M365 migration?
   - [ ] Definitely  [ ] Probably  [ ] Maybe  [ ] No
   - Notes: _______________

10. **Additional Comments**: Anything else we should know about working with this vendor?
    - Notes: _______________

**Reference Check Summary**:
- [ ] Highly Positive (enthusiastic endorsement, would definitely rehire)
- [ ] Positive (satisfied, met expectations, would consider again)
- [ ] Mixed (some concerns, met most expectations)
- [ ] Negative (not satisfied, significant issues, would not rehire)

### 8.2 Reference Check Impact

Reference checks can:
- **Disqualify**: Multiple negative references or single highly negative reference
- **Lower scores**: Consistent concerns (e.g., always over budget) may reduce relevant subcriteria by 10-20%
- **Confirm scores**: Positive references validate technical assessment

---

## 9. Final Selection Decision

### 9.1 Selection Criteria

The highest-scoring vendor is typically selected. Decision factors:

**Quantitative (Primary)**:
- Final combined score (Technical 70% + Cost 30%)
- Technical score minimum threshold (70/100)
- Cost within budget cap (GBP 1.2M)

**Qualitative (Secondary)**:
- Reference check outcomes
- Presentation confidence and team quality
- Cultural fit with Cabinet Office
- Risk assessment (known vendor vs. new entrant)

### 9.2 Decision Matrix

| Vendor | Final Score | Technical | Cost | Reference Check | Risk Level | Recommendation |
|--------|-------------|-----------|------|-----------------|------------|----------------|
| Vendor A | ___ | ___/100 | GBP ___ | Positive/Mixed/Negative | Low/Med/High | [ ] Select |
| Vendor B | ___ | ___/100 | GBP ___ | Positive/Mixed/Negative | Low/Med/High | [ ] Select |
| Vendor C | ___ | ___/100 | GBP ___ | Positive/Mixed/Negative | Low/Med/High | [ ] Select |

### 9.3 Selection Approval

**Approval Authority**:
- CTO (Budget authority)
- SIRO (Security assurance)
- Executive Sponsor (Business accountability)

**Approval Requirements**:
- Evaluation summary presented to approvers
- Selection rationale documented
- Risk assessment and mitigation strategies outlined
- Budget confirmation from Finance

### 9.4 Selection Approval Form

**Recommended Vendor**: _______________

**Final Score**: ___ / 100

**Selection Rationale**:
[Summary of why this vendor was selected]

**Key Strengths**:
- [Strength 1: e.g., Strong UK Government migration track record]
- [Strength 2: e.g., Experienced team with relevant certifications]
- [Strength 3: e.g., Comprehensive security approach]

**Risks and Mitigations**:
- [Risk 1]: [Mitigation strategy]
- [Risk 2]: [Mitigation strategy]

**Contract Negotiation Points**:
- [Point 1: e.g., Payment milestone alignment]
- [Point 2: e.g., Warranty period extension]

**Approvals**:

| Role | Name | Signature | Date |
|------|------|-----------|------|
| Evaluation Lead | [NAME] | _________ | [DATE] |
| Enterprise Architect | [NAME] | _________ | [DATE] |
| Security Lead / CISO | [NAME] | _________ | [DATE] |
| Executive Sponsor | [NAME] | _________ | [DATE] |
| CTO | [NAME] | _________ | [DATE] |
| SIRO | [NAME] | _________ | [DATE] |

---

## 10. Vendor Notification

### 10.1 Award Notification

**Selected Vendor**:
- Notify within 2 business days of approval
- Provide formal award letter
- Schedule contract negotiation kickoff
- Provide high-level feedback on proposal strengths

### 10.2 Unsuccessful Vendor Notification

**Timeline**: Within 3 business days of award decision

**Notification Content**:
- Thank vendor for their proposal
- Inform of selection outcome
- Offer optional debrief call (scheduled within 2 weeks if requested)
- Do NOT disclose winner identity or other vendors' details

**Debrief Guidelines**:
- Provide constructive feedback on their proposal
- Highlight areas for improvement
- Do NOT disclose other vendors' scores, costs, or identities
- Focus on their proposal strengths and weaknesses
- Document debrief for record

### 10.3 Standstill Period

Per UK Public Sector procurement regulations:
- 10-day standstill period between notification and contract signature
- Period allows unsuccessful vendors to raise concerns
- No contract activities during standstill

---

## 11. Appeals Process

### 11.1 Grounds for Appeal

Appeals accepted ONLY for:
- [ ] Evaluation process not followed as documented
- [ ] Mathematical scoring errors
- [ ] Undisclosed evaluator conflict of interest
- [ ] Factual misrepresentation in evaluation

Appeals NOT accepted for:
- [ ] Disagreement with scoring judgment
- [ ] "We should have won" without specific process failure
- [ ] Pricing disagreements

### 11.2 Appeal Procedure

1. Vendor submits written appeal within 10 business days of notification
2. Appeal reviewed by Procurement Director (impartial party)
3. Review completed within 10 business days
4. Decision communicated to vendor in writing
5. Procurement Director's decision is final

---

## 12. Documentation and Records Retention

### 12.1 Required Documentation

All evaluation materials retained for 7 years (OFFICIAL records requirement):

- [ ] RFP/SOW document (published)
- [ ] All vendor proposals (technical and cost, separate)
- [ ] Mandatory qualification checklists
- [ ] Individual evaluator scoring sheets (per vendor, per evaluator)
- [ ] Consensus scoring worksheets
- [ ] Vendor presentation notes
- [ ] Technical demonstration notes
- [ ] Reference check notes (per reference)
- [ ] Cost comparison analysis
- [ ] Combined scoring summary
- [ ] Selection decision memo
- [ ] Approval signatures
- [ ] Vendor notification letters
- [ ] Debrief notes (if conducted)
- [ ] Appeal documentation (if any)

### 12.2 Confidentiality

All evaluation materials are OFFICIAL and confidential:
- Evaluators sign non-disclosure agreement
- Proposals not shared outside evaluation committee
- Scores and vendor comparisons remain confidential
- Vendor debriefs do not disclose competitor information
- FOI requests for procurement records handled per Cabinet Office FOI procedures

---

## Appendices

### Appendix A: Evaluator Scorecard Template

[Individual scoring template for each evaluator - to be completed independently before consensus meeting]

### Appendix B: Consensus Scoring Worksheet

[Template for facilitated consensus scoring meeting with all evaluators]

### Appendix C: Conflict of Interest Declaration Form

[Standard COI form for all evaluation committee members]

### Appendix D: Reference Check Script

[Detailed reference check questionnaire with prompts]

### Appendix E: Requirements Traceability Matrix

| Requirement ID | Requirement Description | Evaluation Criterion | Verification Method |
|----------------|------------------------|---------------------|---------------------|
| BR-001 | Cloud-First Mandate | 1.1 Hybrid Migration Strategy | Technical proposal review |
| BR-007 | Security Classifications | 2.1 OFFICIAL/OFFICIAL-SENSITIVE Handling | Security proposal review |
| FR-001 | Zero Data Loss Migration | 1.2 Data Integrity and Validation | Methodology review, references |
| FR-003 | UK Data Residency | 2.1 OFFICIAL/OFFICIAL-SENSITIVE Handling | Architecture review |
| FR-004 | Conditional Access | 1.4 Azure AD and Identity Integration | Technical proposal review |
| FR-005 | Sensitivity Labels | 2.2 Microsoft Purview Configuration | Security proposal review |
| NFR-SEC-001 | MFA Enforcement | 2.5 Vendor Security Practices | Security proposal review |
| NFR-C-001 | UK GDPR Compliance | MQ-017, 2.1 Data Handling | DPA review, proposal review |

### Appendix F: Architecture Principles Alignment Matrix

| Principle | Evaluation Criterion | How Assessed |
|-----------|---------------------|--------------|
| 1. Cloud-First with UK Sovereignty | 1.1, 2.1 | UK data residency approach, migration to Exchange Online |
| 3. Security by Design | 2.1, 2.2, 2.3, 2.4, 2.5 | Full Category 2 assessment |
| 6. Data Sovereignty and Classification | 2.1, 2.2 | Sensitivity labels, DLP configuration |
| 10. Infrastructure as Code | 1.1 (Bonus) | M365DSC or configuration management approach |
| 11. Zero Trust Identity | 1.4, 2.5 | Conditional Access, MFA, PIM usage |
| 12. Information Governance | 2.2 | Retention policies, eDiscovery approach |
| 19. Audit Logging | 2.4 | UAL configuration, SIEM integration |

---

**Document Control**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2026-01-23 | ArcKit AI | Initial version for Exchange Online Migration evaluation |

---

**Generated by**: ArcKit `/arckit.evaluate` command
**Generated on**: 2026-01-23
**Last Updated**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Exchange Online Migration to Microsoft 365
**Model**: Claude

---

**Classification**: OFFICIAL

*This document contains sensitive Cabinet Office procurement information and should be handled per Government Security Classifications Policy and UK Public Sector Procurement regulations.*

---

**END OF DOCUMENT**
