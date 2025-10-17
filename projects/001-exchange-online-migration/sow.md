# Statement of Work (SOW): Exchange Online Migration to Microsoft 365

**Document Type**: Procurement - Statement of Work / Request for Proposal (RFP)  
**RFP ID**: RFP-CAB-2025-001  
**Project ID**: 001  
**Issue Date**: 2025-10-17  
**Proposal Due Date**: 2025-12-15 at 17:00 GMT  
**Version**: 1.0  
**Issuing Organization**: Cabinet Office, UK Government  
**Point of Contact**: Procurement Team - procurement@cabinetoffice.gov.uk

---

## 1. Executive Summary

### 1.1 Purpose of This SOW

This Statement of Work (SOW) defines the requirements, deliverables, and evaluation criteria for migrating the Cabinet Office email infrastructure from on-premises Microsoft Exchange Server 2016 to Microsoft Exchange Online (M365). The Cabinet Office is seeking qualified migration partners to execute a zero-data-loss migration of 3,500 user mailboxes within a 9-month timeline.

This is an official UK Government procurement and all vendors must comply with UK Public Sector Procurement regulations, Government Security Classifications Policy, and Technology Code of Practice.

### 1.2 Background

The Cabinet Office is at the heart of the UK Government, supporting the Prime Minister, Deputy Prime Minister and the Cabinet. As the corporate headquarters of government, the Cabinet Office leads on issues including digital transformation, civil service reform, and efficiency.

**Current State**: The Cabinet Office operates an on-premises Microsoft Exchange Server 2016 infrastructure across multiple directorates serving approximately 3,500 civil servants. This infrastructure has reached end-of-support lifecycle and requires immediate replacement to avoid security and operational risks.

**Business Drivers**:
- **End-of-support**: Exchange 2016 reaches end-of-extended-support in October 2026, creating security vulnerabilities
- **Hardware refresh cost avoidance**: On-premises infrastructure requires £1.2M capital investment for hardware refresh
- **Flexible working enablement**: Post-COVID hybrid working requires secure mobile email access not adequately supported by current infrastructure
- **Technology Code of Practice compliance**: UK Government TCoP Point 3 mandates "Use cloud first" for all new IT infrastructure
- **Cost optimization**: Move from CapEx to OpEx model with 40% Total Cost of Ownership (TCO) reduction

**Strategic Importance**: This migration is a critical component of Cabinet Office's digital transformation strategy, enabling modern collaboration capabilities while demonstrating leadership in cloud adoption across UK Government.

### 1.3 Project Overview

**Objective**: Migrate 100% of Cabinet Office email infrastructure to Microsoft Exchange Online within 9 months, achieving zero data loss, maintaining OFFICIAL/OFFICIAL-SENSITIVE data classification controls, and ensuring UK data sovereignty.

**Scope Summary**:
- 3,500 user mailboxes (average 15GB, 52TB total)
- 150 shared mailboxes and resource mailboxes (meeting rooms)
- Migration from Exchange Server 2016 to Exchange Online
- Azure AD Connect hybrid identity configuration
- Microsoft Purview sensitivity labels and DLP policies
- Microsoft Defender for Office 365 (Plan 2) deployment
- Intune mobile device management integration
- Retention policies aligned with Public Records Act
- eDiscovery and legal hold capabilities
- Comprehensive user training and change management
- Decommissioning of on-premises Exchange infrastructure

**Expected Outcomes**:
- £800K annual cost savings (40% TCO reduction from £2M to £1.2M annually)
- 99.9% service availability (improved from current 98.5%)
- Zero data loss during migration (100% item count validation)
- 80%+ user satisfaction within 1 month post-migration
- 70% mobile email adoption within 6 months
- Full compliance with OFFICIAL classification and NCSC Cloud Security Principles

**Budget Range**: £800K - £1.2M (excluding M365 E5 licenses already procured)

**Timeline**: 9-month implementation from contract signing (November 2025 - August 2026), with pilot in Month 3 and phased production migration Months 5-9

---

## 2. Scope of Work

### 2.1 In Scope

The selected migration partner will be responsible for:

#### 2.1.1 **Planning and Design Phase** (Months 1-2)
- Current state assessment (Exchange 2016 environment documentation)
- Azure AD Connect hybrid identity design and deployment
- Exchange Hybrid configuration design and implementation
- Microsoft 365 tenant configuration for UK data residency (UK South/UK West)
- High-Level Design (HLD) document with C4 diagrams
- Detailed Design (DLD) document with migration plan
- Security design aligned with NCSC Cloud Security Principles
- Privacy Impact Assessment (PIA) support for DPO approval
- Migration tooling selection and setup (e.g., BitTitan MigrationWiz, Microsoft tooling)
- Pilot wave planning (100 users, Finance directorate)

#### 2.1.2 **Microsoft 365 Configuration** (Months 2-3)
- Azure AD (Entra ID) configuration and synchronization
- Conditional Access policies (MFA, device compliance, geofencing)
- Microsoft Purview Information Protection:
  - Sensitivity labels (OFFICIAL, OFFICIAL-SENSITIVE)
  - Auto-labeling policies based on content inspection
  - Data Loss Prevention (DLP) policies
- Retention policies aligned with Cabinet Office retention schedules (2-20 years)
- Microsoft Defender for Office 365 (Plan 2):
  - Safe Links and Safe Attachments policies
  - Anti-phishing and anti-impersonation policies
  - Threat investigation and response configuration
- Microsoft Intune device compliance policies
- Mail flow rules (transport rules) migration and modernization
- Unified Audit Log configuration (7-year retention for OFFICIAL records)
- eDiscovery permissions and case management setup
- Microsoft Sentinel (SIEM) integration for audit log streaming

#### 2.1.3 **Migration Execution** (Months 3-9)
- **Pilot Migration** (Month 3, 100 users):
  - Finance directorate (validate financial system integrations)
  - IT directorate volunteers
  - M365 Champions (early adopters for peer support network)
  - Validation, lessons learned, process refinement

- **Phase 1 Migration** (Month 5, 1,200 users):
  - Corporate Services directorate
  - Digital and Technology directorate
  - Policy and Strategy directorate

- **Phase 2 Migration** (Month 7, 1,200 users):
  - Economic and Domestic Affairs Secretariat
  - European and Global Affairs Secretariat
  - Cabinet Secretariat

- **Phase 3 Migration** (Month 9, 1,000 users + executives):
  - Propriety and Constitution Group
  - Executive team (Directors General, Directors)
  - Ministerial private offices (weekend cutover only, critical)

**Migration Requirements (All Phases)**:
- Mailbox content migration (emails, calendar, contacts, tasks, rules)
- Shared mailbox permissions preservation
- Resource mailbox booking policies preservation
- Item count validation (100% match, <1% variance acceptable only for corrupted items)
- Folder structure preservation
- Mailbox permissions (send-as, full-access, send-on-behalf) preservation
- MX record and Autodiscover cutover
- 30-day rollback window (on-prem mailbox retained as disabled)
- Post-migration validation reports
- User notification and communication (email, intranet)

#### 2.1.4 **Training and Change Management** (Months 3-10)
- Change management strategy and plan (ADKAR model)
- M365 Champions network establishment (50+ champions across directorates)
- Training materials development (eLearning, quick reference guides, video tutorials)
- Role-based training delivery:
  - End users (Outlook Web App, Outlook mobile, Outlook desktop)
  - Administrators (Exchange Online Admin Center, PowerShell management)
  - Executives (assistants, delegate access, mobile access)
- Accessibility-compliant training materials (WCAG 2.2 AA)
- Service desk knowledge base and escalation procedures
- Training completion tracking (100% mandatory before migration wave)
- Post-migration support (Months 10-11, hypercare period)

#### 2.1.5 **Documentation and Knowledge Transfer** (Months 8-10)
- Architecture documentation (C4 model: Context, Container, Component diagrams)
- Administrator guides (Exchange Online management, mailbox management, security policies)
- Runbooks:
  - Incident response (mailbox compromise, phishing email, mail flow interruption)
  - eDiscovery search procedures (FOI requests, legal hold)
  - User support procedures (password reset, mailbox access troubleshooting)
- User manuals (accessible HTML and PDF, WCAG 2.2 AA compliant)
- Configuration baseline documentation (M365DSC export of tenant configuration)
- Knowledge transfer sessions (IT operations team, administrators, security team)

#### 2.1.6 **Testing and Validation** (Ongoing, Months 3-10)
- Pilot migration testing (100 users, comprehensive validation)
- User Acceptance Testing (UAT) after each phase
- Performance testing (email delivery latency <30 seconds, OWA load time <2 seconds)
- Security testing:
  - Conditional Access policy validation
  - DLP policy testing (OFFICIAL-SENSITIVE blocking)
  - MFA enforcement testing (100% users)
  - Penetration testing (NCSC CHECK-certified assessor)
- Accessibility testing (WCAG 2.2 AA compliance for OWA, training materials)
- Disaster recovery testing (UK West region failover)
- Integration testing (Azure AD, Intune, Sentinel, third-party apps)

#### 2.1.7 **Decommissioning** (Month 11)
- On-premises Exchange Server 2016 decommissioning plan
- Data archival verification (on-prem mailboxes deleted after 30-day rollback window)
- Hardware decommissioning coordination with IT Infrastructure team
- Datacenter exit coordination

### 2.2 Out of Scope

The following are explicitly NOT part of this engagement and remain Cabinet Office responsibility or separate projects:

- **SharePoint migration**: Migration of on-premises SharePoint to SharePoint Online (separate project: Project 002)
- **Microsoft Teams deployment**: Teams migration already completed in prior project
- **Third-party email security appliances**: Current email filtering/security tools to be replaced by Microsoft Defender for Office 365
- **Personal .PST files**: Users responsible for importing personal .PST archives to Exchange Online
- **Email signature management**: Cabinet Office to implement Microsoft 365 signature tools or third-party solution (e.g., Exclaimer)
- **Mobile device procurement**: BYOD policy managed by Cabinet Office, Intune licensing provided by Cabinet Office
- **Microsoft 365 E5 licensing**: Licenses already procured (3,500 licenses) by Cabinet Office
- **Azure subscription and infrastructure**: Existing Azure UK regions subscription managed by Cabinet Office
- **Network bandwidth upgrades**: Existing 100 Mbps dedicated circuit to Azure sufficient for migration
- **On-premises Active Directory management**: Azure AD Connect configuration in scope; on-prem AD management remains with Cabinet Office IT
- **Ongoing M365 operations post-warranty**: Vendor responsible for 90-day warranty post-go-live; ongoing operations transfer to Cabinet Office IT (knowledge transfer required)

### 2.3 Cabinet Office Responsibilities

Cabinet Office will provide the following to support the migration partner:

**Access and Permissions**:
- On-premises Exchange Server 2016 administrator access (for current state assessment and hybrid configuration)
- Azure AD Global Administrator credentials (time-limited, PIM-activated)
- Microsoft 365 E5 tenant access (Exchange Online, Purview, Defender, Intune)
- Azure subscription access for Azure AD Connect VM deployment
- Network access to Cabinet Office datacenters (VPN credentials for remote work, on-site access for hybrid configuration)

