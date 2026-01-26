# Project Requirements: Exchange Online Migration to Microsoft 365

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.requirements`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-REQ-v1.1 |
| **Document Type** | Business and Technical Requirements |
| **Project** | Exchange Online Migration to Microsoft 365 (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.1 |
| **Created Date** | 2025-10-17 |
| **Last Modified** | 2026-01-26 |
| **Review Cycle** | Quarterly |
| **Next Review Date** | 2026-04-26 |
| **Owner** | Cabinet Office IT Directorate |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Project Team, Stakeholders, Enterprise Architecture |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-10-17 | Enterprise Architecture Team | Initial comprehensive requirements based on Cabinet Office M365 Architecture Principles | PENDING | PENDING |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to align with ArcKit template v0.11.2 | PENDING | PENDING |

## Document Purpose

This document defines comprehensive business, functional, non-functional, integration, and data requirements for the Exchange Online Migration project. It serves as the authoritative specification against which the solution will be designed, built, and validated.

---

## Executive Summary

### Business Context

The Cabinet Office operates an on-premises Exchange Server 2016 infrastructure that has reached end-of-support lifecycle. This project migrates 3,500 user mailboxes to Microsoft Exchange Online, aligning with UK Government Technology Code of Practice (TCoP) Point 3 (Use cloud first) and delivering £800K annual cost savings.

### Objectives

- Migrate 100% of mailboxes to Exchange Online within 9 months
- Ensure UK data sovereignty (UK South/UK West regions only)
- Achieve zero data loss with comprehensive validation
- Enable secure mobile access via Intune and Conditional Access
- Reduce TCO by 40% (£2M/year → £1.2M/year)
- Comply with OFFICIAL data classification and NCSC Cloud Security Principles

### Project Scope

**In Scope**: 3,500 user mailboxes, 150 shared/resource mailboxes, DLP policies, sensitivity labels, Defender for Office 365, Intune MDM, retention policies, eDiscovery, decommissioning on-prem Exchange

**Out of Scope**: SharePoint migration (Project 002), Teams migration (completed), third-party email filtering, personal .PST files

---

## Business Requirements

### BR-001: Cloud-First Mandate Compliance
**Description**: Migrate from on-premises Exchange to Exchange Online per TCoP Point 3  
**Rationale**: UK Government mandates cloud-first for IT infrastructure  
**Success Criteria**: 100% mailboxes in Exchange Online, CTO sign-off, zero on-prem mailboxes  
**Priority**: MUST_HAVE  
**Aligns with**: Architecture Principle 1 (Cloud-First with UK Sovereignty)

### BR-002: Cost Reduction and Value for Money
**Description**: Deliver £800K annual savings through infrastructure elimination  
**Rationale**: Fiduciary duty to optimize taxpayer spending  
**Success Criteria**: TCO analysis shows £800K savings, monthly cost tracking  
**Priority**: MUST_HAVE  
**Aligns with**: Architecture Principle 18 (FinOps and License Optimization)

### BR-003: Business Continuity and Service Availability
**Description**: Achieve 99.9% SLA with UK multi-region resilience  
**Rationale**: Single datacenter creates unacceptable business risk  
**Success Criteria**: 99.9% uptime, RTO 4 hours, RPO 15 minutes, annual DR test  
**Priority**: MUST_HAVE  
**Aligns with**: Architecture Principle 16 (Observability and Incident Response)

### BR-004: Support for Flexible Working
**Description**: Enable secure mobile email access for hybrid working  
**Rationale**: Post-COVID flexible working requires mobile access  
**Success Criteria**: 100% users access via OWA/mobile, zero VPN dependency, 80%+ user satisfaction  
**Priority**: MUST_HAVE

### BR-005: Phased Migration Timeline
**Description**: Complete migration in 9 months with phased approach  
**Rationale**: Avoid hardware refresh costs due Month 12  
**Success Criteria**: Pilot Month 3, Phases 1-3 Months 5-9, zero data loss  
**Priority**: MUST_HAVE

### BR-006: User Adoption and Training
**Description**: Achieve 80%+ user proficiency within 1 month post-migration  
**Rationale**: Migration success depends on user adoption  
**Success Criteria**: 100% training completion, 50+ M365 Champions, 80%+ satisfaction  
**Priority**: MUST_HAVE  
**Aligns with**: Architecture Principle 17 (User Adoption and Change Management)

### BR-007: Government Security Classifications Compliance
**Description**: Maintain OFFICIAL/OFFICIAL-SENSITIVE classification controls  
**Rationale**: Legal obligation under Government Security Policy  
**Success Criteria**: Sensitivity labels configured, DLP enforced, 7-year audit logs, SIRO sign-off, CHECK assessment passed  
**Priority**: MUST_HAVE (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 3 (Security by Design), Principle 6 (Data Classification)

---

## Functional Requirements

### FR-001: Mailbox Migration with Zero Data Loss
**Description**: Migrate all mailbox content with 100% data integrity  
**Relates To**: BR-001, UC-002  
**Acceptance Criteria**:
- Given 10,000 emails on-prem, when migrated, then 10,000 emails in Exchange Online (100% match)
- Given calendar with 500 events, when migrated, then all events with correct date/time/attendees
- Given 200 contacts, when migrated, then all contacts with full details preserved
- Edge case: Corrupted items (<1%) logged and reported for manual review
**Priority**: MUST_HAVE  
**Complexity**: HIGH

### FR-002: Hybrid Identity with Azure AD Connect
**Description**: Synchronize on-prem AD to Azure AD for SSO  
**Acceptance Criteria**:
- Given 3,500 AD users, when synced, then 3,500 Azure AD accounts with matching UPN
- Given password change on-prem, when sync runs (30 min), then Azure AD updated within 30 min
- Given new user in AD, when synced, then user in Azure AD and licensed within 1 hour
**Priority**: MUST_HAVE  
**Complexity**: MEDIUM

### FR-003: UK Data Residency
**Description**: Store all mailbox data in UK South/UK West regions only  
**Acceptance Criteria**:
- Given new mailbox, when provisioned, then stored in UK South (verified via Get-Mailbox)
- Given Multi-Geo review, then Multi-Geo disabled (all data in UK)
- Given data audit, when Get-MailboxLocation run, then 100% report "United Kingdom"
**Priority**: MUST_HAVE (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 1 (Cloud-First with UK Sovereignty)

### FR-004: Conditional Access Policies (Zero Trust)
**Description**: Enforce MFA, device compliance, location-based access controls  
**Acceptance Criteria**:
- Given OWA access without MFA, when evaluated, then MFA challenge required
- Given non-compliant device, when accessing email, then access blocked
- Given non-UK IP (not approved), when evaluated, then access blocked or additional auth required
- Given high sign-in risk, when detected, then password change + MFA re-auth required
**Priority**: MUST_HAVE (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 11 (Identity and Access Management - Zero Trust)

### FR-005: Sensitivity Labels (OFFICIAL, OFFICIAL-SENSITIVE)
**Description**: Apply Microsoft Purview sensitivity labels to classify emails  
**Acceptance Criteria**:
- Given email sent, when no label selected, then "OFFICIAL" auto-applied
- Given content with "Cabinet Paper", when composed, then recommend "OFFICIAL-SENSITIVE"
- Given OFFICIAL-SENSITIVE label, when applied, then encryption + visual marking applied
- Given OFFICIAL-SENSITIVE to external recipient, when DLP evaluated, then email blocked
**Priority**: MUST_HAVE (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 6 (Data Sovereignty and Classification)

### FR-006: Data Loss Prevention (DLP) Policies
**Description**: Prevent unauthorized disclosure of OFFICIAL-SENSITIVE content  
**Acceptance Criteria**:
- Given OFFICIAL-SENSITIVE to external, when evaluated, then blocked with policy tip
- Given email with NI number pattern, when sent externally, then blocked and logged
- Given forward to personal Gmail, when evaluated, then blocked
- Given DLP violation, when incident occurs, then SOC alerted within 5 minutes
**Priority**: MUST_HAVE (NON-NEGOTIABLE)

### FR-007: Microsoft Defender for Office 365 (Plan 2)
**Description**: Protect against phishing, malware, zero-day attacks  
**Acceptance Criteria**:
- Given phishing URL, when received, then Safe Links rewrites and blocks at click-time
- Given malicious attachment, when received, then Safe Attachments detonates in sandbox and blocks
- Given BEC impersonation, when received, then anti-impersonation quarantines and alerts
- Given user reports phishing, when reported, then Defender re-analyzes and removes if confirmed malicious
**Priority**: MUST_HAVE (NON-NEGOTIABLE)

### FR-008: Retention Policies (Public Records Act)
**Description**: Apply retention aligned with Cabinet Office schedules  
**Acceptance Criteria**:
- Given "Policy Paper" label, when evaluated, then retained 20 years before disposition
- Given "Transitory" label, when evaluated, then auto-deleted after 1 year
- Given FOI legal hold, when applied, then retention suspended until hold released
- Given end of retention, when reached, then Records Manager notified for disposition approval
**Priority**: MUST_HAVE (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 12 (Information Governance)

### FR-009: eDiscovery and Legal Hold
**Description**: Support FOI requests, employment tribunals, litigation  
**Acceptance Criteria**:
- Given FOI request, when eDiscovery case created, then search all mailboxes with keywords/date range
- Given search results, when reviewed, then tag responsive/non-responsive and export to PST
- Given litigation, when legal hold applied, then all email preserved indefinitely
- FOI response SLA: 20 working days (eDiscovery search within 5 days)
**Priority**: MUST_HAVE

### FR-010: Intune Mobile Device Management
**Description**: Enforce device compliance for mobile email access  
**Acceptance Criteria**:
- Given iPhone without Intune, when accessing Exchange, then blocked and prompted to enroll
- Given Intune-enrolled iPhone, when evaluated, then require PIN (6 digits), iOS 16+, no jailbreak
- Given jailbroken Android, when evaluated, then marked non-compliant and access blocked
- Given lost device, when remote wipe issued, then corporate email data removed
**Priority**: MUST_HAVE

### FR-011: Unified Audit Log (7-Year Retention)
**Description**: Enable audit logging with 7-year retention for OFFICIAL records  
**Acceptance Criteria**:
- Given email send, when sent, then UAL records sender, recipient, subject, date/time, sensitivity label
- Given admin action, when performed, then UAL records admin UPN, action type, target, date/time
- Given audit search for "admin mailbox access", when executed, then returns 7-year history
- Given SIEM (Sentinel), when audit event created, then streamed to Sentinel in real-time
**Priority**: MUST_HAVE (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 19 (Audit Logging and eDiscovery)

### FR-012: Shared/Resource Mailboxes Migration
**Description**: Migrate 150 shared mailboxes and resource mailboxes  
**Acceptance Criteria**:
- Given shared mailbox "Finance-Enquiries", when migrated, then permissions preserved
- Given resource mailbox "Board Room 1", when migrated, then auto-accept booking policy enforced
- Given 50GB shared mailbox, when migrated, then 100% content migrated (zero data loss)
**Priority**: MUST_HAVE

### FR-013: Mail Flow Rules Migration
**Description**: Migrate and modernize transport rules  
**Acceptance Criteria**:
- Given on-prem rule "Block .exe attachments", when migrated, then recreated in Exchange Online
- Given rule "[EXTERNAL] prepend", when migrated, then functional in Exchange Online
- Given 50 on-prem rules, when migration reviewed, then 35 migrated (15 deprecated, replaced by M365 features)
**Priority**: MUST_HAVE

### FR-014: Outlook Web App (OWA) Access
**Description**: Provide browser-based email access with accessibility compliance  
**Acceptance Criteria**:
- Given Chrome on Windows, when navigating to outlook.office365.com, then authenticate and access mailbox
- Given personal laptop (non-Intune), when Conditional Access evaluates, then read-only access granted
- Given screen reader (NVDA), when navigating inbox, then screen reader announces senders/subjects (WCAG 2.2 AA)
- OWA page load: <2 seconds (95th percentile)
**Priority**: MUST_HAVE  
**Aligns with**: Architecture Principle 4 (Accessibility)

### FR-015: Outlook Desktop/Autodiscover Configuration
**Description**: Configure Outlook desktop client with Autodiscover  
**Acceptance Criteria**:
- Given Outlook opened post-migration, when Autodiscover queried, then Exchange Online endpoint returned and mailbox configured
- Given user enters email, when Autodiscover queried, then Outlook detects Exchange Online and prompts Azure AD SSO
- Given offline mode, when user disconnected, then read/compose emails (queued in Outbox)
**Priority**: MUST_HAVE

---

## Non-Functional Requirements

### Performance

#### NFR-P-001: Email Delivery Latency
**Requirement**: Email delivery <30 seconds (95th percentile)  
**Load**: 3,500 users, 175,000 emails/day peak  
**Priority**: HIGH

#### NFR-P-002: OWA Page Load Time
**Requirement**: OWA inbox load <2 seconds (95th percentile)  
**Load**: 1,050 concurrent OWA users (30% of user base)  
**Priority**: MEDIUM

#### NFR-P-003: Mailbox Migration Throughput
**Requirement**: 300 mailboxes per 48-hour weekend window  
**Load**: Average 15GB per mailbox, 100 Mbps bandwidth  
**Priority**: HIGH

### Availability and Resilience

#### NFR-A-001: Exchange Online Service Availability
**Requirement**: 99.9% uptime (SLA), max 43 min unplanned downtime/month  
**Priority**: CRITICAL  
**Aligns with**: Architecture Principle 1 (Cloud-First)

#### NFR-A-002: Disaster Recovery
**RPO**: 15 minutes (Microsoft continuous replication)  
**RTO**: 4 hours for email service restoration  
**Failover**: Automatic to UK West region <15 minutes  
**Priority**: CRITICAL

#### NFR-A-003: Fault Tolerance
**Requirement**: Graceful degradation when dependencies unavailable  
**Patterns**: Circuit breaker, retry with backoff, timeout on API calls, bulkhead isolation  
**Priority**: MEDIUM

### Scalability

#### NFR-S-001: User Growth Scalability
**Requirement**: Support 30% growth over 3 years without performance degradation  
**Projections**: Year 1: 3,500 users, Year 2: 4,000 users, Year 3: 4,550 users  
**Priority**: MEDIUM

#### NFR-S-002: Mailbox Storage Scalability
**Requirement**: Handle storage growth 52TB → 150TB over 3 years  
**Archival**: Auto-archive to Exchange Online Archive after 2 years  
**Priority**: MEDIUM

### Security (NON-NEGOTIABLE)

#### NFR-SEC-001: Multi-Factor Authentication Enforcement
**Requirement**: 100% users authenticate with MFA (no exceptions except 2 break-glass accounts)  
**Methods**: Microsoft Authenticator (preferred), FIDO2 security keys, SMS/phone (fallback)  
**Session**: 8 hours continuous use or 30 min inactivity timeout  
**Priority**: CRITICAL (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 11 (Zero Trust)

#### NFR-SEC-002: Role-Based Access Control (RBAC)
**Requirement**: RBAC with least privilege and PIM for just-in-time access  
**Roles**: Global Admin (5 max, PIM only), Exchange Admin (8, PIM), Security Admin (5), Compliance Admin (3), Helpdesk (10)  
**PIM**: Approval workflow for Global/Exchange Admin, 8-hour max activation  
**Priority**: CRITICAL (NON-NEGOTIABLE)

#### NFR-SEC-003: Encryption in Transit and at Rest
**Requirement**:
- In transit: TLS 1.3 mandatory for all SMTP transport
- At rest: AES-256 for all mailbox data (Microsoft-managed keys)
- OFFICIAL-SENSITIVE: Azure RMS encryption via sensitivity labels
**Priority**: CRITICAL (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 3 (Security by Design - NCSC Principle 1)

#### NFR-SEC-004: Secrets Management
**Requirement**: No credentials in code/config, all secrets in Azure Key Vault  
**Rotation**: Service account passwords 90 days, certificates 1 year, API keys 6 months  
**Priority**: CRITICAL (NON-NEGOTIABLE)

#### NFR-SEC-005: Vulnerability Management and Penetration Testing
**Requirement**: Continuous vulnerability scanning, annual NCSC CHECK penetration test  
**Remediation SLA**: Critical 24 hours, High 7 days, Medium 30 days  
**Priority**: CRITICAL  
**Aligns with**: Architecture Principle 3 (NCSC Principle 7: Secure Development)

### Compliance (NON-NEGOTIABLE)

#### NFR-C-001: UK GDPR and Data Protection Act 2018
**Regulations**: UK GDPR, Data Protection Act 2018  
**Requirements**: PIA completed, DPO approved, SAR procedures (20 days), data breach notification (<72 hours to ICO)  
**Data Residency**: UK only, no cross-border transfers except Microsoft support (Customer Lockbox approval)  
**Priority**: CRITICAL (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 8 (Privacy by Design)

#### NFR-C-002: Government Security Classifications Policy
**Requirement**: All email classified OFFICIAL or OFFICIAL-SENSITIVE  
**Audit**: UAL logs (Who, What, When, Where, Why, Result) with 7-year retention for OFFICIAL, 10 years for OFFICIAL-SENSITIVE  
**Log Integrity**: Immutable logging, SIEM integration (Sentinel)  
**Priority**: CRITICAL (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 19 (Audit Logging)

#### NFR-C-003: Public Records Act and National Archives
**Requirement**: Permanent records (policy papers, ministerial correspondence) retained 20 years, transferred to National Archives  
**Reports**: Monthly retention compliance, quarterly disposition review, annual FOI audit  
**Priority**: CRITICAL (NON-NEGOTIABLE)  
**Aligns with**: Architecture Principle 12 (Information Governance)

### Usability

#### NFR-U-001: User Experience and Intuitiveness
**Requirement**: Intuitive for medium proficiency users (policy advisors, administrators)  
**Standards**: Microsoft Fluent Design, responsive mobile design, browser support (Chrome, Edge, Firefox, Safari last 2 versions)  
**Onboarding**: Microsoft Learn modules, contextual help, quick reference guides  
**Priority**: HIGH

#### NFR-U-002: Accessibility (WCAG 2.2 Level AA)
**Requirement**: WCAG 2.2 AA compliance (legal requirement under Public Sector Accessibility Regulations 2018)  
**Features**: Keyboard navigation, screen reader compatibility (JAWS, NVDA), high contrast mode, adjustable fonts  
**Testing**: Pa11y, Axe DevTools (automated), manual keyboard/screen reader testing, user testing with disabled users  
**Priority**: CRITICAL (LEGAL REQUIREMENT)  
**Aligns with**: Architecture Principle 4 (Accessibility and Inclusion)

### Maintainability

#### NFR-M-001: Observability and Monitoring
**Requirement**: Comprehensive monitoring for service health, security incidents, compliance  
**Telemetry**: UAL (structured JSON to SIEM), Service Health metrics (uptime, latency), Power BI dashboards, M365 Admin Center alerts  
**Priority**: HIGH  
**Aligns with**: Architecture Principle 16 (Observability and Monitoring)

#### NFR-M-002: Documentation and Runbooks
**Requirement**: Comprehensive documentation for operations, administrators, end users  
**Types**: C4 architecture diagrams, admin guides, runbooks (incident response, migration, security incidents), user manuals, training materials  
**Format**: Markdown in SharePoint (version-controlled), accessible HTML (WCAG 2.2 AA), PDF exports  
**Currency**: Updated within 10 business days of configuration changes  
**Priority**: HIGH

#### NFR-M-003: Operational Runbooks
**Requirement**: Runbooks for common tasks and incident response  
**Coverage**: Migration procedures, rollback procedures, incident response (mailbox compromise, phishing, mail flow interruption), eDiscovery search, user support  
**Priority**: HIGH

### Interoperability

#### NFR-I-001: Open Standards for Email
**Requirement**: Support open standards (SMTP, IMAP optional, OAuth 2.0, Microsoft Graph API preferred)  
**Priority**: MEDIUM  
**Aligns with**: Architecture Principle 5 (Open Standards)

#### NFR-I-002: Cross-Government Integration
**Requirement**: Seamless integration with *.gov.uk email systems  
**Patterns**: SMTP with TLS to *.gov.uk domains, Exchange Federation for free/busy, Azure AD B2B guest access  
**SLA**: 99.9% delivery success to *.gov.uk, <1 minute latency  
**Priority**: HIGH  
**Aligns with**: Architecture Principle 13 (Collaboration and External Sharing)

#### NFR-I-003: Data Portability (Email Export)
**Requirement**: Export mailbox data to open formats (PST, EML, MSG)  
**Scope**: Complete mailbox export or filtered (date range, folder, keyword via eDiscovery)  
**Import**: PST import via M365 Import Service  
**Priority**: MEDIUM

---

## Integration Requirements

### INT-001: Azure Active Directory (Entra ID)
**Purpose**: Authenticate users with Azure AD credentials, enforce Conditional Access  
**Type**: Real-time API (OAuth 2.0, OpenID Connect)  
**Data Exchanged**: Authentication tokens (OAuth 2.0), user attributes (UPN, mailbox GUID, group memberships), Conditional Access policy decisions  
**Pattern**: OAuth 2.0 / OIDC authentication flow  
**Error Handling**: Cached credentials allow 8-hour offline access, auto token refresh every 1 hour  
**SLA**: <200ms token validation, 99.99% availability  
**Priority**: CRITICAL

### INT-002: Microsoft Intune (Mobile Device Management)
**Purpose**: Enforce device compliance for mobile email access  
**Type**: Real-time API (Microsoft Graph API, Conditional Access)  
**Data Exchanged**: Device compliance status (compliant, non-compliant), device attributes (OS version, jailbreak, encryption), Conditional Access decisions  
**Pattern**: Policy-based (Conditional Access queries Intune for compliance)  
**Error Handling**: Intune unavailable = fail-open (allow access temporarily, log alert)  
**SLA**: <1 second device compliance check, 99.9% availability  
**Priority**: HIGH

### INT-003: Microsoft Sentinel (SIEM)
**Purpose**: Ingest Exchange Online audit logs for threat detection and incident response  
**Type**: Event-driven (Azure Event Hub streaming from UAL to Sentinel)  
**Data Exchanged**: UAL events (MailItemsAccessed, Send, MailboxLogin, Set-Mailbox), DLP violations, Defender for Office 365 alerts  
**Pattern**: Pub/sub (Exchange publishes to Event Hub, Sentinel subscribes)  
**Error Handling**: Event Hub unavailable = buffer 24 hours in Exchange, replay when restored  
**SLA**: <5 min latency from event to Sentinel ingestion, 10,000 events/second throughput  
**Priority**: HIGH

---

## Data Requirements

### Data Entities

#### Entity 1: User Mailbox
**Attributes**: MailboxGuid (UUID, PK), UserPrincipalName (String, unique), DisplayName (String), MailboxType (Enum: UserMailbox, SharedMailbox, RoomMailbox), MailboxLocation (String: "United Kingdom"), MailboxQuota (Integer: 100GB), ItemCount (Integer), TotalItemSizeGB (Decimal), ArchiveGuid (UUID, nullable), LitigationHoldEnabled (Boolean), CreatedDateTime (Timestamp), LastModifiedDateTime (Timestamp)

**Relationships**: One-to-one with Azure AD User, One-to-many with MailboxPermissions, One-to-one with Archive Mailbox (optional)

**Data Volume**: Year 1: 3,500 mailboxes (52TB), Year 3: 4,550 mailboxes (100TB)

**Classification**: OFFICIAL (default), OFFICIAL-SENSITIVE (content may contain)

**Retention**: Active (while employed), Inactive (30 days post-offboarding unless legal hold), Archive (2-20 years per retention policy)

#### Entity 2: Email Message
**Attributes**: InternetMessageId (String, PK), Sender (String), Recipients (String), Subject (String, nullable), ReceivedDateTime (Timestamp), SensitivityLabel (Enum: OFFICIAL, OFFICIAL-SENSITIVE), HasAttachments (Boolean), MessageSize (Integer, max 150MB), IsEncrypted (Boolean), RetentionLabel (String: Transitory, Financial Record, Policy Paper, Permanent)

**Relationships**: Many-to-one with User Mailbox, One-to-many with EmailAttachments, One-to-one with AuditLogEntry

**Data Volume**: 175 million emails total (50,000 per user over 10 years), 175,000 emails/day ingestion

**Classification**: OFFICIAL or OFFICIAL-SENSITIVE (per SensitivityLabel)

**Retention**: 1-20 years depending on RetentionLabel

### Data Migration

**Scope**: 3,500 user mailboxes (52TB), 150 shared/resource mailboxes

**Strategy**: Hybrid migration (Exchange Hybrid coexistence), phased (Pilot Month 3, Phases 1-3 Months 5-9), incremental sync with final cutover

**Validation**: Item count (<1% variance acceptable), folder structure preserved, calendar 100% accurate, permissions preserved

**Rollback**: 30-day window (on-prem mailbox retained as disabled), rollback procedure documented

**Timeline**: Pilot 2 weeks (Month 3), Phase 1-3 each 4 weeks (Months 5-9)

---

## Constraints and Assumptions

### Technical Constraints
**TC-001**: Integrate with on-prem AD (Win Server 2016) via Azure AD Connect  
**TC-002**: Deploy in existing Azure UK regions (UK South, UK West)  
**TC-003**: Use existing M365 E5 licenses (3,500 procured)  
**TC-004**: 100 Mbps bandwidth (10 concurrent migrations at 10 Mbps each)  
**TC-005**: Coexist with on-prem Exchange 2016 for 6 months (hybrid)

### Business Constraints
**BC-001**: Go-live deadline Month 9 (April 2026) - non-negotiable (hardware end-of-support)  
**BC-002**: Budget cap £1.2M (actual £962.5K)  
**BC-003**: Pilot must include Finance directorate (validate financial system integrations)  
**BC-004**: Ministerial offices migrated last (Phase 3, weekend only)  
**BC-005**: Change freeze Q4 (Jan-Mar 2026) - Budget prep period

### Assumptions
**A-001**: Users have modern devices (Windows 10/11, macOS 11+, 8GB RAM)  
**A-002**: M365 meets 99.9% SLA (no prolonged Microsoft outages)  
**A-003**: Network latency Cabinet Office to UK South <20ms  
**A-004**: Users adapt to OWA/mobile within 1 month (with training)  
**A-005**: On-prem Exchange 2016 remains operational for 9 months

**Validation Plan**: A-001 (IT asset audit), A-002 (Service Health monitoring), A-003 (monthly latency tests), A-004 (user surveys), A-005 (daily Exchange health checks)

---

## Success Criteria and KPIs

### Business Metrics
| Metric | Baseline | Target | Timeline | Measurement |
|--------|----------|--------|----------|-------------|
| TCO Reduction | £2M/year | £1.2M/year (40% reduction) | Month 12 | Financial report |
| Availability | 98.5% | 99.9% | Monthly | M365 Service Health |
| User Satisfaction (NPS) | 45 | 70 | Month 3 post-migration | User survey |
| IT Operational Effort | 40 hrs/week | 15 hrs/week (60% reduction) | Month 6 | Time tracking |
| Mobile Adoption | 20% | 70% | Month 6 | M365 usage reports |

### Technical Metrics
| Metric | Target | Measurement |
|--------|--------|-------------|
| Migration Success Rate | 99% | Migration batch statistics |
| Email Latency (p95) | <30 seconds | Message Trace |
| Availability | 99.9% | Service Health dashboard |
| Security Incidents | 50% reduction | Defender threat analytics |
| Data Loss | Zero (100% item count match) | Post-migration validation |

### Adoption Metrics
| Metric | Target | Timeline | Measurement |
|--------|--------|----------|-------------|
| Training Completion | 100% | Before each wave | LMS completion reports |
| OWA Active Users | 30% (1,050 users) | Month 3 | M365 usage analytics |
| Mobile Active Users | 70% (2,450 users) | Month 6 | M365 usage analytics |
| Service Desk Tickets | Return to baseline (<100/week) | Month 1 | ServiceNow tracking |

---

## Dependencies and Risks

### Dependencies
| Dependency | Owner | Target | Status | Impact if Delayed |
|------------|-------|--------|--------|-------------------|
| Azure AD Connect | IT Infrastructure | Month 1 | On Track | HIGH (blocks migration) |
| M365 E5 Licenses | Procurement | Month 2 | On Track | HIGH (no licenses) |
| Exchange Hybrid Config | Exchange Admin | Month 2 | At Risk | HIGH (no hybrid connectivity) |
| Intune MDM Rollout | Intune Team | Month 3 | On Track | MEDIUM (no mobile access) |
| Sensitivity Labels Approval | InfoGov Team | Month 2 | At Risk | HIGH (data classification mandatory) |

### Risks
| Risk ID | Description | Prob | Impact | Mitigation | Owner |
|---------|-------------|------|--------|------------|-------|
| R-001 | Hybrid config fails (cert/federation issues) | MED | HIGH | Pre-migration lab testing, Microsoft Premier Support | Exchange Admin |
| R-002 | Bandwidth insufficient (100 Mbps shared) | LOW | MED | Schedule off-peak, throttle to 5 concurrent | Network Team |
| R-003 | User resistance to change | MED | HIGH | Champions network, exec sponsorship, feedback loops | Change Mgmt |
| R-004 | Large mailboxes (>50GB) fail weekend cutover | MED | MED | Pre-migration cleanup, split across weekends | Migration Team |
| R-005 | Third-party app integration fails (SMTP relay) | MED | HIGH | App inventory, integration testing pre-migration | App Support |
| R-006 | Data breach during migration | LOW | CRIT | TLS 1.3, Azure AD auth, audit logging | CISO |
| R-007 | M365 outage during exec migration | LOW | CRIT | Stagger exec migrations, rollback plan ready | PM |
| R-008 | DLP misconfiguration (OFFICIAL-SENSITIVE leak) | LOW | CRIT | DLP testing in pilot, quarterly audits, user training | Compliance |

---

## Timeline and Milestones

| Milestone | Description | Target Date | Dependencies |
|-----------|-------------|-------------|--------------|
| Requirements Approval | Stakeholder sign-off | Month 0 (Nov 2025) | This document |
| Architecture Review (Gate 2) | EA and SIRO review | Month 2 (Jan 2026) | Requirements |
| Pilot Migration Complete | 100 users (Finance) | Month 3 (Feb 2026) | Azure AD Connect, Hybrid, Licenses |
| Phase 1 Complete | 1,200 users | Month 5 (Apr 2026) | Pilot lessons learned |
| Phase 2 Complete | 1,200 users | Month 7 (Jun 2026) | Phase 1 |
| Phase 3 Complete | 1,000 users + execs | Month 9 (Aug 2026) | Phase 2 |
| Stabilization Period | 1 month monitoring | Month 10 (Sep 2026) | Phase 3 |
| On-Prem Decommission | Exchange 2016 powered off | Month 11 (Oct 2026) | Stabilization, 30-day rollback expired |
| Post-Implementation Review | Lessons learned | Month 12 (Nov 2026) | Decommission |

---

## Budget

### Cost Estimate
| Category | Cost | Notes |
|----------|------|-------|
| M365 E5 Licenses | £0 | Pre-existing (3,500 × £47/month = £1.97M annually) |
| Azure AD Connect Infrastructure | £25,000 | VM hosting, monitoring |
| Exchange Hybrid Config | £50,000 | Microsoft Premier Support (2 weeks) |
| Migration Services | £300,000 | BitTitan MigrationWiz, consulting |
| Training & Change Mgmt | £150,000 | eLearning, training delivery, Champions |
| Testing & Validation | £50,000 | Pilot testing, UAT, validation tools |
| Security & Compliance | £100,000 | Purview config, Defender tuning, CHECK test |
| Project Management | £200,000 | PM, BA, technical leads (6 months) |
| Contingency (10%) | £87,500 | Budget reserve |
| **Total** | **£962,500** | Within £1.2M cap |

### Ongoing Operational Costs
| Category | Annual Cost | Notes |
|----------|-------------|-------|
| M365 E5 Licenses | £1,970,000 | 3,500 × £47/month × 12 |
| Azure AD Connect Hosting | £12,000 | Azure VM (£1,000/month) |
| Microsoft Premier Support | £50,000 | Optional Year 1 |
| IT Operations (Exchange Admin) | £120,000 | 1.5 FTE (reduced from 4 FTE on-prem) |
| **Total** | **£2,152,000/year** | **£800K savings vs on-prem (£2.95M/year)** |

---

## Approval

### Requirements Review
| Reviewer | Role | Status | Date | Comments |
|----------|------|--------|------|----------|
| [CTO Name] | Executive Sponsor | [ ] Approved | [DATE] | |
| [Enterprise Architect] | Enterprise Architect | [ ] Approved | [DATE] | Verify Principles 1,3,6,11,12,19 alignment |
| [SIRO] | Senior Information Risk Owner | [ ] Approved | [DATE] | Verify OFFICIAL-SENSITIVE controls |
| [CISO] | Chief Information Security Officer | [ ] Approved | [DATE] | Verify NCSC Cloud Security Principles |
| [IAO] | Information Asset Owner | [ ] Approved | [DATE] | Verify sensitivity labels, DLP |
| [DPO] | Data Protection Officer | [ ] Approved | [DATE] | Verify GDPR, PIA completion |
| [Change Manager] | Change Manager | [ ] Approved | [DATE] | Verify migration timeline, rollback |
| [Finance Director] | Finance | [ ] Approved | [DATE] | Verify budget £962.5K within £1.2M cap |

---

## Appendices

### Appendix A: Glossary
- **Azure AD (Entra ID)**: Microsoft cloud identity service
- **BPSS**: Baseline Personnel Security Standard (UK gov vetting)
- **CHECK**: NCSC penetration testing scheme
- **DLP**: Data Loss Prevention
- **eDiscovery**: Electronic discovery (email search, legal hold)
- **Exchange Hybrid**: On-prem Exchange + Exchange Online coexistence
- **IAO**: Information Asset Owner (data classification owner)
- **Intune**: Microsoft MDM/MAM service
- **MFA**: Multi-Factor Authentication
- **NCSC**: National Cyber Security Centre
- **OFFICIAL**: UK Government Security Classification (routine business)
- **OFFICIAL-SENSITIVE**: OFFICIAL subset (enhanced controls)
- **OWA**: Outlook on the Web (browser email client)
- **PIM**: Privileged Identity Management (JIT admin access)
- **PST**: Personal Storage Table (Outlook mailbox export)
- **SIRO**: Senior Information Risk Owner (info risk accountable)
- **TLS**: Transport Layer Security (email encryption in transit)
- **UAL**: Unified Audit Log (M365 audit logging)

### Appendix B: Reference Documents
- Cabinet Office M365 Architecture Principles (.arckit/memory/architecture-principles.md)
- UK Government Technology Code of Practice (TCoP)
- GDS Service Standard (14 points)
- NCSC Cloud Security Principles
- Government Security Classifications Policy
- Public Records Act 1958 (National Archives retention)
- UK GDPR and Data Protection Act 2018
- WCAG 2.2 Guidelines (Level AA)

### Appendix C: Migration Phases
**Pilot (Month 3, 100 users)**: Finance directorate, IT volunteers, M365 Champions  
**Phase 1 (Month 5, 1,200 users)**: Corporate Services, Digital & Technology, Policy & Strategy  
**Phase 2 (Month 7, 1,200 users)**: Economic & Domestic Affairs, European & Global Affairs, Cabinet Secretariat  
**Phase 3 (Month 9, 1,000 users + execs)**: Propriety & Constitution, Executive team, Ministerial offices

### Appendix D: Conditional Access Policies
1. **Require MFA for All Users**: All cloud apps, no exclusions (except break-glass)
2. **Block Legacy Authentication**: Exchange Online, block POP3/IMAP/SMTP Basic Auth
3. **Require Compliant Device**: Exchange Online, require Intune compliance
4. **Block Non-UK Locations**: Exchange Online, block non-UK IPs (exclude travelers list)
5. **Session Controls for High-Risk**: Azure AD Identity Protection, high risk = password change + MFA

---

**Classification**: OFFICIAL

*This document contains sensitive Cabinet Office IT infrastructure information and should be handled per Government Security Classifications Policy.*

---

**Generated by**: ArcKit `/arckit.requirements` command
**Generated on**: 2025-10-17
**Last Updated**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Exchange Online Migration to Microsoft 365
**Model**: Claude