**Subject Matter Experts (SMEs)**:
- Exchange administrator (on-prem Exchange SME, hybrid configuration support)
- Azure AD administrator (identity and Conditional Access SME)
- Information governance lead (sensitivity labels, retention policies, DLP rules)
- Security architect (NCSC Cloud Security Principles compliance review)
- SIRO and IAO (security risk approval, data classification approval)
- Data Protection Officer (DPO) (GDPR compliance, PIA approval)
- Change manager (Change Advisory Board coordination, stakeholder communications)
- Directorate representatives (user acceptance testing, pilot feedback)

**Infrastructure and Tools**:
- Microsoft 365 E5 licenses (3,500 procured, assigned by vendor during migration)
- Azure subscription (UK South and UK West regions)
- 100 Mbps dedicated network circuit to Azure (for migration bandwidth)
- ServiceNow (for service desk ticket tracking and incident management)
- Microsoft Sentinel (SIEM for audit log ingestion)
- Microsoft Intune (MDM for device compliance)

**Decisions and Approvals**:
- Architecture Review Board (ARB) approval for HLD and DLD
- SIRO sign-off on security controls and residual risks
- Change Advisory Board (CAB) approval for migration batches and production changes
- Pilot migration go/no-go decision (based on validation results)
- Ministerial office migration scheduling (sensitive, requires executive coordination)

**Business Continuity**:
- On-premises Exchange 2016 operational support during migration period (9 months)
- Backup and disaster recovery for on-prem Exchange (maintained by Cabinet Office IT until decommissioning)
- Rollback decision authority (if migration fails validation, Cabinet Office authorizes rollback)

---

## 3. Requirements

### 3.1 Requirements Summary

This project has **48 mandatory requirements** organized as follows:
- 7 Business Requirements (BR-001 through BR-007)
- 15 Functional Requirements (FR-001 through FR-015)
- 23 Non-Functional Requirements (NFR-P, NFR-A, NFR-S, NFR-SEC, NFR-C, NFR-U, NFR-M, NFR-I)
- 3 Integration Requirements (INT-001 through INT-003)

**CRITICAL**: All requirements marked "MUST_HAVE" or "NON-NEGOTIABLE" are mandatory. Vendors failing to meet these requirements will be disqualified. Detailed requirements available in Appendix A and attached requirements document (`requirements.md`).

### 3.2 Key Functional Capabilities

**3.2.1 Mailbox Migration (FR-001)**
- Zero data loss migration (100% item count match, <1% variance only for corrupted items logged and reported)
- 3,500 user mailboxes (average 15GB, 52TB total)
- 150 shared/resource mailboxes
- Content types: Emails, calendar events, contacts, tasks, Outlook rules
- Permissions preservation: Send-as, full-access, send-on-behalf delegations
- **Acceptance Criteria**: Post-migration validation reports show 100% item count match, folder structure preserved, calendar events with correct date/time/attendees

**3.2.2 Hybrid Identity (FR-002)**
- Azure AD Connect deployment and configuration
- Synchronization of 3,500 on-prem AD accounts to Azure AD
- Password hash synchronization (30-minute sync interval)
- Seamless single sign-on (SSO) for Exchange Online access
- **Acceptance Criteria**: All users can authenticate to Exchange Online with on-prem credentials, password changes sync within 30 minutes

**3.2.3 UK Data Residency (FR-003, NON-NEGOTIABLE)**
- All mailbox data stored in UK South (primary) and UK West (disaster recovery) regions
- Multi-Geo disabled (no data outside UK)
- Monthly data residency attestation reports
- Customer Lockbox enabled (Microsoft support requires SIRO approval for data access)
- **Acceptance Criteria**: Get-MailboxLocation cmdlet shows 100% mailboxes report "United Kingdom" as data location

**3.2.4 Security and Compliance (FR-004 through FR-011, NON-NEGOTIABLE)**
- Conditional Access policies: MFA (100% users), device compliance, geofencing (UK + approved countries)
- Sensitivity labels: OFFICIAL (default), OFFICIAL-SENSITIVE (encryption, visual markings)
- DLP policies: Block external sharing of OFFICIAL-SENSITIVE, detect NI numbers/passport numbers
- Microsoft Defender for Office 365 (Plan 2): Safe Links, Safe Attachments, anti-phishing, anti-impersonation
- Retention policies: 1-20 years based on document type (aligned with Public Records Act)
- eDiscovery: FOI request support (20-day response SLA), legal hold capabilities
- Intune MDM: Device compliance policies (PIN, OS version, jailbreak detection), remote wipe
- Unified Audit Log: 7-year retention for OFFICIAL records, SIEM integration (Sentinel)
- **Acceptance Criteria**: SIRO sign-off, NCSC CHECK penetration test passed, DLP policy violations logged and SOC alerted

### 3.3 Non-Functional Requirements

#### 3.3.1 Performance (NFR-P-001 through NFR-P-003)
- **Email Delivery Latency**: <30 seconds (95th percentile) for 3,500 users, 175,000 emails/day peak
- **OWA Page Load Time**: <2 seconds (95th percentile) for 1,050 concurrent users
- **Migration Throughput**: 300 mailboxes per 48-hour weekend window (10 concurrent migrations at 10 Mbps each)
- **Measurement**: Microsoft 365 Message Trace, synthetic monitoring, migration batch statistics

#### 3.3.2 Availability and Resilience (NFR-A-001 through NFR-A-003, CRITICAL)
- **Uptime SLA**: 99.9% availability (max 43 min unplanned downtime/month, measured by Microsoft 365 Service Health)
- **Disaster Recovery**:
  - RPO (Recovery Point Objective): 15 minutes (Microsoft continuous replication)
  - RTO (Recovery Time Objective): 4 hours for email service restoration
  - Automatic failover to UK West region <15 minutes
  - Annual DR drill required
- **Fault Tolerance**: Graceful degradation patterns (circuit breaker, retry with exponential backoff, timeouts, bulkhead isolation)

#### 3.3.3 Security (NFR-SEC-001 through NFR-SEC-005, NON-NEGOTIABLE)
- **Multi-Factor Authentication**: 100% users (no exceptions except 2 break-glass accounts), Microsoft Authenticator preferred, FIDO2 security keys for high-privilege accounts
- **RBAC with PIM**: Global Admin (5 max, PIM only), Exchange Admin (8, PIM), least privilege principle, approval workflows
- **Encryption**:
  - In transit: TLS 1.3 mandatory for all SMTP transport
  - At rest: AES-256 for all mailbox data (Microsoft-managed keys), customer-managed keys optional for OFFICIAL-SENSITIVE
- **Secrets Management**: Azure Key Vault (no credentials in code/config), 90-day password rotation, 1-year certificate rotation
- **Penetration Testing**: Annual NCSC CHECK-certified penetration test, vulnerability remediation SLA (Critical 24 hours, High 7 days, Medium 30 days)

#### 3.3.4 Compliance (NFR-C-001 through NFR-C-003, NON-NEGOTIABLE)
- **UK GDPR / Data Protection Act 2018**:
  - Privacy Impact Assessment (PIA) completed and DPO approved
  - Subject Access Request (SAR) procedures (20-day response SLA)
  - Data breach notification to ICO <72 hours
  - UK-only data residency (no cross-border transfers except Microsoft support with Customer Lockbox approval)

- **Government Security Classifications Policy**:
  - All email classified OFFICIAL or OFFICIAL-SENSITIVE
  - Unified Audit Log: Who, What, When, Where, Why, Result (7-year retention for OFFICIAL, 10 years for OFFICIAL-SENSITIVE)
  - Immutable logging, SIEM integration (Microsoft Sentinel)

- **Public Records Act / National Archives**:
  - Permanent records (policy papers, ministerial correspondence) retained 20 years, transferred to National Archives
  - Retention label auto-application based on sender/recipient/content
  - Monthly compliance reports, quarterly disposition reviews

#### 3.3.5 Accessibility (NFR-U-002, CRITICAL - LEGAL REQUIREMENT)
- **WCAG 2.2 Level AA Compliance**: Public Sector Bodies (Websites and Mobile Applications) Accessibility Regulations 2018
- **Features**: Keyboard navigation, screen reader compatibility (JAWS, NVDA), high contrast mode, adjustable fonts
- **Testing**: Pa11y, Axe DevTools (automated), manual keyboard/screen reader testing, user testing with disabled users
- **Scope**: Outlook Web App, training materials (eLearning, PDFs), documentation
- **Deliverable**: Accessibility statement published, WCAG 2.2 AA compliance certificate

#### 3.3.6 Observability and Documentation (NFR-M-001 through NFR-M-003)
- **Monitoring**: Unified Audit Log to SIEM (Sentinel), M365 Service Health dashboard, Power BI adoption dashboards, alerting (DLP violations, security incidents, service degradation)
- **Documentation**: C4 architecture diagrams, administrator guides, runbooks (incident response, eDiscovery, user support), user manuals (accessible HTML/PDF), M365DSC configuration baseline
- **Currency**: Documentation updated within 10 business days of configuration changes

### 3.4 Integration Requirements

#### INT-001: Azure Active Directory (Entra ID) - CRITICAL
- **Purpose**: Authenticate users, enforce Conditional Access policies
- **Type**: Real-time API (OAuth 2.0, OpenID Connect)
- **Data**: Authentication tokens, user attributes (UPN, group memberships), Conditional Access decisions
- **SLA**: <200ms token validation, 99.99% availability
- **Error Handling**: Cached credentials allow 8-hour offline access

#### INT-002: Microsoft Intune (Mobile Device Management) - HIGH
- **Purpose**: Enforce device compliance for mobile email access
- **Type**: Real-time API (Microsoft Graph, Conditional Access)
- **Data**: Device compliance status, device attributes (OS, jailbreak, encryption)
- **SLA**: <1 second compliance check, 99.9% availability
- **Error Handling**: Fail-open (temporary allow with alert) if Intune unavailable

#### INT-003: Microsoft Sentinel (SIEM) - HIGH
- **Purpose**: Ingest Exchange Online audit logs for threat detection
- **Type**: Event-driven (Azure Event Hub streaming)
- **Data**: Unified Audit Log events (MailItemsAccessed, Send, MailboxLogin, admin actions), DLP violations, Defender alerts
- **SLA**: <5 min latency event to Sentinel, 10,000 events/second throughput
- **Error Handling**: 24-hour buffer in Exchange if Event Hub unavailable, replay when restored

### 3.5 Technical Constraints

**TC-001**: Must integrate with on-premises Active Directory (Windows Server 2016 AD Domain Services) via Azure AD Connect hybrid identity

**TC-002**: Must deploy within existing Azure UK regions subscription (UK South, UK West only)

**TC-003**: Must use existing Microsoft 365 E5 licenses (3,500 procured by Cabinet Office)

**TC-004**: Network bandwidth constraint: 100 Mbps dedicated circuit to Azure (sufficient for 10 concurrent mailbox migrations at 10 Mbps each)

**TC-005**: Must coexist with on-premises Exchange 2016 for 6-month hybrid period during phased migration

**TC-006**: Must comply with Cabinet Office M365 Architecture Principles (see Appendix B: 20 principles across strategic, data, technology, architecture, development, operational, and compliance domains)

**TC-007**: Must align with UK Government standards:
- Technology Code of Practice (TCoP) - all 10 points
- GDS Service Standard - 14 points
- NCSC Cloud Security Principles - all 14 principles
- Government Security Classifications Policy
- WCAG 2.2 Level AA (Public Sector Accessibility Regulations 2018)

---

## 4. Deliverables

### 4.1 Planning Phase Deliverables

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Current State Assessment** | Exchange 2016 environment documentation (servers, mailbox distribution, sizes, permissions, transport rules) | Document (PDF/Markdown) | Week 2 | Cabinet Office IT validates accuracy |
| **High-Level Design (HLD)** | Architecture overview (C4 Context, Container diagrams), M365 tenant config, hybrid identity design, migration approach | Document + Diagrams | Week 4 | Architecture Review Board approval |
| **Detailed Design (DLD)** | Component specifications (Azure AD Connect, Conditional Access, sensitivity labels, DLP, Defender, retention policies), migration plan | Document + Config specs | Week 8 | Technical reviewers approval |
| **Security Design** | Threat model (NCSC guidance), security controls mapped to NCSC Cloud Security Principles, compliance matrix (GDPR, Gov Sec Classifications) | Document | Week 6 | SIRO and CISO approval |
| **Privacy Impact Assessment (PIA) Support** | PIA documentation support, lawful basis analysis, data flow diagrams | Document | Week 6 | DPO approval |
| **Migration Plan** | Phased migration schedule (pilot, Phase 1-3), batch definitions, rollback procedures, validation plan | Document + Project plan | Week 8 | Change Manager and CTO approval |

### 4.2 Configuration Deliverables

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Azure AD Connect Configuration** | Hybrid identity deployed (3,500 users synced), password hash sync enabled, SSO tested | Deployed system + runbook | Week 10 | All users authenticate to M365 |
| **Exchange Hybrid Configuration** | Hybrid coexistence (on-prem + cloud), free/busy federation, mailbox move capability | Deployed system + runbook | Week 10 | Test mailbox migrated successfully |
| **Conditional Access Policies** | 5 policies (MFA all users, block legacy auth, device compliance, geofencing, high-risk controls) | M365 policies + documentation | Week 10 | Policy testing passed, CISO approval |
| **Sensitivity Labels & DLP** | OFFICIAL/OFFICIAL-SENSITIVE labels, auto-labeling rules, DLP policies (block external OFFICIAL-SENSITIVE) | Purview config + documentation | Week 11 | IAO approval, DLP testing passed |
| **Defender for Office 365** | Safe Links, Safe Attachments, anti-phishing, anti-impersonation policies | Defender config + documentation | Week 11 | Security team approval |
| **Retention Policies** | Retention labels (Transitory 1yr, Financial 7yr, Policy Papers 20yr), auto-application rules | Purview config + documentation | Week 11 | Records Manager approval |
| **Intune Device Compliance** | Device compliance policies (PIN, OS version, jailbreak detection), Conditional Access enforcement | Intune config + documentation | Week 11 | Mobile access tested and validated |
| **Unified Audit Log & Sentinel** | UAL enabled (7-year retention), Sentinel integration (Event Hub), alerting rules | M365 + Sentinel config + documentation | Week 11 | Audit log search tested, SIEM alerts verified |
| **M365 Configuration Baseline** | M365DSC export of tenant configuration (IaC baseline for change control and DR) | PowerShell DSC scripts | Week 12 | Configuration reproducible from code |

### 4.3 Migration Execution Deliverables

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Pilot Migration (100 users)** | Finance directorate, IT volunteers, M365 Champions migrated and validated | Migrated mailboxes + validation report | Month 3 (Week 12) | Zero data loss, user acceptance, lessons learned documented |
| **Phase 1 Migration (1,200 users)** | Corporate Services, Digital & Technology, Policy & Strategy migrated | Migrated mailboxes + validation report | Month 5 (Week 20) | Zero data loss, <10% service desk tickets |
| **Phase 2 Migration (1,200 users)** | Economic & Domestic Affairs, European & Global Affairs, Cabinet Secretariat migrated | Migrated mailboxes + validation report | Month 7 (Week 28) | Zero data loss, user satisfaction >75% |
| **Phase 3 Migration (1,000 users + execs)** | Propriety & Constitution, Executive team, Ministerial offices migrated | Migrated mailboxes + validation report | Month 9 (Week 36) | Zero data loss, executive satisfaction >90%, zero escalations |
| **Migration Validation Reports** | Per-batch validation: item count match, folder structure, calendar accuracy, permissions, performance metrics | Reports (CSV + PDF) | After each migration batch | 100% item count match, <1% variance (corrupted items logged) |

### 4.4 Training and Change Management Deliverables

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Change Management Plan** | ADKAR model, stakeholder engagement, communication plan, resistance management | Document | Week 8 | Change Manager approval |
| **M365 Champions Network** | 50+ champions recruited, trained, and equipped for peer support | Champion list + training materials | Week 10 | Champions trained and active in directorates |
| **Training Materials** | eLearning modules (Outlook Web App, Outlook mobile, Outlook desktop), quick reference guides, video tutorials | SCORM packages + PDF + videos | Week 12 | Accessibility compliant (WCAG 2.2 AA), content reviewed |
| **Training Delivery** | Role-based training sessions (end users, administrators, executives) | Training sessions + LMS tracking | Weeks 11-36 | 100% users trained before their migration wave |
| **Service Desk Knowledge Base** | Knowledge articles (Outlook access, password reset, mobile setup, troubleshooting), escalation procedures | ServiceNow KB articles | Week 12 | Service desk staff trained, articles validated |
| **User Communications** | Email campaigns, intranet announcements, town halls, posters (pre-migration, cutover notifications, post-migration tips) | Emails + intranet pages + presentations | Weeks 10-40 | Stakeholder approval, communications delivered on schedule |

### 4.5 Documentation and Knowledge Transfer Deliverables

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Architecture Documentation** | C4 model (Context, Container, Component), logical architecture, network diagram, data flow diagrams | Diagrams + document (Markdown/PDF) | Week 38 | Enterprise Architect approval |
| **Administrator Guides** | Exchange Online Admin Center, PowerShell cmdlets, mailbox management, security policy admin, troubleshooting | Document (Markdown + accessible HTML/PDF) | Week 38 | Cabinet Office admin team validates |
| **Operational Runbooks** | Incident response (mailbox compromise, phishing, mail flow failure), eDiscovery (FOI requests, legal hold), user support (password reset, access issues) | Markdown documents in SharePoint | Week 38 | Runbooks tested with IT ops team |
| **User Manuals** | Outlook Web App user guide, Outlook mobile guide, Outlook desktop guide, FAQs | Accessible HTML + PDF (WCAG 2.2 AA) | Week 36 | Accessibility audit passed, user feedback |
| **Configuration Baseline (M365DSC)** | Infrastructure-as-Code export of M365 tenant configuration (Conditional Access, DLP, Defender, retention policies) | PowerShell DSC scripts + documentation | Week 38 | Configuration drift detection tested |
| **Knowledge Transfer Sessions** | Architecture walkthrough, operations training (monitoring, incident response), security training (DLP, Defender, audit logs) | Training sessions + recorded videos | Weeks 38-40 | Cabinet Office teams can operate independently |
| **Post-Implementation Review** | Lessons learned, benefits realization analysis, recommendations for ongoing optimization | Report | Week 42 | CTO sign-off, project closure |

### 4.6 Testing Deliverables

| Deliverable | Description | Format | Due Date | Acceptance Criteria |
|-------------|-------------|--------|----------|---------------------|
| **Pilot Test Results** | Pilot migration validation (item counts, performance, security, user feedback) | Test report | Month 3 | Go/no-go decision for Phase 1 |
| **UAT Results** | User acceptance testing after each phase (functionality, performance, usability) | UAT sign-off forms + defect log | After each phase | Business users sign-off |
| **Performance Test Results** | Email delivery latency, OWA page load time, migration throughput | Test report with metrics | Month 9 | SLA targets met (<30s email, <2s OWA) |
| **Security Test Results** | Conditional Access testing, DLP testing, MFA enforcement, penetration test (NCSC CHECK) | Test report + pen test report | Month 9 | SIRO sign-off, no critical vulnerabilities |
| **Accessibility Test Results** | WCAG 2.2 AA compliance (OWA, training materials, documentation) | Accessibility audit report | Month 9 | Pa11y/Axe passed, manual testing passed |
| **DR Test Results** | UK West region failover test (RTO <4 hours, RPO <15 minutes) | DR test report | Month 10 | DR drill successful, RTO/RPO met |

### 4.7 Warranty and Support (Months 10-12, Post-Go-Live)

**90-Day Warranty Period** (from final migration completion, Month 9):
- All defects identified during warranty will be fixed at no additional cost
- Response time for critical defects: 4 hours
- Response time for non-critical defects: 2 business days
- Monthly warranty reports (incidents, resolutions, outstanding issues)

**Hypercare Support** (Months 10-11, 60 days):
- Dedicated support team available for escalations
- Daily stand-ups with Cabinet Office IT ops team
- Proactive monitoring and issue resolution
- User support escalation path (from service desk to vendor)

---

## 5. Project Timeline and Milestones

### 5.1 High-Level Timeline

**Total Duration**: 11 months from contract signing (plus 1 month warranty = 12 months total)

| Phase | Duration | Key Milestones |
|-------|----------|----------------|
| **Procurement** | Weeks 1-8 (Nov-Dec 2025) | RFP issued, proposals due, vendor selection, contract signed |
| **Planning & Design** | Weeks 1-8 (Nov-Dec 2025) | Current state assessment, HLD, DLD, security design, migration plan |
| **M365 Configuration** | Weeks 8-12 (Dec 2025-Jan 2026) | Azure AD Connect, Conditional Access, Purview, Defender, Intune, Sentinel |
| **Pilot Migration** | Week 12, Month 3 (Feb 2026) | 100 users (Finance), validation, lessons learned, go/no-go decision |
| **Phase 1 Migration** | Month 5 (Apr 2026) | 1,200 users (Corporate Services, Digital & Tech, Policy & Strategy) |
| **Phase 2 Migration** | Month 7 (Jun 2026) | 1,200 users (Economic Affairs, European Affairs, Cabinet Secretariat) |
| **Phase 3 Migration** | Month 9 (Aug 2026) | 1,000 users + executives (Ministerial offices, weekend cutover) |
| **Stabilization** | Month 10 (Sep 2026) | Hypercare support, issue resolution, performance tuning |
| **Decommissioning** | Month 11 (Oct 2026) | On-prem Exchange 2016 decommissioned, datacenter exit |
| **Warranty** | Months 10-12 (Sep-Nov 2026) | 90-day warranty period, knowledge transfer complete |

### 5.2 Key Milestones

| Milestone | Target Date | Deliverables Due | Exit Criteria |
|-----------|-------------|------------------|---------------|
| **M0: Contract Signed** | 2025-12-20 | Signed contract | Vendor mobilization begins |
| **M1: Project Kickoff** | Week 1 (2026-01-06) | Project plan, resource assignments, kickoff meeting | Teams introduced, environment access granted |
| **M2: Design Approval** | Week 8 (2026-02-24) | HLD, DLD, security design, migration plan | Architecture Review Board approval, SIRO sign-off |
| **M3: Pilot Go-Live** | Month 3 (2026-02-27) | 100 users migrated, validation report | Pilot successful, go/no-go decision for Phase 1 |
| **M4: Phase 1 Complete** | Month 5 (2026-04-30) | 1,200 users migrated | User satisfaction >75%, zero data loss |
| **M5: Phase 2 Complete** | Month 7 (2026-06-30) | 1,200 users migrated | User satisfaction >80%, service desk tickets declining |
| **M6: Phase 3 Complete** | Month 9 (2026-08-31) | 1,000 users + execs migrated | All users migrated, executive satisfaction >90% |
| **M7: Stabilization Complete** | Month 10 (2026-09-30) | Hypercare support, performance tuning | Service desk tickets at baseline, 99.9% availability achieved |
| **M8: Decommissioning Complete** | Month 11 (2026-10-31) | On-prem Exchange decommissioned | Hardware removed, datacenter exit confirmed |
| **M9: Project Closure** | Month 12 (2026-11-30) | Post-implementation review, warranty complete | CTO sign-off, project formally closed |

### 5.3 Procurement Timeline

| Event | Date |
|-------|------|
| **RFP Issued** | 2025-10-17 |
| **Vendor Questions Due** | 2025-10-31 (2 weeks) |
| **Answers Published** | 2025-11-07 (3 weeks) |
| **Proposals Due** | 2025-12-15 at 17:00 GMT (8 weeks) |
| **Vendor Presentations** | 2025-12-18 to 2026-01-08 (Weeks 9-12) |
| **Final Vendor Selection** | 2026-01-12 (Week 13) |
| **Contract Negotiation** | 2026-01-13 to 2026-01-19 (Week 13) |
| **Contract Signed (M0)** | 2026-01-20 |
| **Project Start (M1)** | 2026-01-27 (Week 1) |

---

## 6. Vendor Qualifications and Requirements

### 6.1 Mandatory Qualifications (PASS/FAIL)

Vendors MUST meet the following minimum qualifications to be considered. Failure to meet ANY mandatory qualification will result in disqualification.

**MQ-1 - Microsoft 365 Migration Experience**:
- Minimum 5 years of experience delivering Microsoft 365 (Exchange Online) migration projects
- Minimum 3 reference projects in the past 3 years migrating >1,000 mailboxes from on-premises Exchange to Exchange Online
- At least 1 reference project demonstrating hybrid identity (Azure AD Connect) and Exchange Hybrid configuration

**MQ-2 - UK Public Sector Experience**:
- Minimum 2 reference projects for UK Central Government departments or UK public sector organizations within past 5 years
- Demonstrated understanding of Government Security Classifications Policy (OFFICIAL/OFFICIAL-SENSITIVE)
- Experience with NCSC Cloud Security Principles compliance

**MQ-3 - Microsoft Certifications**:
- Team must include at minimum:
  - 1× Microsoft Certified: Identity and Access Administrator Associate (Azure AD/Entra ID)
  - 1× Microsoft 365 Certified: Messaging Administrator Associate (Exchange Online)
  - 1× Microsoft Certified: Security, Compliance, and Identity Fundamentals (minimum) or Microsoft Certified: Security Operations Analyst Associate (preferred)
  - 1× Microsoft Certified: Azure Solutions Architect Expert (preferred) or Microsoft Certified: Azure Administrator Associate (minimum)

**MQ-4 - Security Compliance**:
- Company must hold ISO 27001:2013 (or ISO 27001:2022) certification (current, not expired)
- Company must hold Cyber Essentials Plus certification (UK Government requirement for public sector contracts >£5M cumulative)
- Evidence of compliance with UK GDPR (Data Protection Act 2018)

**MQ-5 - Financial Stability**:
- Company must provide audited financial statements for past 2 years demonstrating financial stability
- Minimum annual revenue: £5M
- Minimum 5 years in business
- Professional liability insurance: £5M minimum coverage
- Cyber liability insurance: £3M minimum coverage

**MQ-6 - UK Presence**:
- Vendor must have UK office/presence with on-site resources available for hybrid configuration (on-prem Exchange datacenter access required)
- Solution Architect and Technical Lead must be UK-based (for SIRO/CISO meetings and architecture reviews)

**MQ-7 - Personnel Security**:
- All vendor staff with access to Cabinet Office data must hold Baseline Personnel Security Standard (BPSS) clearance minimum
- Key personnel (Solution Architect, Technical Lead, Migration Leads) must obtain Security Check (SC) clearance (Cabinet Office will sponsor, vendor responsible for vetting process costs)

**MQ-8 - Accessibility Compliance**:
- Demonstrated experience delivering WCAG 2.1 Level AA compliant training materials or documentation
- Evidence of accessibility testing capabilities (Pa11y, Axe, manual keyboard/screen reader testing)

**MQ-9 - Migration Tooling**:
- Vendor must have proven experience with enterprise migration tools (BitTitan MigrationWiz, Quest On Demand Migration, or native Microsoft tooling)
- Migration tool must support: incremental sync, zero-downtime cutover, item-level validation, rollback capability

### 6.2 Preferred Qualifications (SCORED)

Preference will be given to vendors with the following (scored in evaluation):

**PQ-1 - Microsoft Partner Status**:
- Microsoft Gold Partner (or Solutions Partner Expert designation under new Microsoft Cloud Partner Program)
- Advanced Specialization in "Modernization of Web Applications to Microsoft Azure" or "Adoption and Change Management"

**PQ-2 - UK Government Frameworks**:
- Listed on Crown Commercial Service (CCS) G-Cloud 14 or Digital Outcomes and Specialists (DOS) framework
- Experience delivering services via Government frameworks

**PQ-3 - Security Certifications**:
- SOC 2 Type II certification
- Team includes NCSC CHECK Team Member (CTM) or CREST certified penetration testers

**PQ-4 - Specialized Expertise**:
- Experience with Microsoft Purview Information Protection (sensitivity labels, auto-labeling, DLP)
- Experience with Microsoft Defender for Office 365 (Plan 2) deployment and tuning
- Experience with Microsoft Sentinel integration for M365 audit log ingestion
- Experience with Power Platform governance (Power Automate, Power Apps CoE)

**PQ-5 - Change Management Maturity**:
- Prosci-certified change management practitioners on team
- Demonstrated success with large-scale user adoption programs (>1,000 users)
- M365 Champions program experience

**PQ-6 - Accessibility Expertise**:
- Team includes accessibility consultant or IAAP Certified Professional in Accessibility Core Competencies (CPACC)
- Experience delivering to WCAG 2.2 Level AA (preferred, vs 2.1)

### 6.3 Approved Technology Stack

The following technologies are mandated by Cabinet Office Architecture Principles:

**Cloud Platform** (MANDATORY):
- Microsoft Azure UK regions (UK South, UK West)
- No other cloud providers permitted

**Microsoft 365 Services** (MANDATORY):
- Exchange Online (M365 E5)
- Azure AD / Microsoft Entra ID
- Microsoft Purview (Information Protection, Records Management, eDiscovery)
- Microsoft Defender for Office 365 (Plan 2)
- Microsoft Intune (Mobile Device Management)
- Microsoft Sentinel (SIEM)

**Identity** (MANDATORY):
- Azure AD Connect (hybrid identity)
- Conditional Access
- Privileged Identity Management (PIM)

**Migration Tooling** (VENDOR PROPOSED):
- Vendor may propose migration tooling (BitTitan MigrationWiz, Quest On Demand, Microsoft native tools, etc.)
- Justification required in proposal (cost, capabilities, experience)

**Infrastructure as Code** (MANDATORY):
- Microsoft365DSC (Desired State Configuration) for M365 tenant configuration
- Terraform or Bicep for Azure resources (if Azure infrastructure deployed)
- Version control: Git (GitHub.com or Azure DevOps)

**Documentation** (MANDATORY):
- C4 model for architecture diagrams
- Markdown for runbooks and documentation (stored in SharePoint Online, version-controlled)

**Accessibility Testing** (MANDATORY):
- Pa11y and/or Axe DevTools for automated WCAG testing
- Manual testing with NVDA and/or JAWS screen readers

**Alternative Technologies**: Vendors may NOT propose alternative technologies without prior written approval from Cabinet Office CTO.

### 6.4 Team Requirements

**Minimum Team Composition**:

| Role | Qty | Required Experience | Certifications | Allocation |
|------|-----|---------------------|----------------|------------|
| **Solution Architect** | 1 | 10+ years, M365 architecture, UK public sector | Microsoft Certified: Azure Solutions Architect Expert | 50% minimum |
| **Security Architect** | 1 | 8+ years, NCSC Cloud Security Principles, OFFICIAL classification | CISSP or equivalent | 25% minimum |
| **Technical Lead (Migration)** | 1 | 8+ years, Exchange Online migration, Azure AD Connect, hybrid | Microsoft 365 Messaging Administrator | 75% minimum |
| **Change Manager** | 1 | 5+ years, large-scale change programs, Prosci ADKAR (preferred) | Prosci Change Management (preferred) | 50% minimum |
| **Migration Engineers** | 3 | 5+ years, Exchange migration, PowerShell scripting | Microsoft 365 Messaging Administrator (preferred) | 100% during migration phases |
| **Security Engineer** | 1 | 5+ years, Purview, Defender for Office 365, Conditional Access | Microsoft Security Operations Analyst (preferred) | 50% minimum |
| **Training Lead** | 1 | 5+ years, M365 training delivery, accessibility (WCAG) | Microsoft Certified Trainer (MCT) (preferred) | 50% minimum |
| **Project Manager** | 1 | 8+ years, large-scale IT projects, UK public sector | PRINCE2 Practitioner or PMP | 75% minimum |
| **Technical Writer** | 1 | 3+ years, technical documentation, accessibility (WCAG 2.2 AA) | Technical writing certification (preferred) | 25% minimum |
| **Accessibility Consultant** | 1 | 3+ years, WCAG 2.1/2.2 compliance testing | IAAP CPACC (preferred) | 10% (on-call) |

**Key Personnel Requirements**:
- Key personnel (Solution Architect, Security Architect, Technical Lead, Change Manager, Project Manager) must be dedicated for at least 50% allocation (except where higher allocation specified)
- Resumes for ALL key personnel must be included in proposal (max 2 pages each)
- Key personnel cannot be changed without Cabinet Office approval (substitution requires equivalent qualifications and Cabinet Office CTO sign-off)
- CVs must demonstrate UK public sector experience and relevant certifications

**Personnel Security**:
- All staff with access to Cabinet Office systems or data: BPSS clearance minimum
- Key personnel (Solution Architect, Security Architect, Technical Lead, Migration Engineers): Security Check (SC) clearance (Cabinet Office sponsored, vendor pays vetting costs)
- Clearance timeline: 6-8 weeks for BPSS, 8-12 weeks for SC (must be factored into project timeline)

**On-Site Requirements**:
- Solution Architect, Security Architect, Technical Lead: On-site availability in London for architecture reviews, SIRO meetings (expect 2 days/month)
- Migration Engineers: On-site availability for Exchange Hybrid configuration (datacenter access, expect 1 week on-site for hybrid setup)
- Training Lead: On-site availability for executive training sessions (expect 1-2 days during Months 8-9)

**Onshore/Offshore Model**:
- Solution Architect, Security Architect, Technical Lead, Project Manager, Change Manager: MUST be UK-based (onshore)
- Migration Engineers: UK-based preferred, nearshore (EU) acceptable with justification
- Training delivery: UK-based required (for on-site sessions)
- Documentation / development work: Offshore acceptable with UK-based oversight

---

## 7. Proposal Requirements

### 7.1 Proposal Format

Proposals must be submitted in TWO SEPARATE DOCUMENTS:
1. **Technical Proposal** (sections 1-7, 9 below)
2. **Cost Proposal** (section 8 below, SEPARATE FILE)

**Format Requirements**:
- PDF format (not Word or other formats)
- File naming: `[VENDOR_NAME]_CAB_RFP_2025-001_Technical.pdf` and `[VENDOR_NAME]_CAB_RFP_2025-001_Cost.pdf`
- Page limits enforced (proposals exceeding page limits will be rejected)
- Font: Arial or Calibri, 11pt minimum, 1.5 line spacing minimum
- Accessibility: PDF must be accessible (tagged PDF, WCAG 2.1 Level AA compliant)

#### Section 1: Executive Summary (3 pages max)
- High-level understanding of Cabinet Office requirements
- Proposed approach (migration strategy, phasing, change management)
- Key differentiators (why your team is best qualified)
- Summary of costs (total project cost, ongoing support cost)

#### Section 2: Company Overview (5 pages max)
- Company history, size, UK presence
- Relevant expertise (M365 migration, UK public sector)
- Certifications (ISO 27001, Cyber Essentials Plus, Microsoft Partner status)
- Financial stability evidence (annual revenue, years in business)
- Insurance certificates (professional liability £5M, cyber liability £3M)

#### Section 3: Understanding of Requirements (10 pages max)
- Demonstrated understanding of Cabinet Office business drivers (end-of-support, TCoP compliance, flexible working)
- Analysis of key challenges:
  - Zero data loss across 3,500 mailboxes (52TB)
  - UK data sovereignty (UK South/UK West, Customer Lockbox)
  - OFFICIAL/OFFICIAL-SENSITIVE classification controls
  - Ministerial office migration sensitivity (Phase 3, weekend cutover)
  - Change freeze Q4 constraint (Budget preparation period)
- Identified risks and proposed mitigations
- Questions/clarifications needed (addressed in proposal Q&A section)

#### Section 4: Technical Solution (40 pages max)

**4.1 High-Level Architecture** (10 pages):
- C4 Context diagram (Cabinet Office M365 tenant in context of on-prem Exchange, Azure AD, Intune, Sentinel)
- C4 Container diagram (Exchange Online, Azure AD, Purview, Defender, Intune, Sentinel containers)
- Hybrid identity architecture (Azure AD Connect, password hash sync, SSO)
- Exchange Hybrid architecture (coexistence, mailbox move, free/busy federation)
- Network architecture (on-prem to Azure connectivity, MX record cutover, Autodiscover)

**4.2 Migration Strategy** (15 pages):
- Migration tooling selection and justification (BitTitan, Quest, Microsoft native, etc.)
- Hybrid coexistence approach (on-prem + cloud during 6-month phased migration)
- Phased migration approach:
  - Pilot (100 users, Finance directorate): validation, lessons learned, go/no-go criteria
  - Phase 1-3: batch sizing (300 mailboxes per weekend), scheduling (avoid Q4 freeze), user notifications
- Item-level validation approach (item count match, folder structure, calendar accuracy)
- Rollback procedures (30-day window, on-prem mailbox re-enable, MX record revert)
- Data integrity assurance (zero data loss, corrupted item handling)

**4.3 Security and Compliance** (10 pages):
- Conditional Access policies (MFA, device compliance, geofencing, high-risk controls)
- Microsoft Purview Information Protection:
  - Sensitivity labels (OFFICIAL, OFFICIAL-SENSITIVE): auto-labeling rules, encryption, visual markings
  - DLP policies: block external OFFICIAL-SENSITIVE, detect NI numbers, alert SOC
  - Retention policies: auto-application rules (Transitory 1yr, Financial 7yr, Policy Papers 20yr)
- Microsoft Defender for Office 365 (Plan 2): Safe Links, Safe Attachments, anti-phishing, anti-impersonation
- Intune device compliance: MDM policies (PIN, OS version, jailbreak detection), remote wipe
- Unified Audit Log: 7-year retention, Sentinel integration (Event Hub)
- NCSC Cloud Security Principles compliance mapping (all 14 principles addressed)
- GDPR compliance (PIA support, SAR procedures, ICO breach notification <72 hours)

**4.4 Integration Approach** (3 pages):
- Azure AD (Entra ID): OAuth 2.0, Conditional Access integration
- Intune: Device compliance integration with Conditional Access
- Sentinel: Event Hub streaming (UAL events, DLP violations, Defender alerts)
- Third-party applications: SMTP relay testing, calendar integration (Outlook), authentication (SSO)

**4.5 Performance and Scalability** (2 pages):
- Performance targets: Email delivery <30s, OWA load <2s, migration throughput 300 mailboxes/48hrs
- Load testing approach (peak load: 3,500 users, 175,000 emails/day)
- Scalability: support 30% user growth over 3 years (3,500 → 4,550 users)

#### Section 5: Project Approach and Methodology (15 pages max)

**5.1 Project Management Methodology** (5 pages):
- Delivery methodology (Agile, Waterfall, Hybrid)
- Project governance (steering committee, Architecture Review Board, Change Advisory Board)
- Communication and reporting (weekly status reports, monthly steering committee, dashboards)
- Issue and risk management (RAID log, escalation procedures)

**5.2 Migration Execution Plan** (5 pages):
- Detailed phasing (pilot, Phase 1-3): timelines, dependencies, go/no-go criteria
- Weekend cutover procedures (MX record update, Autodiscover redirect, user notifications)
- Validation procedures (item count, folder structure, calendar, permissions, performance)
- Rollback procedures (triggers, steps, timeline)

**5.3 Change Management and User Adoption** (5 pages):
- Change management framework (ADKAR model or equivalent)
- M365 Champions network (recruitment, training, peer support)
- Training strategy:
  - Role-based training (end users, administrators, executives)
  - Delivery formats (eLearning, instructor-led, quick reference guides, videos)
  - Accessibility compliance (WCAG 2.2 AA)
- Service desk preparation (knowledge articles, escalation procedures)
- User communications (email campaigns, intranet, town halls)
- Adoption metrics and success criteria (training completion 100%, user satisfaction >80%)

#### Section 6: Team and Resources (10 pages max)
- Proposed team structure and org chart
- Key personnel resumes (2 pages each max): Solution Architect, Security Architect, Technical Lead, Change Manager, Project Manager
- Team allocation and timeline (Gantt chart showing resource allocation by phase)
- Onshore/offshore/nearshore model (if applicable)
- Personnel security (BPSS/SC clearance timeline and costs)
- Key personnel continuity commitment (no changes without Cabinet Office approval)

#### Section 7: Experience and References (15 pages max)

Minimum 3 reference projects (5 pages each) demonstrating M365 migration experience. Each reference MUST include:

**Reference Project Template**:
- **Client Name and Contact Information**: Name, organization, email, phone (we will contact references)
- **Project Scope and Size**: Number of mailboxes migrated, data volume, timeline
- **Project Dates**: Start and end dates (must be within past 5 years)
- **Technologies Used**: Exchange version (on-prem), Exchange Online, migration tooling, security tools (Purview, Defender)
- **Challenges Overcome**: Technical challenges, migration complexity, data integrity issues
- **Outcomes Achieved**: Zero data loss? User satisfaction? On-time/on-budget?
- **Relevance to Cabinet Office**: UK public sector? Government Security Classifications? NCSC compliance?

**At least ONE reference must demonstrate**:
- UK Central Government or UK public sector organization
- OFFICIAL/OFFICIAL-SENSITIVE data classification handling
- NCSC Cloud Security Principles compliance

**Additional Experience** (5 pages):
- UK Government frameworks (G-Cloud, DOS)
- Industry awards or recognition
- Case studies (anonymized if confidential)

#### Section 8: Cost Proposal (SEPARATE FILE - no page limit)

**CRITICAL**: Cost proposal must be submitted in a SEPARATE PDF file to allow technical evaluation independent of cost.

**8.1 Pricing Model**:
- Fixed Price OR Time & Materials (specify)
- If Fixed Price: Total lump-sum price for all deliverables
- If T&M: Hourly/daily rates by role, estimated hours, total estimated cost, not-to-exceed cap

**8.2 Cost Breakdown**:

| Cost Category | Description | Amount (GBP £) |
|---------------|-------------|----------------|
| **Planning & Design** | Current state assessment, HLD, DLD, security design, PIA support | |
| **M365 Configuration** | Azure AD Connect, Conditional Access, Purview, Defender, Intune, Sentinel, M365DSC baseline | |
| **Migration Execution** | Pilot + Phase 1-3 migration (3,500 mailboxes), validation, rollback procedures | |
| **Training & Change Management** | Change plan, Champions network, training materials, delivery, service desk prep | |
| **Documentation & Knowledge Transfer** | Architecture docs, admin guides, runbooks, user manuals, KT sessions | |
| **Testing** | Pilot testing, UAT, performance testing, security testing (NCSC CHECK pen test), accessibility testing, DR testing | |
| **Project Management** | Project manager, reporting, governance, RAID management | |
| **Migration Tooling** | BitTitan MigrationWiz licenses (or equivalent), 3,500 mailboxes | |
| **Third-Party Costs** | NCSC CHECK pen test, accessibility audit, travel expenses (if applicable) | |
| **Contingency** | Percentage and justification | |
| **TOTAL PROJECT COST** | | |

**8.3 Payment Milestones** (for Fixed Price proposals):

| Milestone | Deliverables | Payment (% of Total) | Amount (GBP £) |
|-----------|--------------|----------------------|----------------|
| Contract Signed | Signed contract | 10% | |
| Design Approval (M2) | HLD, DLD, security design, migration plan approved | 15% | |
| Pilot Complete (M3) | 100 users migrated, validated, go/no-go decision | 15% | |
| Phase 1 Complete (M4) | 1,200 users migrated | 20% | |
| Phase 2 Complete (M5) | 1,200 users migrated | 20% | |
| Phase 3 Complete (M6) | 1,000 users + execs migrated, all migrations complete | 15% | |
| Project Closure (M9) | Knowledge transfer complete, warranty begun, post-implementation review | 5% | |
| **TOTAL** | | **100%** | |

**8.4 Ongoing Support and Maintenance** (Post-Warranty, Optional):

**Warranty Period** (included in project cost):
- 90 days post-migration (Months 10-12)
- All defects fixed at no cost
- Response times: Critical 4 hours, Non-critical 2 business days

**Post-Warranty Support** (optional annual contract):

| Support Tier | Description | Annual Cost (GBP £) |
|--------------|-------------|---------------------|
| **L2 Support** | M365 configuration support, mailbox management, security policy tuning | |
| **L3 Support** | Architecture advisory, complex troubleshooting, escalations from Cabinet Office IT | |
| **Retained Services** | Ad-hoc consulting (e.g., new features, policy changes), X hours/month included | |

**8.5 Pricing Assumptions and Exclusions**:
- Microsoft 365 E5 licenses provided by Cabinet Office (3,500 licenses, cost excluded)
- Azure subscription and infrastructure costs provided by Cabinet Office (UK South/UK West, cost excluded)
- Network bandwidth (100 Mbps to Azure) provided by Cabinet Office (cost excluded)
- On-premises Exchange Server access provided by Cabinet Office (admin credentials, datacenter access)
- BPSS/SC clearance vetting: Cabinet Office sponsors, vendor pays vetting costs (included above? specify)
- Travel expenses: If T&M, specify daily rate. If Fixed Price, include estimate above.
- Out-of-scope items: SharePoint migration, Teams deployment, third-party email security, .PST import, email signatures (all excluded)

**8.6 Pricing Terms**:
- Payment terms: Net 30 days from invoice date
- Invoicing: Upon milestone completion (for Fixed Price) or monthly in arrears (for T&M)
- Currency: GBP (£ Pound Sterling)
- Pricing validity: 120 days from proposal submission
- Rate escalation: None during project (fixed rates), or specify annual escalation % for post-warranty support

#### Section 9: Assumptions, Dependencies, and Risks (5 pages max)

**9.1 Key Assumptions**:
- Example: "Users have modern devices (Windows 10/11, macOS 11+, 8GB RAM)" (from requirements document Assumption A-001)
- Example: "Cabinet Office provides Exchange 2016 admin access within 1 week of contract signing"
- List all assumptions affecting timeline, cost, or scope

**9.2 Dependencies on Cabinet Office**:
- Example: "Cabinet Office SIRO and ARB approvals within 5 business days of deliverable submission"
- Example: "Cabinet Office provides 3 SMEs (Exchange admin, Azure AD admin, info governance lead) allocated 25% each"
- List all dependencies requiring Cabinet Office action

**9.3 Identified Risks and Mitigations**:

| Risk ID | Risk Description | Probability | Impact | Mitigation Strategy |
|---------|------------------|-------------|--------|---------------------|
| R-001 | Exchange Hybrid configuration fails (certificate/federation issues) | MED | HIGH | Pre-migration lab testing, Microsoft Premier Support engagement |
| R-002 | Large mailboxes (>50GB) fail weekend cutover | MED | MED | Pre-migration mailbox cleanup, split large mailboxes across multiple weekends |
| ... | (Include risks from requirements document + additional vendor-identified risks) | | | |

### 7.2 Submission Instructions

**Deadline**: Proposals must be received by **2025-12-15 at 17:00 GMT**

**Submission Method**: Email to **procurement@cabinetoffice.gov.uk**
- Subject Line: "RFP-CAB-2025-001 - Exchange Online Migration - [VENDOR_NAME]"
- Email body: Brief cover letter (1 page max)
- Attachments:
  1. Technical Proposal PDF: `[VENDOR_NAME]_CAB_RFP_2025-001_Technical.pdf`
  2. Cost Proposal PDF: `[VENDOR_NAME]_CAB_RFP_2025-001_Cost.pdf`
  3. Company certifications (ISO 27001, Cyber Essentials Plus, insurance certificates)
  4. Microsoft Partner certificates (if applicable)
  5. Financial statements (past 2 years, redacted if sensitive)

**File Size Limit**: 25 MB total (compress images if needed)

**Late Proposals**: Will NOT be accepted. Email timestamp is official submission time.

**Questions**:
- Submit questions by **2025-10-31** to **procurement@cabinetoffice.gov.uk**
- Subject Line: "RFP-CAB-2025-001 - Question"
- All questions and answers will be published to all vendors by **2025-11-07**
- No proprietary or confidential information in questions (visible to all vendors)
- Final Q&A document will be emailed to all vendors who downloaded the RFP

**Confidentiality**:
- Non-Disclosure Agreement (NDA) required before detailed requirements or data sharing
- Proposals will be treated as confidential (not shared with other vendors)
- Cost proposals will only be opened for shortlisted vendors

---

## 8. Evaluation Criteria

### 8.1 Evaluation Process

Proposals will be evaluated in **three phases**:

**Phase 1: Mandatory Qualifications Check** (Week 1 post-submission)
- Pass/Fail review of mandatory qualifications (MQ-1 through MQ-9, Section 6.1)
- Vendors failing ANY mandatory qualification will be disqualified (no appeal)
- Cabinet Office reserves the right to request clarifications or evidence for mandatory qualifications

**Phase 2: Technical Evaluation** (Weeks 2-6 post-submission)
- Cost proposals remain SEALED (not opened)
- Technical scoring (see Section 8.2 below, 100-point scale)
- Evaluation committee: CTO, Enterprise Architect, SIRO, CISO, Change Manager, Procurement Lead
- Shortlisting of top 3-5 vendors based on technical score (minimum 70 points required to shortlist)

**Phase 3: Cost Evaluation and Vendor Presentations** (Weeks 7-10 post-submission)
- Cost proposals opened ONLY for shortlisted vendors
- Combined technical and cost scoring (see Section 8.3 below)
- Vendor presentations (2 hours each): 1-hour presentation, 1-hour Q&A with evaluation committee
- Reference checks (contacting 3 references per vendor)
- Final selection based on combined score and "best value" (not necessarily lowest price)

### 8.2 Technical Evaluation Criteria (100 points total)

Cost proposals remain sealed during technical evaluation. Technical scoring is independent of cost.

| Criteria | Weight | Max Points | Evaluation Focus |
|----------|--------|------------|------------------|
| **1. Technical Solution and Architecture** | 30% | 30 | Architecture quality (C4 diagrams, hybrid identity, Exchange Hybrid), migration strategy (zero data loss, phased approach), security design (NCSC compliance, Purview, Defender), UK data residency (UK South/UK West), integration approach (Azure AD, Intune, Sentinel) |
| **2. Migration Approach and Data Integrity** | 25% | 25 | Migration tooling justification, item-level validation procedures, rollback capability, data integrity assurance (zero data loss commitment), phased migration plan (pilot, Phase 1-3), weekend cutover procedures, Ministerial office sensitivity handling |
| **3. Security and Compliance** | 20% | 20 | NCSC Cloud Security Principles compliance (all 14 principles), OFFICIAL/OFFICIAL-SENSITIVE classification controls (sensitivity labels, DLP, audit logging), GDPR compliance (PIA support, SAR procedures), penetration testing (NCSC CHECK), Conditional Access policies, encryption (TLS 1.3, AES-256, Azure RMS) |
| **4. Team Qualifications and Experience** | 15% | 15 | Team expertise (certifications, UK public sector experience), key personnel CVs (Solution Architect, Security Architect, Technical Lead, Change Manager), team allocation (adequate resources), personnel security (BPSS/SC clearance plan), continuity commitment |
| **5. Change Management and User Adoption** | 7% | 7 | Change management framework (ADKAR or equivalent), M365 Champions network, training strategy (role-based, accessibility-compliant WCAG 2.2 AA), service desk preparation, user communications, adoption metrics |
| **6. Relevant Experience and References** | 3% | 3 | UK Central Government references, OFFICIAL classification experience, similar-scale migrations (>1,000 mailboxes), recent projects (past 3 years), reference quality (contactable, positive outcomes) |
| **TOTAL** | **100%** | **100** | Minimum 70 points required to shortlist for Phase 3 |

**Scoring Rubric (per criterion)**:
- **Excellent (90-100%)**: Exceeds requirements, innovative approach, proven track record, comprehensive detail
- **Good (75-89%)**: Meets all requirements, sound approach, relevant experience, adequate detail
- **Acceptable (60-74%)**: Meets minimum requirements, standard approach, some relevant experience, sufficient detail
- **Poor (<60%)**: Does not meet requirements, unclear approach, limited experience, insufficient detail

### 8.3 Cost Evaluation and Final Scoring (Phase 3 - Shortlisted Vendors Only)

**Cost Scoring Method**: Lowest Price Best Value

- Lowest cost proposal among shortlisted vendors receives maximum cost points (30 points)
- Other proposals scaled proportionally:
  - Cost Score = (Lowest Proposal Cost / Vendor Proposal Cost) × 30 points

**Example**:
- Vendor A: £800K (lowest) = 30 points
- Vendor B: £1,000K = (£800K / £1,000K) × 30 = 24 points
- Vendor C: £1,200K = (£800K / £1,200K) × 30 = 20 points

**Final Score Calculation**:
- **Technical Score**: 70% weight (from Phase 2, max 100 points)
- **Cost Score**: 30% weight (from Phase 3, max 30 points)
- **Final Score** = (Technical Score × 0.7) + (Cost Score × 0.3)

**Example Final Scores**:
- Vendor A: (85 × 0.7) + (30 × 0.3) = 59.5 + 9.0 = **68.5 points**
- Vendor B: (92 × 0.7) + (24 × 0.3) = 64.4 + 7.2 = **71.6 points** (WINNER - best value, not lowest price)
- Vendor C: (78 × 0.7) + (20 × 0.3) = 54.6 + 6.0 = **60.6 points**

**Best Value Determination**:
- Vendor with highest final score wins (not necessarily lowest price)
- Evaluation committee reserves the right to consider qualitative factors:
  - Confidence in vendor's ability to deliver
  - Cultural fit and communication quality (from vendor presentation)
  - Reference feedback quality
  - Risk assessment (financial stability, resource availability, UK presence)

### 8.4 Vendor Presentations (Shortlisted Vendors Only)

**Format**: Virtual presentations via Microsoft Teams (on-site presentations permitted if vendor prefers)

**Duration**: 2 hours per vendor
- 1 hour: Vendor presentation (PowerPoint or equivalent)
- 1 hour: Q&A with evaluation committee

**Audience**: Evaluation committee (8-10 attendees)
- CTO (chair), Enterprise Architect, SIRO, CISO, IAO, Change Manager, Procurement Lead, IT Director

**Presentation Content Requirements**:
- Solution Architect presents technical solution (architecture, migration strategy, security)
- Change Manager presents change management and user adoption approach
- Technical Lead presents migration execution plan and data integrity assurance
- Project Manager presents project governance and timeline
- Team introductions (key personnel attending: Solution Architect, Security Architect, Technical Lead, Change Manager, Project Manager)

**Q&A Topics** (expect questions on):
- Zero data loss commitment (how will you guarantee 100% item count match?)
- Ministerial office migration sensitivity (how will you handle Phase 3 weekend cutover?)
- NCSC Cloud Security Principles compliance (specific controls for each principle)
- Rollback procedures (what are the triggers? how long does rollback take?)
- Change freeze Q4 constraint (how will you work around Budget preparation period?)
- Reference projects (specific outcomes, challenges overcome)

**Evaluation Factors** (scored qualitatively, influences final decision):
- Team cohesion and communication
- Depth of understanding (requirements, Cabinet Office environment)
- Clarity and professionalism of presentation
- Responsiveness to questions
- Confidence in delivery capability

### 8.5 Selection Decision and Notification

**Decision Authority**: Cabinet Office Procurement Board (chaired by CTO, includes CFO, SIRO, Procurement Director)

**Selection Criteria** (in priority order):
1. Highest final score (technical + cost)
2. Best value for money (not necessarily lowest price)
3. Confidence in vendor's ability to deliver (based on experience, references, presentation)
4. Risk assessment (financial stability, resource availability, cultural fit)

**Selection Timeline**:
- Vendor presentations: 2025-12-18 to 2026-01-08 (Weeks 9-12 post-RFP)
- Reference checks: 2026-01-09 to 2026-01-12 (Week 13)
- Final selection decision: 2026-01-12 (Week 13)
- Contract negotiation: 2026-01-13 to 2026-01-19 (Week 13)
- Contract signed: 2026-01-20
- All vendors notified: 2026-01-22

**Notification**:
- All vendors (including non-shortlisted) will receive outcome notification by email by **2026-01-22**
- Successful vendor: Formal award letter, contract negotiation invitation
- Unsuccessful vendors: Brief feedback on proposal strengths/weaknesses (upon request)

**Debriefing**:
- Unsuccessful vendors may request debrief meeting (30 minutes, virtual)
- Debrief available 5 business days after notification
- Debrief covers: scoring summary, proposal strengths/weaknesses, improvement suggestions

---

## 9. Contract Terms and Conditions

### 9.1 Contract Type

**Fixed Price Contract** (preferred)

Cabinet Office prefers fixed-price contracts for defined scope with milestone-based payments. Time & Materials proposals will be considered if vendor provides compelling justification and not-to-exceed cap.

### 9.2 Payment Terms

**Payment Schedule** (for Fixed Price contracts):

See Section 8.2 (Cost Proposal) for detailed milestone-based payment schedule. Summary:
- 10% upon contract signing
- 75% across migration milestones (design approval, pilot complete, Phase 1-3 complete)
- 15% upon project closure (knowledge transfer complete, warranty begun)

**Retainage**: 5% of total contract value held for 90 days post-migration (warranty period) to ensure defect resolution

**Invoicing**:
- Vendor submits invoice within 5 business days of milestone completion
- Invoice must include: Milestone description, deliverables completed, acceptance sign-off, payment amount
- Cabinet Office pays within 30 days of invoice receipt (Net 30)

**Payment Method**: BACS (UK bank transfer) or CHAPS for large amounts. Vendor must provide UK bank account details.

### 9.3 Acceptance Criteria

Each deliverable must meet defined acceptance criteria (see Section 4). Acceptance process:

1. **Vendor Submits Deliverable**: Email to procurement@cabinetoffice.gov.uk with deliverable attached
2. **Cabinet Office Reviews** (5 business days): Evaluation against acceptance criteria
3. **Cabinet Office Response**:
   - **Accepted**: Formal acceptance email, milestone payment triggered
   - **Rejected with Feedback**: Specific defects/gaps listed, vendor must remediate
   - **Clarifications Requested**: Questions sent to vendor, response within 2 business days
4. **Vendor Remediates** (if rejected): Addresses feedback, resubmits within agreed timeline
5. **Re-Review**: Cabinet Office reviews remediated deliverable (3 business days)
6. **Formal Acceptance Sign-Off**: Email confirmation, logged in project tracker

**Escalation**:
- If acceptance delayed beyond 5 business days, vendor may escalate to Project Sponsor
- If deliverable rejected 3 times, escalation to Procurement Board for resolution

**Acceptance Authority**:
- Technical deliverables (HLD, DLD, M365 config): Enterprise Architect and SIRO
- Migration deliverables (pilot, Phase 1-3): Change Manager and IT Director
- Training/documentation: Training Lead and Change Manager
- Project closure: CTO final sign-off

### 9.4 Warranty and Support

**Warranty Period**: 90 days from final migration completion (Month 9 go-live = warranty until Month 12)

**Warranty Coverage**:
- All defects identified during warranty period will be fixed at NO ADDITIONAL COST
- Defect definition: System behavior deviating from requirements document or acceptance criteria
- Exclusions: Changes to requirements, user error, third-party system failures, Cabinet Office configuration changes

**Response Times**:
- **Severity 1 (Critical)**: System down, >100 users affected, data loss
  - Response: 4 hours
  - Resolution: 8 hours (or workaround provided)
- **Severity 2 (High)**: Major feature broken, 10-100 users affected
  - Response: 8 hours
  - Resolution: 24 hours
- **Severity 3 (Medium)**: Minor feature issue, <10 users affected
  - Response: 2 business days
  - Resolution: 5 business days
- **Severity 4 (Low)**: Enhancement request, cosmetic issue
  - Response: 5 business days
  - Resolution: Best effort (may defer to post-warranty)

**Warranty Reporting**:
- Monthly warranty reports: Incidents logged, resolutions, outstanding issues
- Warranty closure report: Summary of all warranty activity, final sign-off

**Hypercare Support** (Months 10-11, 60 days):
- Dedicated vendor support team (Solution Architect, Technical Lead, Migration Engineer on-call)
- Daily stand-ups with Cabinet Office IT ops team (15 minutes, review incidents/issues)
- Proactive monitoring (Service Health dashboard, Unified Audit Log, user feedback)
- Escalation path: Service desk → Vendor → Cabinet Office IT ops → Vendor escalation (4-hour response)

### 9.5 Ongoing Support and Maintenance (Optional, Post-Warranty)

**Post-Warranty Support** (optional annual contract, negotiated separately):

Cabinet Office may elect to engage vendor for ongoing support beyond 90-day warranty. This is optional and will be negotiated as separate contract.

**Support Tiers** (indicative, final terms negotiated):
- **L2 Support**: M365 configuration support, mailbox management, security policy tuning, user escalations
- **L3 Support**: Architecture advisory, complex troubleshooting, vendor escalations
- **Retained Services**: Ad-hoc consulting (new features, policy changes, compliance assessments)

**Support SLA** (indicative):

| Severity | Response Time | Resolution Time |
|----------|---------------|-----------------|
| Severity 1 (Critical - System down) | 4 hours | 8 hours |
| Severity 2 (High - Major feature broken) | 8 hours | 24 hours |
| Severity 3 (Medium - Minor issue) | 1 business day | 5 business days |
| Severity 4 (Low - Enhancement) | 5 business days | Best effort |

**Annual Maintenance**: Includes bug fixes, security patches, minor configuration changes (up to X hours/month included, additional hours billed at agreed hourly rate)

**Contract Renewal**: Annual renewal with 60-day notice, rates subject to CPI escalation (max 3% annually)

### 9.6 Intellectual Property Rights

**Work Product Ownership**: All custom-developed work product and deliverables (HLD, DLD, documentation, training materials, scripts, M365 configurations) become the exclusive property of Cabinet Office upon final payment.

**Vendor Pre-Existing IP**: Vendor retains ownership of pre-existing IP, reusable frameworks, methodologies, and tools brought to the project. Vendor grants Cabinet Office perpetual, irrevocable, royalty-free license to use pre-existing IP necessary for operating the M365 environment.

**Open Source**: Vendor must disclose all open-source components and licenses used in scripts, tooling, or documentation. No GPL-licensed code permitted (due to copyleft restrictions). Permissive licenses (MIT, Apache 2.0, BSD) acceptable with disclosure.

**Microsoft Software**: Microsoft 365 software and services remain Microsoft's property under Microsoft licensing terms. Cabinet Office licenses (E5) provided by Cabinet Office.

### 9.7 Data and Security

**Data Ownership**: Cabinet Office retains exclusive ownership of all data (mailbox content, audit logs, user data, configuration data).

**Data Security**: Vendor must comply with:
- Cabinet Office M365 Architecture Principles (see Appendix B)
- Government Security Classifications Policy (OFFICIAL/OFFICIAL-SENSITIVE handling)
- NCSC Cloud Security Principles (all 14 principles)
- UK GDPR and Data Protection Act 2018

**Data Handling**:
- Vendor must NOT use Cabinet Office data for vendor's own purposes (analytics, AI training, marketing)
- Data access limited to vendor personnel with BPSS or SC clearance and need-to-know
- Data access logged (Unified Audit Log) and monitored
- Data encryption in transit (TLS 1.3) and at rest (AES-256)
- Data must NOT leave UK geographic boundaries (Azure UK South/UK West regions only)

**Data Return/Destruction** (upon contract termination):
- Vendor must return all Cabinet Office data within 30 days
- Secure deletion of all data from vendor systems (NIST 800-88 or equivalent)
- Certificate of destruction provided to Cabinet Office

**Data Processing Agreement (DPA)**: Vendor must sign DPA (UK GDPR Article 28) before accessing any personal data. DPA template provided by Cabinet Office, vendor may propose amendments for negotiation.

**Background Checks**: All vendor personnel with access to Cabinet Office data or systems must pass:
- **BPSS (Baseline Personnel Security Standard)**: Minimum for all staff (identity verification, right to work, employment history 3 years, criminal record check)
- **SC (Security Check)**: Required for key personnel (Solution Architect, Security Architect, Technical Lead, Migration Engineers) (BPSS + employment history 5 years, credit check, security questionnaire)
- Cabinet Office sponsors clearances, vendor pays vetting costs (£100-£150 per BPSS, £350-£500 per SC)

### 9.8 Confidentiality

**Non-Disclosure Agreement (NDA)**: Vendor must sign NDA before receiving detailed requirements, data, or access to Cabinet Office systems. NDA template provided by Cabinet Office (mutual confidentiality, 5-year term, UK jurisdiction).

**Confidential Information** includes:
- Requirements document, architecture principles, security design, M365 configuration details
- Mailbox data, user data, audit logs, organizational structure
- Cabinet Office internal communications, meeting notes, business strategies

**Exclusions**: Publicly available information, information independently developed by vendor, information received from third party without confidentiality obligation.

**Obligations**:
- Vendor must protect confidential information with same care as its own confidential information (minimum: reasonable care)
- Disclosure limited to vendor personnel with need-to-know and confidentiality obligations
- No disclosure to third parties without Cabinet Office written consent
- Return or destruction of confidential information upon contract termination

**Breach**: Unauthorized disclosure of OFFICIAL-SENSITIVE information is a serious security incident requiring immediate notification to Cabinet Office SIRO and potentially ICO (if personal data). Vendor may be liable for damages and breach of contract.

### 9.9 Liability and Indemnification

**Liability Cap**: Vendor's total cumulative liability under contract is capped at **1.5× total contract value** (e.g., if contract value is £1M, liability cap is £1.5M).

**Exceptions to Liability Cap** (unlimited liability):
- Data breaches due to vendor negligence or breach of security obligations
- Breaches of confidentiality obligations or NDA
- Fraud, willful misconduct, gross negligence
- Intellectual property infringement
- Death or personal injury caused by vendor negligence

**Indemnification**: Vendor indemnifies and holds harmless Cabinet Office against:
- **IP Infringement**: Claims that vendor's deliverables or tools infringe third-party intellectual property rights
- **Data Breach**: Claims arising from vendor's negligent handling of Cabinet Office data (breach of GDPR, security obligations)
- **Violations of Law**: Vendor's violation of UK laws, regulations, or Government Security Classifications Policy

**Indemnification Process**:
1. Cabinet Office notifies vendor of claim within reasonable time
2. Vendor assumes defense of claim (Cabinet Office may participate at its own cost)
3. Vendor may not settle claim without Cabinet Office consent
4. Vendor reimburses Cabinet Office for reasonable costs (legal fees, damages, settlements)

**Insurance**: Vendor must maintain adequate insurance:
- Professional liability (errors & omissions): £5M minimum
- Cyber liability (data breach, privacy): £3M minimum
- General liability: £5M minimum
- Certificates of insurance provided to Cabinet Office annually

### 9.10 Termination

**Termination for Convenience**: Cabinet Office may terminate contract at any time with 60 days' written notice, for any reason or no reason.
- Cabinet Office pays vendor for work completed to date (pro-rated based on milestones)
- Vendor provides transition assistance (30 days, at no additional cost)
- Vendor returns all Cabinet Office data and confidential information

**Termination for Cause**: Either party may terminate if other party:
- **Material Breach**: Breaches material terms and fails to cure within 30 days of written notice
  - Examples: Repeated failure to meet acceptance criteria, security breach, failure to provide key personnel
- **Insolvency**: Becomes insolvent, files bankruptcy, goes into administration
- **Force Majeure**: Force majeure event continues for >90 days

**Termination Procedure**:
1. Non-breaching party sends written notice of breach (specific breach, cure requirements, 30-day cure period)
2. Breaching party has 30 days to cure breach and provide evidence of cure
3. If not cured, non-breaching party sends termination notice (effective immediately or specified date)
4. Transition assistance and data return (see below)

**Transition Assistance** (upon termination):
- Vendor must provide 90 days of transition assistance to new vendor or Cabinet Office internal team
- Transition activities: Knowledge transfer, documentation handover, access credentials, M365 configuration export (M365DSC baseline)
- Transition assistance billed at **50% of standard hourly rates** (for termination for convenience) or **no charge** (for termination for cause by Cabinet Office)

**Effect of Termination**:
- All vendor access to Cabinet Office systems revoked immediately
- All Cabinet Office data returned or securely destroyed within 30 days
- Outstanding invoices for completed milestones paid (termination for convenience) or withheld pending dispute resolution (termination for cause)
- Confidentiality and IP provisions survive termination indefinitely
- Warranty survives for delivered and accepted work products

### 9.11 Change Management

**Change Request Process**:
1. **Initiation**: Either party submits written change request (email to procurement@cabinetoffice.gov.uk or vendor project manager)
2. **Impact Analysis**: Vendor provides impact analysis within 5 business days (cost, schedule, scope, risk impacts)
3. **Review**: Cabinet Office reviews impact analysis, may request clarifications or alternatives
4. **Decision**: Cabinet Office approves, rejects, or requests modifications
5. **Change Order**: Approved changes documented in formal change order (signed by both parties)
6. **Contract Amendment**: Contract updated to reflect scope, cost, schedule changes

**Change Request Content**:
- Description of requested change
- Justification (why change is needed, business benefit)
- Impact on scope, schedule, cost, risk
- Alternative approaches (if applicable)

**Approval Thresholds**:
- **Minor changes** (<£10K or <5 days schedule impact): Technical Lead approval
- **Medium changes** (£10K-£50K or 5-20 days schedule impact): Project Sponsor approval
- **Major changes** (>£50K or >20 days schedule impact): CTO / Procurement Board approval

**Change Control Board** (for major changes):
- Members: CTO (chair), Project Sponsor, Enterprise Architect, Procurement Lead, Vendor Project Manager
- Meetings: As-needed (convened within 10 business days of change request submission)
- Decision authority: CTO final decision

**Scope Creep Prevention**:
- All changes must go through formal change request process
- Vendor may not unilaterally change scope, even if beneficial
- "Gold plating" (adding features beyond requirements) not permitted without change order

---

## 10. Appendices

### Appendix A: Detailed Requirements

**Full requirements document attached separately**: `CAB-RFP-2025-001-Requirements.pdf`

**Requirements Summary** (48 total requirements):
- 7 Business Requirements (BR-001 to BR-007)
- 15 Functional Requirements (FR-001 to FR-015)
- 23 Non-Functional Requirements (Performance, Availability, Scalability, Security, Compliance, Usability, Maintainability, Interoperability)
- 3 Integration Requirements (INT-001 to INT-003)

**Critical Non-Negotiable Requirements** (failure to meet = disqualification):
- FR-003: UK Data Residency (UK South/UK West only)
- FR-004: Conditional Access Policies (MFA 100% users)
- FR-005: Sensitivity Labels (OFFICIAL, OFFICIAL-SENSITIVE)
- FR-006: DLP Policies (block external OFFICIAL-SENSITIVE)
- FR-007: Microsoft Defender for Office 365 (Plan 2)
- FR-008: Retention Policies (Public Records Act compliance)
- FR-011: Unified Audit Log (7-year retention)
- NFR-SEC-001 to NFR-SEC-005: All security requirements
- NFR-C-001 to NFR-C-003: All compliance requirements
- NFR-U-002: Accessibility (WCAG 2.2 AA - legal requirement)

### Appendix B: Cabinet Office M365 Architecture Principles

**Full architecture principles document attached separately**: `CAB-M365-Architecture-Principles.pdf`

**Principles Summary** (20 principles across 8 domains):

**Strategic Principles**:
1. Cloud-First with UK Sovereignty
2. Government Digital Service (GDS) Standard Compliance
3. Security by Design (OFFICIAL Classification)
4. Accessibility and Inclusion (WCAG 2.2 AA)
5. Open Standards and Interoperability

**Data Principles**:
6. Data Sovereignty and Classification
7. Data Quality and Lifecycle Management
8. Privacy by Design

**Technology Standards**:
9. Approved M365 Technology Stack
10. Infrastructure as Code and DevOps

**Architecture Patterns**:
11. Identity and Access Management (Zero Trust)
12. Information Governance and Records Management
13. Collaboration and External Sharing Governance

**Development and Customization**:
14. SharePoint Framework (SPFx) and Custom Development
15. Power Platform Governance and Center of Excellence

**Operational Excellence**:
16. Observability, Monitoring, and Incident Response
17. User Adoption and Change Management

**Financial Governance**:
18. FinOps and License Optimization

**Compliance and Audit**:
19. Audit Logging and eDiscovery
20. Compliance Score and Continuous Assessment

**Vendor Compliance**: All deliverables and solutions MUST align with these 20 principles. Architecture Review Board will validate compliance at design approval milestone.

### Appendix C: UK Government Standards and Compliance

**Technology Code of Practice (TCoP)** - All 10 points:
1. Define user needs
2. Make things accessible and inclusive
3. Use cloud first
4. Make use of open standards
5. Use open source
6. Make things secure
7. Make privacy integral
8. Share, reuse and collaborate
9. Integrate and adapt technology
10. Make better use of data

**GDS Service Standard** - 14 points (see requirements document for full list)

**NCSC Cloud Security Principles** - 14 principles:
1. Data in transit protection
2. Asset protection and resilience
3. Separation between users
4. Governance framework
5. Operational security
6. Personnel security
7. Secure development
8. Supply chain security
9. Secure user management
10. Identity and authentication
11. External interface protection
12. Secure service administration
13. Audit information for users
14. Secure use of the service

**WCAG 2.2 Level AA**: Public Sector Bodies (Websites and Mobile Applications) Accessibility Regulations 2018

**Government Security Classifications Policy**: OFFICIAL, OFFICIAL-SENSITIVE, SECRET (M365 approved for OFFICIAL and OFFICIAL-SENSITIVE only)

**UK GDPR and Data Protection Act 2018**: Data protection, privacy, subject access requests, breach notification

### Appendix D: Glossary

- **Azure AD (Entra ID)**: Microsoft's cloud-based identity and access management service
- **BPSS**: Baseline Personnel Security Standard (UK government vetting level)
- **CHECK**: NCSC scheme for IT security health checks (penetration testing)
- **DLP**: Data Loss Prevention (prevents unauthorized data disclosure)
- **eDiscovery**: Electronic discovery for email search and legal hold
- **Exchange Hybrid**: Coexistence configuration between on-prem Exchange and Exchange Online
- **IAO**: Information Asset Owner (responsible for data classification and governance)
- **Intune**: Microsoft's mobile device management (MDM) and mobile application management (MAM) service
- **MFA**: Multi-Factor Authentication (additional authentication beyond password)
- **M365DSC**: Microsoft 365 Desired State Configuration (Infrastructure-as-Code tool for M365)
- **NCSC**: National Cyber Security Centre (UK government cyber security authority)
- **OFFICIAL**: UK Government Security Classification for routine public sector business
- **OFFICIAL-SENSITIVE**: Subset of OFFICIAL requiring enhanced protective controls
- **OWA**: Outlook on the Web (browser-based email client)
- **PIM**: Privileged Identity Management (just-in-time admin access)
- **PST**: Personal Storage Table (Outlook mailbox export format)
- **SC**: Security Check (UK government vetting level, higher than BPSS)
- **SIRO**: Senior Information Risk Owner (accountable for information risk)
- **TLS**: Transport Layer Security (encryption protocol for email in transit)
- **UAL**: Unified Audit Log (M365 audit logging across all workloads)
- **WCAG**: Web Content Accessibility Guidelines (international accessibility standard)

### Appendix E: Contact Information and Questions

**Primary Contact**:
Procurement Team  
Cabinet Office, UK Government  
Email: procurement@cabinetoffice.gov.uk  
Phone: +44 (0)20 7276 1234

**Technical Lead**:
Enterprise Architecture Team  
Cabinet Office  
Email: enterprise.architecture@cabinetoffice.gov.uk

**Procurement Timeline**:
- RFP Issued: 2025-10-17
- Questions Due: 2025-10-31
- Answers Published: 2025-11-07
- Proposals Due: 2025-12-15 at 17:00 GMT

**Question Submission Format**:
- Email: procurement@cabinetoffice.gov.uk
- Subject: "RFP-CAB-2025-001 - Question"
- Body: Section reference, specific question, context/rationale

---

**Document Control**

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-10-17 | Cabinet Office Enterprise Architecture Team | Initial SOW/RFP issuance |

**Approvals**

| Role | Name | Signature | Date |
|------|------|-----------|------|
| CTO | [NAME] | _________ | 2025-10-17 |
| SIRO | [NAME] | _________ | 2025-10-17 |
| Procurement Director | [NAME] | _________ | 2025-10-17 |
| Legal Review | [NAME] | _________ | 2025-10-17 |

---

**Classification**: OFFICIAL

**END OF STATEMENT OF WORK**

*This document is issued by the Cabinet Office, UK Government, and should be handled in accordance with Government Security Classifications Policy.*
