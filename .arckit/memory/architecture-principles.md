# Cabinet Office Microsoft 365 Architecture Principles

**Document Type**: Architectural Governance
**Version**: 1.0
**Effective Date**: 2025-10-17
**Last Updated**: 2025-10-17
**Owner**: Enterprise Architecture Team, Cabinet Office
**Status**: DRAFT

---

## Executive Summary

This document establishes the immutable principles governing the Microsoft 365 deployment and all technology architecture decisions at the Cabinet Office. These principles ensure consistency, security, scalability, accessibility, and alignment with UK Government digital standards across all projects and initiatives.

**Scope**: All M365 workloads, integrations, and technology initiatives at Cabinet Office
**Authority**: Enterprise Architecture Review Board, Cabinet Office CTO
**Compliance**: Mandatory unless exception approved by CTO/CISO
**Regulatory Context**: UK Technology Code of Practice, GDS Service Standard, Government Security Classifications

---

## I. Strategic Principles

### 1. Cloud-First with UK Sovereignty

**Principle Statement**:
All new solutions MUST leverage cloud-native services following Microsoft Azure UK regions (UK South, UK West) to meet data sovereignty and UK Government Technology Code of Practice (TCoP) requirements.

**Rationale**:
Cloud platforms provide resilience, security, and cost efficiency while meeting Cabinet Office obligations under TCoP Point 3 (Use cloud first) and ensuring UK data sovereignty for OFFICIAL classified information.

**Implications**:
- All M365 data stored in UK Azure regions (UK South primary, UK West disaster recovery)
- Prefer Microsoft managed services (SharePoint Online, Teams, Exchange Online) over custom deployments
- Design for Azure Active Directory (now Entra ID) integration
- Leverage Microsoft 365 Defender, Purview, and compliance tools
- Multi-region resilience within UK geographic boundaries

**Approved Providers**:
- **Primary Cloud**: Microsoft Azure UK regions (UK South, UK West)
- **M365 Services**: Exchange Online, SharePoint Online, Teams, OneDrive for Business
- **Identity**: Azure AD (Entra ID) with Conditional Access
- **Prohibited**: Non-UK data residency, on-premises Exchange/SharePoint expansion

**Data Sovereignty Requirements**:
- OFFICIAL data: UK regions only
- OFFICIAL-SENSITIVE: UK regions with enhanced encryption
- Customer Lockbox enabled for Microsoft support access
- Data residency attestation documented

**Exceptions**:
- Legacy on-premises systems with documented migration roadmap (<24 months)
- Cross-government services requiring specific non-UK integrations (with SIRO approval)
- Edge devices requiring local caching (with encryption)

**Validation Gates**:
- [ ] All M365 workloads configured for UK data residency
- [ ] Infrastructure-as-Code defined (Terraform/Bicep)
- [ ] UK South/UK West multi-region strategy documented
- [ ] Cost model with FinOps tags defined
- [ ] Data sovereignty attestation signed

---

### 2. Government Digital Service (GDS) Standard Compliance

**Principle Statement**:
All digital services MUST meet the 14-point GDS Service Standard and Technology Code of Practice to ensure accessible, usable, and inclusive government services.

**Rationale**:
Cabinet Office sets the standard for UK Government digital services. Our M365 deployment must exemplify best practice in accessibility, user-centered design, and open standards.

**GDS Service Standard Key Points**:
1. **Understand users and their needs** (User research mandatory)
2. **Solve a whole problem for users** (End-to-end service design)
3. **Provide a joined-up experience across channels**
4. **Make the service simple to use** (WCAG 2.2 AA minimum)
5. **Make sure everyone can use the service** (Accessibility imperative)
6. **Have a multidisciplinary team**
7. **Use agile ways of working**
8. **Iterate and improve frequently**
9. **Create a secure service** (Cyber Essentials Plus minimum)
10. **Define success metrics** (KPIs tracked)
11. **Choose the right tools and technology**
12. **Make new source code open** (Open source by default)
13. **Use and contribute to open standards**
14. **Operate a reliable service** (Availability targets)

**Technology Code of Practice (TCoP) Alignment**:
- **TCoP 1**: Define user needs
- **TCoP 2**: Make things accessible and inclusive
- **TCoP 3**: Use cloud first
- **TCoP 4**: Make use of open standards
- **TCoP 5**: Use open source
- **TCoP 6**: Make things secure
- **TCoP 7**: Make privacy integral
- **TCoP 8**: Share and reuse technology
- **TCoP 9**: Integrate and adapt technology
- **TCoP 10**: Make better use of data

**Mandatory Requirements**:
- [ ] Service assessments at Alpha, Beta, Live phases
- [ ] User research with diverse user groups including those with disabilities
- [ ] WCAG 2.2 AA compliance (targeting AAA where possible)
- [ ] Accessibility statement published
- [ ] Performance metrics published on Performance Platform

**Exceptions**:
- NONE for public-facing services
- Internal-only tools require CTO waiver with compensating controls

**Validation Gates**:
- [ ] GDS Service Standard assessment completed
- [ ] Accessibility audit passed (WCAG 2.2 AA minimum)
- [ ] User research findings documented
- [ ] Service performance metrics defined

---

### 3. Security by Design (OFFICIAL Classification)

**Principle Statement**:
All architectures MUST implement UK Government Security Classification Policy with Zero Trust principles. Security is NON-NEGOTIABLE and appropriate to OFFICIAL data handling.

**Rationale**:
Cabinet Office handles OFFICIAL and OFFICIAL-SENSITIVE information requiring protective marking controls, secure-by-design architecture, and compliance with National Cyber Security Centre (NCSC) Cloud Security Principles.

**Government Security Classification Tiers**:
1. **OFFICIAL**: Majority of Cabinet Office information (default classification)
2. **OFFICIAL-SENSITIVE**: Subset requiring enhanced handling (Cabinet papers, policy development)
3. **SECRET**: Not handled in M365 environment (separate accreditation required)

**NCSC Cloud Security Principles Compliance**:
All 14 NCSC Cloud Security Principles MUST be addressed:
1. Data in transit protection (TLS 1.3+)
2. Asset protection and resilience (UK region redundancy)
3. Separation between users (tenant isolation, sensitivity labels)
4. Governance framework (SIRO, IAO appointed)
5. Operational security (patching, monitoring)
6. Personnel security (Baseline Personnel Security Standard - BPSS minimum)
7. Secure development (DevSecOps)
8. Supply chain security (Microsoft supply chain assurance)
9. Secure user management (MFA mandatory)
10. Identity and authentication (Azure AD with Conditional Access)
11. External interface protection (DLP, Conditional Access)
12. Secure service administration (Privileged Identity Management)
13. Audit information for users (M365 audit logs, 7-year retention)
14. Secure use of the service (end-user security awareness)

**Zero Trust Pillars for M365**:
1. **Verify explicitly**: Every access request fully authenticated and authorized
2. **Least privilege access**: Just-in-time, just-enough-access (JIT/JEA)
3. **Assume breach**: Minimize blast radius, segment access, verify end-to-end encryption

**Mandatory Security Controls**:
- [ ] Multi-factor authentication (MFA) mandatory for all users (no exceptions)
- [ ] Conditional Access policies enforcing device compliance
- [ ] Microsoft Purview Information Protection with sensitivity labels (OFFICIAL, OFFICIAL-SENSITIVE)
- [ ] Data Loss Prevention (DLP) policies preventing unauthorized sharing
- [ ] Microsoft Defender for Office 365 (Plan 2) for threat protection
- [ ] Encryption at rest (Microsoft-managed keys minimum, customer-managed optional for OFFICIAL-SENSITIVE)
- [ ] Encryption in transit (TLS 1.3+ mandatory)
- [ ] Privileged Identity Management (PIM) for admin roles
- [ ] Azure AD Identity Protection for risk-based policies
- [ ] Microsoft Sentinel or SIEM integration for security monitoring
- [ ] Audit logging with 7-year retention (OFFICIAL requirement)
- [ ] Regular penetration testing and CHECK-certified assessments

**Personnel Security**:
- BPSS clearance minimum for all users
- SC clearance for administrators and OFFICIAL-SENSITIVE handlers
- Security awareness training mandatory (annual refresh)

**Compliance Frameworks**:
- Cyber Essentials Plus (minimum)
- NCSC Cloud Security Principles
- ISO 27001 / Government Security Classifications Policy
- HMG Security Policy Framework
- GDPR (UK GDPR)

**Exceptions**:
- NONE. Security principles are non-negotiable.
- Specific control alternatives require SIRO/IAO approval with documented compensating controls

**Validation Gates**:
- [ ] Threat model completed using NCSC guidance
- [ ] Security controls mapped to NCSC Cloud Security Principles
- [ ] SIRO sign-off obtained
- [ ] Penetration test / CHECK assessment completed
- [ ] Incident response playbook aligned with NCSC Cyber Incident Response guidance

---

### 4. Accessibility and Inclusion (WCAG 2.2 AA Minimum)

**Principle Statement**:
All digital services and content MUST meet WCAG 2.2 Level AA standards as required by the Public Sector Bodies (Websites and Mobile Applications) Accessibility Regulations 2018.

**Rationale**:
Cabinet Office has a legal and moral obligation to ensure government services are accessible to all citizens, including the 1 in 5 UK adults with disabilities. This is non-negotiable under UK law.

**Accessibility Requirements**:
- **WCAG 2.2 AA**: Mandatory minimum (targeting AAA where feasible)
- **Perceivable**: Alt text, captions, transcripts, sufficient color contrast (4.5:1 minimum)
- **Operable**: Keyboard navigation, no keyboard traps, sufficient time limits
- **Understandable**: Plain English (reading age 9 per GDS guidelines), consistent navigation
- **Robust**: Compatible with assistive technologies (JAWS, NVDA, ZoomText)

**M365 Accessibility Features** (MUST be enabled):
- Accessibility Checker in Office apps
- Immersive Reader in SharePoint and Teams
- Live captions in Teams meetings
- Screen reader compatibility
- Keyboard shortcuts documented
- High contrast mode support

**Content Accessibility**:
- All documents (Word, Excel, PowerPoint) MUST pass Accessibility Checker before publishing
- PDF/A format for archival documents with tagged structure
- Video content MUST have captions and transcripts
- Forms MUST be screen reader accessible
- Colour MUST NOT be the only means of conveying information

**Testing Requirements**:
- Automated testing with Pa11y, Axe, or WAVE
- Manual testing with keyboard navigation
- Screen reader testing (NVDA/JAWS)
- User testing with people with disabilities
- Annual accessibility audit by certified auditor

**Public Sector Accessibility Statement**:
- Accessibility statement published and maintained
- Contact details for accessibility issues
- Enforcement procedure documented
- Compliance status declared

**Exceptions**:
- NONE for public-facing services or citizen interactions
- Internal tools require documented justification and remediation plan (<6 months)

**Validation Gates**:
- [ ] WCAG 2.2 AA compliance verified (automated + manual testing)
- [ ] Accessibility statement published
- [ ] Screen reader testing completed
- [ ] User testing with disabled users conducted
- [ ] Accessibility Checker compliance for all templates

---

### 5. Open Standards and Interoperability

**Principle Statement**:
All systems MUST use open standards for data formats, APIs, and protocols to ensure interoperability, avoid vendor lock-in, and enable cross-government collaboration.

**Rationale**:
TCoP Point 4 requires open standards to ensure long-term sustainability, user choice, and cross-government integration. Cabinet Office must lead by example.

**Compulsory Open Standards** (per Open Standards Board):
- **Document formats**: ODF 1.2 (Open Document Format) for editable documents
- **Email**: SMTP, IMAP (not proprietary connectors)
- **Calendar**: iCalendar (RFC 5545)
- **Contacts**: vCard (RFC 6350)
- **Web browsing**: HTML5, CSS3
- **APIs**: RESTful APIs with OpenAPI 3.0+ specifications
- **Authentication**: OAuth 2.0, OpenID Connect (OIDC), SAML 2.0

**M365 Open Standards Compliance**:
- SharePoint: Support ODF export/import alongside Office formats
- Exchange Online: Standards-compliant email (SMTP/IMAP/POP3)
- Teams: Standards-based calling (SIP/RTP where possible)
- Microsoft Graph API: OpenAPI documented endpoints

**Data Portability**:
- Users can export data in open formats
- No proprietary lock-in for citizen data
- Migration paths to alternative solutions documented

**Cross-Government Integration**:
- GOV.UK Verify / One Login integration
- Government Digital Identity (GDI) alignment
- Cross-government APIs follow GDS API standards
- Shared platforms (e.g., GOV.UK Notify, GOV.UK Pay) prioritized

**Exceptions**:
- Specialized functionality where no open standard exists (document with rationale)
- Legacy integrations during migration period (max 18 months with roadmap)

**Validation Gates**:
- [ ] Open standards compliance verified
- [ ] Data export capability in open formats tested
- [ ] API specifications published (OpenAPI 3.0+)
- [ ] Cross-government interoperability tested where applicable

---

## II. Data Principles

### 6. Data Sovereignty and Classification

**Principle Statement**:
All data MUST be classified according to Government Security Classifications and stored in UK regions with appropriate protective marking controls.

**Rationale**:
Cabinet Office handles sensitive government information requiring clear classification, UK data residency, and controls aligned with Government Security Policy Framework.

**Data Classification and Handling**:

| Classification | Description | M365 Sensitivity Label | Storage Location | Encryption | Sharing Restrictions |
|----------------|-------------|------------------------|------------------|------------|---------------------|
| **OFFICIAL** | Routine public sector business | OFFICIAL | UK regions | TLS 1.3 + AES-256 at rest | Within HMG with need-to-know |
| **OFFICIAL-SENSITIVE** | Damaging if lost/stolen (policy, personnel) | OFFICIAL-SENSITIVE | UK regions | Customer-managed keys | Restricted distribution |
| **SECRET** | Serious damage to national interests | N/A - Not in M365 | Accredited SECRET system | N/A | N/A |

**M365 Information Protection Configuration**:
- Microsoft Purview sensitivity labels matching GSC tiers
- Automatic labeling based on content inspection (keywords, regex)
- Labels embedded in document metadata (persistent protection)
- Visual markings (header/footer) applied automatically
- Encryption applied to OFFICIAL-SENSITIVE content

**Data Residency Requirements**:
- **OFFICIAL**: UK South (primary), UK West (DR)
- **OFFICIAL-SENSITIVE**: UK South (primary), UK West (DR), customer-managed keys
- **Multi-Geo**: NOT enabled (all data remains in UK)
- **Data Location Validation**: Monthly attestation reports

**Data Loss Prevention (DLP)**:
- Block external sharing of OFFICIAL-SENSITIVE content
- Detect and protect sensitive information types (NI numbers, passport numbers, policy document patterns)
- Prevent upload to personal cloud services
- Alert on bulk downloads exceeding thresholds
- Endpoint DLP for devices accessing M365

**GDPR and UK Data Protection Act 2018**:
- Privacy Impact Assessment (PIA) for personal data processing
- Data Protection Officer (DPO) consulted
- Data subject rights (access, rectification, erasure) procedures
- Lawful basis for processing documented
- Retention schedules aligned with National Archives guidance

**Retention and Disposal**:
- Retention labels applied based on document type
- Automatic deletion after retention period (Public Records Act compliance)
- Legal hold for FOI requests and litigation
- Secure disposal with audit trail

**Exceptions**:
- Cross-border data transfers require SIRO approval with Standard Contractual Clauses (SCCs)
- Anonymized/pseudonymized data for analytics (with DPO approval)

**Validation Gates**:
- [ ] All content labeled with sensitivity classification
- [ ] UK data residency validated
- [ ] DLP policies configured and tested
- [ ] Retention schedules applied
- [ ] GDPR compliance documented

---

### 7. Data Quality and Lifecycle Management

**Principle Statement**:
Data MUST be accurate, complete, and managed through defined lifecycle stages with documented lineage and quality controls.

**Rationale**:
Poor data quality undermines policy decisions and service delivery. Cabinet Office requires high-quality data with clear ownership and lifecycle management.

**Data Quality Standards**:
- **Accuracy**: Validated at point of entry, regular quality checks
- **Completeness**: Required fields enforced
- **Consistency**: Standardized formats (dates, addresses)
- **Timeliness**: Freshness indicators, version control
- **Validity**: Business rule validation

**Data Lifecycle Stages**:
1. **Creation/Capture**: Classification at source, quality validation
2. **Active Use**: Accessible to authorized users, version controlled
3. **Review**: Periodic review of accuracy and relevance
4. **Archive**: Moved to long-term storage (Azure Archive Storage)
5. **Disposal**: Secure deletion after retention period

**Microsoft Purview Data Catalog**:
- Data assets registered and documented
- Data owners and stewards assigned
- Lineage tracking for reports and analytics
- Glossary terms for consistent terminology

**SharePoint and OneDrive Governance**:
- Site lifecycle management (creation, review, archival, deletion)
- Unused sites automatically archived after 12 months inactivity
- Orphaned content identified and reassigned
- External sharing monitored and reported

**Validation Gates**:
- [ ] Data owners assigned for key datasets
- [ ] Quality rules defined and enforced
- [ ] Lifecycle policies configured
- [ ] Purview Data Catalog populated

---

### 8. Privacy by Design

**Principle Statement**:
Privacy MUST be embedded into system design from the outset, with Privacy Impact Assessments (PIAs) for all personal data processing.

**Rationale**:
TCoP Point 7 (Make privacy integral) and UK GDPR require proactive privacy protection, not reactive compliance.

**Privacy Principles (ICO Guidelines)**:
1. **Lawfulness, fairness, transparency**: Clear lawful basis, privacy notices
2. **Purpose limitation**: Process only for specified purposes
3. **Data minimization**: Collect only necessary data
4. **Accuracy**: Keep personal data accurate and up-to-date
5. **Storage limitation**: Retain only as long as necessary
6. **Integrity and confidentiality**: Appropriate security measures
7. **Accountability**: Demonstrate compliance

**Privacy Impact Assessment (PIA) Triggers**:
- New processing of personal data
- Significant change to existing processing
- Large-scale processing of special category data
- Systematic monitoring (e.g., audit logging)
- Automated decision-making

**M365 Privacy Controls**:
- Subject Access Request (SAR) tooling (eDiscovery, Content Search)
- Right to erasure workflows
- Consent management (where consent is lawful basis)
- Data breach detection and notification (<72 hours to ICO)
- Privacy notices embedded in services

**Third-Party Processors**:
- Data Processing Agreements (DPAs) with Microsoft
- Sub-processor transparency (Microsoft Trust Center)
- International transfers safeguarded (SCCs, adequacy decisions)

**Validation Gates**:
- [ ] PIA completed and DPO approved
- [ ] Lawful basis documented
- [ ] Privacy notice published
- [ ] SAR procedures tested
- [ ] Data breach response plan in place

---

## III. Technology Standards

### 9. Approved M365 Technology Stack

**Principle Statement**:
M365 solutions MUST leverage approved Microsoft and partner technologies to ensure supportability, security, and license compliance.

**Core M365 Services** (Approved):
- **Collaboration**: Microsoft Teams, SharePoint Online, OneDrive for Business
- **Communication**: Exchange Online, Outlook, Yammer
- **Productivity**: Microsoft 365 Apps (Word, Excel, PowerPoint, OneNote)
- **Security & Compliance**: Microsoft Purview, Defender for Office 365, Azure AD (Entra ID)
- **Workflow**: Power Automate (formerly Flow)
- **Forms**: Microsoft Forms
- **Planning**: Microsoft Planner, Microsoft To Do, Microsoft Lists

**Power Platform** (Approved with Governance):
- **Power Apps**: Canvas and Model-driven apps (DLP policies enforced)
- **Power Automate**: Workflows and RPA (premium connectors require approval)
- **Power BI**: Analytics and reporting (gateway for on-prem data)
- **Power Virtual Agents**: Chatbots (limited to internal use without additional assessment)

**Power Platform Governance Requirements**:
- Data Loss Prevention (DLP) policies block non-business connectors
- Environment strategy (production, development, personal productivity)
- Maker governance (approval workflow for production deployments)
- CoE Starter Kit deployed for monitoring and compliance
- Premium connector usage tracked and justified

**Development and Integration**:
- **APIs**: Microsoft Graph API (preferred), REST APIs with OAuth 2.0
- **Custom Development**: SharePoint Framework (SPFx), Teams apps
- **Languages**: TypeScript (preferred), JavaScript, PowerShell, C#
- **Authentication**: Azure AD OAuth 2.0 / OpenID Connect (OIDC)

**Third-Party Integrations** (Require Assessment):
- Pre-approved: GOV.UK services (Notify, Pay, PaaS)
- Security assessment required for new SaaS integrations
- Azure AD app registration for all integrated apps
- Conditional Access policies applied to third-party apps

**Prohibited Technologies**:
- Consumer OneDrive (personal accounts)
- Non-UK M365 tenants
- Unapproved file sharing services (Dropbox, Google Drive)
- Shadow IT tools bypassing IT procurement

**Exceptions**:
- Proof-of-concept in isolated environment (time-boxed, 90 days max)
- Specialized use cases with CTO approval
- Legacy tools during migration period (documented sunset date)

**Validation Gates**:
- [ ] All solutions use approved M365 services
- [ ] Power Platform DLP policies enforced
- [ ] Third-party integrations security assessed
- [ ] Licensing compliance verified

---

### 10. Infrastructure as Code and DevOps

**Principle Statement**:
ALL M365 configuration and infrastructure MUST be defined as code, version-controlled, and deployed via CI/CD pipelines. Manual configuration changes are prohibited in production.

**Rationale**:
Infrastructure-as-Code ensures repeatability, auditability, change control, and disaster recovery capability. Manual changes introduce drift and risk.

**IaC Standards for M365**:
- **Primary Tools**: Microsoft365DSC (Desired State Configuration), Terraform with AzureRM provider
- **Version Control**: Git (GitHub.com with private repos, or Azure DevOps)
- **Configuration Baseline**: M365DSC export of current tenant configuration
- **Change Management**: All changes via pull request with mandatory review

**M365 Configuration as Code**:
- Azure AD (Entra ID): Conditional Access policies, groups, users
- SharePoint Online: Site collections, hub sites, sharing policies
- Exchange Online: Mail flow rules, retention policies, mailbox settings
- Microsoft Teams: Team templates, policies, settings
- Purview: Sensitivity labels, retention labels, DLP policies
- Defender: Security policies, threat policies

**CI/CD Pipeline Stages**:
1. **Development**: Test tenant for validation
2. **Code Review**: Peer review of configuration changes
3. **Automated Testing**: M365DSC Test to validate drift detection
4. **Approval Gate**: CAB (Change Advisory Board) approval for production changes
5. **Production Deployment**: M365DSC Apply with audit logging
6. **Validation**: Post-deployment drift detection
7. **Rollback**: Revert to previous configuration version if issues detected

**Change Control**:
- Normal changes: 5-day CAB review
- Standard changes: Pre-approved templates
- Emergency changes: CTO/CISO approval with 24-hour retrospective documentation

**Drift Detection**:
- Daily M365DSC drift monitoring
- Automated alerts on unauthorized manual changes
- Quarterly compliance reports

**Disaster Recovery**:
- M365 configuration backed up daily via M365DSC export
- Recovery procedures tested quarterly
- Configuration history retained for 7 years

**Exceptions**:
- Emergency security hotfixes (with 24-hour IaC update requirement)
- User-driven configuration (e.g., Teams channel creation) within governed boundaries

**Validation Gates**:
- [ ] M365 configuration exported to M365DSC
- [ ] CI/CD pipeline configured with approval gates
- [ ] Drift detection automated
- [ ] Disaster recovery procedures tested
- [ ] Change management integrated with ServiceNow/Jira

---

## IV. Architecture Patterns

### 11. Identity and Access Management (Zero Trust)

**Principle Statement**:
All access MUST be identity-based using Azure AD with Conditional Access policies enforcing device compliance, location, and risk-based controls. Network location is NOT a proxy for trust.

**Rationale**:
Zero Trust assumes breach and verifies every access request explicitly. Traditional perimeter security is insufficient for cloud-first, mobile-enabled government.

**Azure AD (Entra ID) Architecture**:
- **Single tenant**: Cabinet Office production tenant (no multi-tenancy)
- **Hybrid identity**: Azure AD Connect for on-prem AD sync (if applicable)
- **Identity Protection**: Risk-based policies for sign-in and user risk
- **Privileged Identity Management (PIM)**: Just-in-time admin access
- **Multi-factor authentication (MFA)**: Enforced for all users via Conditional Access

**Conditional Access Policies** (Mandatory):
1. **Require MFA for all users**: No exceptions
2. **Block legacy authentication**: Modern auth only (OAuth 2.0)
3. **Require compliant device**: Intune-managed devices only for OFFICIAL-SENSITIVE
4. **Block access from unapproved locations**: Geofencing to UK + approved countries
5. **Require approved client apps**: Microsoft apps or approved third-party apps
6. **Session controls for high-risk users**: Require password change, limited session duration

**MFA Methods** (Approved):
- **Preferred**: Microsoft Authenticator (passwordless), FIDO2 security keys
- **Allowed**: SMS/Phone (for users without smartphones - time-limited)
- **Prohibited**: Voice call only (vulnerable to social engineering)

**Passwordless Authentication**:
- Roadmap to eliminate passwords for all users (18-month target)
- Windows Hello for Business for device sign-in
- Microsoft Authenticator for mobile access
- FIDO2 keys for high-privilege accounts

**Privileged Access Management**:
- Global Admin role: Maximum 5 accounts, PIM activated only
- Break-glass accounts: 2 accounts, stored in secure vault, no MFA (for AAD outage)
- Admin roles: Least privilege assignment, PIM approval workflows
- Admin workstations: Privileged Access Workstations (PAWs) or secure admin workstation

**Device Management (Intune)**:
- All devices accessing M365 must be Intune-managed OR Hybrid Azure AD joined
- Device compliance policies: Encryption, firewall, antivirus, OS version
- Conditional Access enforces device compliance
- Mobile Application Management (MAM) for BYOD scenarios (where approved)

**Guest Access Governance**:
- External collaboration enabled with restrictions
- Guest invitations require sponsor approval
- Guests subject to same Conditional Access policies
- Guest access reviews quarterly (Azure AD Access Reviews)
- Time-limited guest accounts (max 12 months, renewal required)

**Validation Gates**:
- [ ] Conditional Access policies configured and tested
- [ ] MFA enrollment for 100% of users
- [ ] PIM configured for admin roles
- [ ] Device compliance policies enforced
- [ ] Guest access review process operational

---

### 12. Information Governance and Records Management

**Principle Statement**:
All M365 content MUST be governed by retention policies, sensitivity labels, and disposition schedules aligned with National Archives guidance and Public Records Act requirements.

**Rationale**:
Cabinet Office has legal obligations under the Public Records Act 1958 and must ensure records are retained, accessible, and disposed of appropriately.

**Records Management Framework**:
- **Records Authority**: National Archives guidance on retention schedules
- **Retention Schedule**: Aligned with Cabinet Office retention and disposal schedule
- **File Plan**: Document types mapped to retention periods
- **Records Manager**: Appointed role with governance responsibility

**Microsoft Purview Records Management**:
- **Retention labels**: Applied manually or automatically based on rules
- **Retention policies**: Apply retention to all content in scope
- **Disposition reviews**: Workflow for records reaching end of retention
- **Regulatory records**: Locked records preventing deletion
- **Event-based retention**: Triggers (e.g., contract expiry, project closure)

**Common Retention Periods** (Cabinet Office):
- **Policy papers**: Permanent (transfer to National Archives after 20 years)
- **Ministerial correspondence**: Permanent
- **Financial records**: 7 years (post-transaction)
- **HR records**: 6 years (post-employment)
- **Transitory information**: Delete after 1 year or when no longer needed
- **OFFICIAL emails**: 2 years (unless related to above categories)

**Sensitivity Labels and Retention Integration**:
- Sensitivity labels can auto-apply retention labels
- OFFICIAL-SENSITIVE content: Minimum 7-year retention
- Public Records Act: Transfer to National Archives at 20 years (policy papers)

**eDiscovery and Legal Hold**:
- eDiscovery cases for FOI requests, legal proceedings
- Legal hold overrides retention policies
- Content Search across Exchange, SharePoint, OneDrive, Teams
- Export to PST/PDF for disclosure

**Freedom of Information (FOI) Compliance**:
- Content searchable for FOI requests
- Response SLA: 20 working days
- Exemptions documented and justified
- Disclosure log maintained

**Validation Gates**:
- [ ] Retention labels published and auto-applied
- [ ] Retention policies cover all M365 workloads
- [ ] Disposition review workflow tested
- [ ] eDiscovery permissions assigned
- [ ] FOI response procedures documented

---

### 13. Collaboration and External Sharing Governance

**Principle Statement**:
External collaboration is permitted with appropriate controls to prevent unauthorized data disclosure while enabling cross-government and partner collaboration.

**Rationale**:
Cabinet Office must collaborate with other government departments, agencies, and trusted partners while protecting OFFICIAL information.

**Sharing Principles**:
- **Default to closed**: Sharing disabled unless explicitly enabled
- **Need-to-know**: Share only with authorized recipients
- **Least privilege**: Grant minimum necessary permissions
- **Auditability**: All sharing logged and reviewable

**SharePoint and OneDrive Sharing Policies**:
- **Internal-only**: Default for all new sites
- **External sharing**: Enabled only for approved sites (whitelisted domains)
- **Anonymous links**: Disabled (authenticated sharing only)
- **Expiration**: External links expire after 90 days
- **Permissions**: View-only preferred, edit with justification

**Approved External Domains** (Allowlist):
- *.gov.uk (all UK Government departments)
- *.nhs.uk (NHS organizations)
- *.mod.uk (Ministry of Defence)
- *.police.uk (Police forces)
- Specific partner organizations (Cabinet Office approved list)

**Microsoft Teams External Access**:
- **External access (federation)**: Enabled for gov.uk domains only
- **Guest access**: Enabled with approval workflow
- **Private channels**: Restricted to internal members only
- **Channel email**: Disabled (prevents uncontrolled email-to-Teams ingestion)

**OneDrive for Business**:
- Personal use permitted for work documents only
- Syncing OFFICIAL-SENSITIVE requires encrypted device
- External sharing disabled by default
- Storage quota: 1TB per user (reviewable)

**Teams Meetings with External Participants**:
- Lobby enabled (guests admitted by organizer)
- Recording requires notification and consent
- Meeting recordings auto-deleted after 60 days (unless retained)
- Transcripts reviewed for sensitive information before sharing

**Monitoring and Compliance**:
- Monthly reports on external sharing activity
- Quarterly access reviews for external guest accounts
- Alerts on unusual sharing patterns (e.g., bulk downloads by guests)
- DLP policies block sharing of OFFICIAL-SENSITIVE externally

**Validation Gates**:
- [ ] Sharing policies configured per classification
- [ ] Allowlist of external domains enforced
- [ ] Guest access review workflow operational
- [ ] External sharing audit reports generated monthly

---

## V. Development and Customization

### 14. SharePoint Framework (SPFx) and Custom Development

**Principle Statement**:
Custom M365 development MUST use approved frameworks (SharePoint Framework, Teams apps) with security reviews and code quality standards.

**Rationale**:
Custom code introduces security and supportability risks. Standardized frameworks with governance ensure secure, maintainable solutions.

**Approved Development Frameworks**:
- **SharePoint Online**: SharePoint Framework (SPFx) web parts, extensions
- **Microsoft Teams**: Teams apps (tabs, bots, messaging extensions)
- **Power Platform**: Power Apps, Power Automate (with governance)
- **Microsoft Graph**: APIs for data access
- **Azure Functions**: Serverless backend for integrations

**SPFx Development Standards**:
- TypeScript (not JavaScript) for type safety
- React (preferred framework)
- SPFx version: Latest GA version within 6 months of release
- Yeoman generator for project scaffolding
- npm packages: Only approved, security-scanned packages

**Security Requirements for Custom Code**:
- **Code review**: Peer review mandatory before deployment
- **Static analysis**: SonarQube, ESLint, TypeScript compiler strict mode
- **Dependency scanning**: npm audit, Dependabot alerts
- **No secrets in code**: Use Azure Key Vault for API keys
- **Authentication**: Azure AD OAuth 2.0 (no basic auth)
- **API permissions**: Least privilege Graph API permissions

**Teams App Development**:
- Teams Toolkit for Visual Studio Code
- App manifest validated against schema
- App submission to internal App Catalog (not public store)
- Permissions reviewed by security team
- Bots hosted in Azure Bot Service (UK region)

**Power Platform Development**:
- Solution-aware development (not unmanaged customizations)
- ALM (Application Lifecycle Management) with environments (dev, test, prod)
- Connectors: Only approved connectors (DLP enforced)
- Code components (PCF): Reviewed and approved
- Power Apps security roles: Least privilege

**Testing Requirements**:
- Unit tests: Jest for SPFx, PAC CLI for Power Apps
- Integration tests: Test tenant validation
- User acceptance testing: Business user sign-off
- Accessibility testing: Pa11y, Axe for WCAG compliance
- Performance testing: Load testing for high-traffic solutions

**Deployment Process**:
- Development: Test tenant
- User Acceptance Testing (UAT): Pre-production tenant
- Production: Scheduled deployment with rollback plan
- Monitoring: Application Insights telemetry

**Validation Gates**:
- [ ] Code review completed and approved
- [ ] Security scan passed (no high/critical vulnerabilities)
- [ ] Accessibility testing passed (WCAG 2.2 AA)
- [ ] CAB approval for production deployment
- [ ] Rollback procedure documented

---

### 15. Power Platform Governance and Center of Excellence

**Principle Statement**:
Power Platform solutions MUST be governed through a Center of Excellence with DLP policies, environment strategy, and maker governance to prevent shadow IT while enabling citizen development.

**Rationale**:
Power Platform democratizes development but requires governance to prevent data leakage, licensing violations, and unsupportable solutions.

**Power Platform Center of Excellence (CoE)**:
- **CoE Starter Kit**: Deployed for monitoring and governance
- **CoE Team**: Power Platform admins, business analysts, governance lead
- **Maker Community**: Internal community of practice, training, best practices
- **App Review Board**: Governance board for production app approvals

**Environment Strategy**:
1. **Default environment**: Disabled (prevent ungoverned development)
2. **Personal productivity environments**: Auto-created for makers (isolated, DLP enforced)
3. **Development environments**: Requested via service catalog
4. **Test/UAT environments**: Managed environments for testing
5. **Production environments**: Restricted, requires approval

**Data Loss Prevention (DLP) Policies**:
- **Business data only**: Microsoft connectors (SharePoint, Outlook, Teams)
- **Non-business data**: Blocked (Twitter, personal email, Dropbox)
- **Approved connectors**: Specific connectors with security review (HTTP, SQL Server with governance)

**Maker Governance**:
- Maker registration: Makers identify themselves, agree to governance
- App quarantine: Apps in default environment auto-quarantined
- App assessment: Pre-production checklist (security, accessibility, licensing)
- App retirement: Unused apps archived after 6 months

**Licensing Governance**:
- Per-app plans for production apps (not per-user unless justified)
- Premium connector usage tracked and optimized
- Power Automate RPA: Unattended licenses audited quarterly

**CoE Dashboard**:
- App and flow inventory
- Connector usage analytics
- Orphaned resources (creator left organization)
- Compliance status

**Validation Gates**:
- [ ] CoE Starter Kit deployed
- [ ] DLP policies enforced on all environments
- [ ] App review process operational
- [ ] Maker training program established

---

## VI. Operational Excellence

### 16. Observability, Monitoring, and Incident Response

**Principle Statement**:
M365 services MUST be monitored for availability, performance, security threats, and compliance with SLAs. Incidents MUST be responded to using NCSC Cyber Incident Response guidance.

**Rationale**:
Proactive monitoring enables rapid detection and response to service degradation, security incidents, and compliance violations.

**M365 Monitoring Tools**:
- **Microsoft 365 Admin Center**: Service health dashboard, message center
- **Microsoft 365 Defender**: Security incidents, threat analytics
- **Microsoft Purview Compliance**: Compliance score, alerts
- **Azure AD (Entra ID) Monitoring**: Sign-in logs, audit logs, risky users
- **Microsoft Sentinel**: SIEM for advanced threat detection (if deployed)
- **Power BI**: Custom dashboards for usage analytics

**Key Metrics and SLIs**:
- **Availability**: Service uptime (Exchange, SharePoint, Teams)
- **Performance**: Response time, latency
- **Security**: Sign-in failures, MFA denials, DLP policy violations
- **Compliance**: Unlabeled documents, retention policy gaps
- **Adoption**: Active users, Teams usage, SharePoint collaboration

**Alerting and Notifications**:
- **Critical alerts**: Service outage, security breach, DLP violations
- **Warning alerts**: Capacity thresholds, guest account expiry
- **Informational**: Planned maintenance, new features
- **Escalation**: On-call rotation, PagerDuty/ServiceNow integration

**Service Level Agreements (SLAs)**:
- **Microsoft SLA**: 99.9% uptime for M365 services
- **Internal SLA (Cabinet Office)**: Response and resolution times
  - P1 (Critical): 1-hour response, 4-hour resolution target
  - P2 (High): 4-hour response, 24-hour resolution target
  - P3 (Medium): 1 business day response, 5 business days resolution
  - P4 (Low): 2 business days response, 10 business days resolution

**Incident Response Process** (NCSC Aligned):
1. **Detection**: Alert triggered or user report
2. **Triage**: Severity assessment, initial containment
3. **Investigation**: Root cause analysis, scope determination
4. **Containment**: Isolate affected systems, prevent spread
5. **Eradication**: Remove threat, patch vulnerabilities
6. **Recovery**: Restore services, validate functionality
7. **Post-Incident Review**: Lessons learned, remediation actions

**Security Incident Categories**:
- **Account compromise**: Credentials stolen, unauthorized access
- **Malware/Phishing**: Malicious attachments, phishing emails
- **Data breach**: Unauthorized disclosure of OFFICIAL data
- **Insider threat**: Malicious or negligent insider actions
- **Denial of service**: Service unavailable due to attack or misconfiguration

**Regulatory Reporting**:
- **Data breaches**: Report to ICO within 72 hours (GDPR requirement)
- **Serious incidents**: Report to SIRO, CTO, DPO within 24 hours
- **NCSC**: Report significant cyber incidents to NCSC via Cyber Incident Response service

**Disaster Recovery and Business Continuity**:
- **Microsoft BC/DR**: Microsoft's multi-region resilience
- **Cabinet Office BC/DR**: Failover procedures, alternate work modes
- **Recovery Time Objective (RTO)**: 4 hours for critical services
- **Recovery Point Objective (RPO)**: 1 hour (maximum acceptable data loss)
- **Testing**: Annual DR exercise, tabletop exercises quarterly

**Validation Gates**:
- [ ] Monitoring dashboards configured
- [ ] Alerting rules defined with on-call rotation
- [ ] Incident response playbooks documented
- [ ] SLA tracking automated
- [ ] DR procedures tested annually

---

### 17. User Adoption and Change Management

**Principle Statement**:
M365 deployment success depends on user adoption. Change management, training, and support MUST be proactive, user-centered, and measurable.

**Rationale**:
Technology deployment fails without user adoption. Cabinet Office must ensure staff are equipped, trained, and supported to work effectively with M365.

**Change Management Framework**:
- **ADKAR Model**: Awareness, Desire, Knowledge, Ability, Reinforcement
- **Stakeholder engagement**: Early and continuous involvement
- **Communication plan**: Multi-channel, tailored by audience
- **Resistance management**: Identify and address concerns

**Communication Channels**:
- **Intranet**: M365 adoption hub, FAQs, news
- **Email campaigns**: Phased announcements, tips and tricks
- **Yammer/Teams**: Community-led discussions, champions network
- **Town halls**: Leadership messages, Q&A sessions
- **Posters and digital signage**: Visual reminders, key messages

**Training Strategy**:
- **Role-based training**: Tailored to job functions (executive, administrator, knowledge worker)
- **Format diversity**: eLearning, instructor-led, quick reference guides, video tutorials
- **Just-in-time learning**: Contextual help, tooltips, chatbots
- **Hands-on practice**: Sandbox environment for safe experimentation
- **Accessibility training**: How to create accessible content

**User Support Model**:
- **Service desk**: Tier 1 support for basic M365 queries
- **M365 champions network**: Peer support, super users in each department
- **Self-service portal**: Knowledge base, how-to guides, troubleshooting
- **Office hours**: Drop-in sessions with M365 experts

**Adoption Metrics**:
- **Active users**: Daily/monthly active users (DAU/MAU)
- **Feature usage**: Teams adoption, SharePoint collaboration, OneDrive migration
- **Training completion**: % of users trained
- **Support tickets**: Volume and trends (declining indicates adoption success)
- **User satisfaction**: Surveys, Net Promoter Score (NPS)

**Champions Network**:
- **M365 Champions**: Enthusiastic early adopters in each directorate
- **Responsibilities**: Peer support, feedback to IT, evangelism
- **Benefits**: Early access to features, direct line to product team
- **Recognition**: Certificates, badges, leadership visibility

**Feedback Loops**:
- **User surveys**: Quarterly pulse surveys
- **Focus groups**: Targeted sessions for specific scenarios
- **Usage analytics**: Microsoft 365 usage reports, adoption dashboard
- **Continuous improvement**: Iterative refinement based on feedback

**Validation Gates**:
- [ ] Change management plan documented and approved
- [ ] Training materials created and accessible
- [ ] Champions network established
- [ ] Support model operational
- [ ] Adoption metrics dashboard published

---

## VII. Cost and Financial Governance

### 18. FinOps and License Optimization

**Principle Statement**:
M365 licensing and costs MUST be transparent, optimized, and aligned with user needs. License waste and over-provisioning are unacceptable uses of public funds.

**Rationale**:
Cabinet Office has a fiduciary duty to taxpayers to optimize technology spending. M365 licensing is complex and requires active management to avoid waste.

**License Governance**:
- **License assignment**: Only assign licenses to active users
- **License types**: Match license to user role (E3 vs E5 vs F3)
- **License reclamation**: Reclaim licenses from inactive users (automated)
- **License pooling**: Shared mailboxes, resource accounts (no license required)

**M365 License Tiers** (Cabinet Office Standard):
- **M365 E5**: Executives, senior civil servants, security/compliance roles (advanced security, analytics)
- **M365 E3**: Standard knowledge workers (core productivity, basic security)
- **M365 F3**: Frontline workers (limited requirements, mobile-first)
- **Add-ons**: Specific features (e.g., Power BI Pro, Visio) on exception basis

**Cost Optimization Strategies**:
- **Right-sizing**: E5 licenses only for users needing advanced features (e.g., Defender for Endpoint, Power BI Premium)
- **Inactive user cleanup**: Offboard users within 7 days of departure
- **Shared devices**: Shared Computer Activation for shared workstations
- **Guest access**: Use guest accounts (free) instead of full licenses
- **Power Platform**: Per-app plans instead of per-user where possible

**License Compliance**:
- Monthly license reconciliation
- Audit trail for license assignments
- True-up process for annual Microsoft contract renewal
- Compliance with Microsoft Product Terms and Online Services Terms

**Cost Tracking and Reporting**:
- Monthly cost reports by directorate
- Cost allocation to budget holders
- Variance analysis: Actual vs. budget
- Forecasting: Projected costs for new initiatives

**Budget Controls**:
- Budget allocated per directorate
- Approval workflow for license requests exceeding allocation
- Quarterly reviews with finance business partners
- Cost avoidance metrics (e.g., reduced on-prem infrastructure costs)

**Third-Party Tools** (Optional):
- CoreView, Quest On Demand, Veeam for M365 management and optimization
- Licensing optimization tools for recommendations

**Validation Gates**:
- [ ] License assignment policy enforced
- [ ] Inactive user cleanup automated
- [ ] Monthly cost reports published
- [ ] Quarterly license optimization review completed
- [ ] Budget tracking integrated with finance systems

---

## VIII. Compliance and Audit

### 19. Audit Logging and eDiscovery

**Principle Statement**:
All privileged operations, data access, and administrative actions MUST be logged immutably for compliance, audit, and forensic analysis with 7-year retention for OFFICIAL records.

**Rationale**:
Government Security Classifications Policy and Public Records Act require comprehensive audit trails. M365 audit logs are essential for accountability and incident investigation.

**M365 Unified Audit Log**:
- **Unified Audit Log (UAL)**: Enabled for all users and workloads
- **Coverage**: Exchange, SharePoint, OneDrive, Teams, Azure AD, Power Platform
- **Retention**: 7 years (OFFICIAL requirement) via long-term retention policies
- **Search**: PowerShell, Purview Compliance portal, SIEM integration

**Audit Log Categories**:
- **User activities**: File access, sharing, downloads, searches
- **Admin activities**: Configuration changes, permission grants, user creation
- **Security events**: Sign-ins, MFA, Conditional Access policy triggers
- **Compliance events**: DLP policy matches, retention label application, eDiscovery holds

**Critical Events to Monitor**:
- Global Admin role assignment
- Conditional Access policy modification
- DLP policy changes
- Sensitivity label changes
- External sharing of OFFICIAL-SENSITIVE content
- Mass downloads or deletions
- Guest account creation

**Audit Log Retention Policies**:
- **OFFICIAL records**: 7 years minimum (extendable to 10 years for E5)
- **OFFICIAL-SENSITIVE**: 10 years
- **Privileged operations**: 10 years
- **Temporary/transitory**: 1 year

**SIEM Integration** (Recommended):
- Microsoft Sentinel or third-party SIEM (Splunk, QRadar)
- Real-time ingestion of M365 audit logs
- Correlation rules for threat detection
- Automated alerting for suspicious activity
- Compliance dashboards

**eDiscovery Capabilities**:
- **Content Search**: Basic keyword search across all M365 content
- **eDiscovery (Standard)**: Case management, holds, exports
- **eDiscovery (Premium)**: Advanced analytics, threading, near-duplicate detection
- **Use cases**: FOI requests, employment tribunals, litigation, investigations

**eDiscovery Permissions**:
- **eDiscovery Manager**: Create and manage cases
- **eDiscovery Administrator**: Access all cases, assign permissions
- **Compliance Administrator**: View-only access for compliance reporting
- **Role-based access**: Segregation of duties (creator cannot be reviewer)

**Legal Hold and Preservation**:
- Litigation holds override retention policies
- In-place preservation for user mailboxes and sites
- Hold notifications to custodians
- Audit trail of hold activities

**Validation Gates**:
- [ ] Unified Audit Log enabled for all users
- [ ] 7-year retention configured
- [ ] SIEM integration tested
- [ ] eDiscovery permissions assigned
- [ ] Quarterly audit log reviews conducted

---

### 20. Compliance Score and Continuous Assessment

**Principle Statement**:
M365 configuration MUST be continuously assessed against Microsoft Purview Compliance Score and UK Government security baselines with quarterly compliance reviews.

**Rationale**:
Compliance is not a one-time activity but a continuous process. Compliance Score provides measurable, actionable recommendations.

**Microsoft Purview Compliance Score**:
- **Baseline score**: Initial assessment upon deployment
- **Target score**: 80%+ (Cabinet Office standard)
- **Improvement actions**: Prioritized recommendations
- **Score tracking**: Monthly trend analysis

**Compliance Frameworks Assessed**:
- **NCSC Cloud Security Principles**: 14 principles mapped to M365 controls
- **Cyber Essentials Plus**: Technical controls for cyber hygiene
- **ISO 27001**: Information security management
- **GDPR / UK Data Protection Act 2018**: Data protection controls
- **NIST Cybersecurity Framework**: Identify, Protect, Detect, Respond, Recover

**Compliance Posture Management**:
- **Automated assessment**: Daily compliance score updates
- **Policy enforcement**: Technical controls (not just documentation)
- **Remediation tracking**: Action owners, due dates, status
- **Evidence collection**: Automated evidence for auditors

**Quarterly Compliance Reviews**:
- **Stakeholders**: SIRO, IAO, Compliance Manager, IT Security
- **Review scope**: Compliance score changes, new risks, remediation progress
- **Outputs**: Action plan for next quarter, escalations for non-compliance

**External Audits**:
- **Annual IT Health Check**: NCSC-approved CHECK scheme assessments
- **Annual ISO 27001 audit**: External certification body
- **Internal audit**: Cabinet Office Internal Audit team
- **Microsoft compliance certifications**: ISO, SOC 2, FedRAMP (validated annually)

**Regulatory Inspections**:
- **ICO audits**: Data protection compliance
- **National Audit Office (NAO)**: Value for money, controls
- **Government Internal Audit Agency (GIAA)**: Governance and risk

**Continuous Improvement Cycle**:
1. **Assess**: Measure compliance score and control effectiveness
2. **Plan**: Identify improvement actions, prioritize by risk
3. **Implement**: Execute remediation actions
4. **Verify**: Test controls, validate compliance
5. **Report**: Update stakeholders, document evidence

**Validation Gates**:
- [ ] Compliance score baselined and tracked
- [ ] Improvement actions assigned with owners
- [ ] Quarterly compliance review scheduled
- [ ] External audit schedule confirmed
- [ ] Evidence repository maintained

---

## IX. Exception Process

### Exception Request Procedure

Exceptions to these principles require documented justification and formal approval. Exceptions are granted reluctantly and time-limited.

**Exception Request Must Include**:
1. **Principle Being Violated**: Specific principle number and description
2. **Business Justification**: Why exception is necessary (not merely convenient)
3. **Risk Assessment**: Security, operational, compliance, reputational risks
4. **Compensating Controls**: How risks will be mitigated (must be equivalent)
5. **Time Limit**: Exception expiration date (maximum 12 months, preference for 6 months)
6. **Remediation Plan**: Specific actions and timeline to achieve compliance
7. **Cost/Benefit Analysis**: Cost of exception vs. cost of compliance

**Approval Authority**:

| Risk Level | Approver | Turnaround Time |
|------------|----------|-----------------|
| **Low Risk** | Enterprise Architect | 5 business days |
| **Medium Risk** | Architecture Review Board (ARB) | 10 business days |
| **High Risk** | CTO + SIRO/CISO | 15 business days + Board briefing |
| **Security Principle Violations** | CISO + SIRO (mandatory) | Escalated review |

**Exception Categories**:
- **Technical limitation**: Technology cannot support requirement (compensating control required)
- **Timeline**: Compliance possible but delayed (interim controls required)
- **Cost**: Compliance cost disproportionate (must demonstrate value for money assessment)
- **Legacy system**: Existing system with sunset date (<12 months)

**Exception Registry**:
- All approved exceptions tracked in central registry (SharePoint list or Jira)
- Fields: Exception ID, principle violated, requestor, approver, approval date, expiry date, status
- Quarterly reviews: Re-assess necessity, extend or revoke
- Annual exception audit: Identify patterns, update principles if systemic exceptions

**Exception Monitoring**:
- Automated reminders 30 days before expiry
- Escalation if extension requested without remediation progress
- Reporting: Exception summary in quarterly ARB report

**Automatic Exception Denial Criteria**:
- Violates legal/regulatory requirement (GDPR, Public Records Act, Government Security Policy)
- Creates unacceptable security risk to OFFICIAL-SENSITIVE data
- No compensating controls possible
- Perpetual exception (no remediation plan)

**Validation Gates**:
- [ ] Exception request form completed in full
- [ ] Risk assessment quantified (likelihood × impact)
- [ ] Compensating controls documented and implemented
- [ ] Remediation plan with milestones
- [ ] Approval obtained at appropriate level

---

## X. Governance and Enforcement

### Architecture Review Process

All M365 projects and initiatives MUST undergo architecture review at defined gates to ensure compliance with these principles.

**Review Gates**:

**Gate 1: Initiation (Business Case)**
- **Trigger**: New M365 initiative, significant configuration change
- **Review**: Alignment with principles, feasibility, cost estimate
- **Reviewers**: Enterprise Architect + Business Relationship Manager
- **Outcome**: Approved to proceed to requirements / Rejected / More information required

**Gate 2: Requirements Complete**
- **Trigger**: Requirements documented
- **Review**: Requirements comply with architecture principles (security, accessibility, data classification)
- **Reviewers**: Domain Architect + Information Assurance Officer (IAO)
- **Outcome**: Proceed to design / Revise requirements

**Gate 3: Solution Design**
- **Trigger**: High-level design documented
- **Review**: Technology choices, integration patterns, security controls, data flows
- **Reviewers**: Enterprise Architect + CISO representative + Compliance Manager
- **Outcome**: Approved / Approved with conditions / Rejected

**Gate 4: Pre-Production**
- **Trigger**: Solution ready for UAT deployment
- **Review**: Testing completion, configuration as code, monitoring, runbooks, training materials
- **Reviewers**: Service Delivery Manager + Security Operations
- **Outcome**: Approved for UAT / Additional controls required

**Gate 5: Production Release**
- **Trigger**: UAT successful, ready for production
- **Review**: Change Advisory Board (CAB) approval, rollback plan, comms plan
- **Reviewers**: CAB (Change Manager, Service Owner, IT Operations)
- **Outcome**: Approved for production / Delayed / Rejected

**Gate 6: Post-Implementation Review (PIR)**
- **Trigger**: 90 days post-production release
- **Review**: Lessons learned, benefits realized, adoption metrics, incident trends
- **Reviewers**: Project team + Enterprise Architect + Business Owner
- **Outcome**: Formal project closure / Remediation actions

**Architecture Review Board (ARB)**:
- **Membership**: CTO (chair), Enterprise Architect, CISO, IAO, Compliance Manager, Domain Architects
- **Frequency**: Monthly (on-demand for urgent reviews)
- **Quorum**: Minimum 3 members including CTO or delegate
- **Decisions**: Recorded in ARB decision log, published to architecture community

**Review Outcomes**:
- **APPROVED**: Proceed to next phase immediately
- **APPROVED WITH CONDITIONS**: Minor issues, must address before next gate
- **DEFERRED**: Insufficient information, resubmit when ready
- **REJECTED**: Major concerns, fundamental redesign required

### Compliance Monitoring and Enforcement

**Automated Compliance Scanning**:
- **Microsoft Secure Score**: Daily automated assessment
- **Compliance Score**: Daily updates with improvement actions
- **Azure Policy / Policy as Code**: Continuous compliance checks
- **M365DSC Drift Detection**: Daily configuration drift monitoring
- **Third-party tools**: Qualys, Tenable for vulnerability scanning

**Manual Compliance Reviews**:
- **Quarterly**: Access reviews, exception registry review, compliance score review
- **Annual**: Architecture principles review, comprehensive audit

**Non-Compliance Escalation**:
1. **Detection**: Automated alert or audit finding
2. **Notification**: Service owner notified, 14 days to remediate
3. **Escalation (Day 15)**: CTO notified, remediation plan required
4. **Escalation (Day 30)**: ARB review, potential service suspension
5. **Enforcement (Day 45)**: Service disabled if non-compliance creates unacceptable risk

**Consequences for Non-Compliance**:
- **Low risk**: Warning, remediation deadline
- **Medium risk**: Escalation to senior management, project hold
- **High risk**: Service suspension, disciplinary action (for willful violations)

---

## XI. Amendment Process

### Modifying Principles

These principles are living documents and will be reviewed annually or when significant changes to M365, government policy, or threat landscape occur.

**Amendment Proposal Requirements**:
1. **Problem Statement**: Why current principle is inadequate
2. **Proposed Change**: Specific wording amendments
3. **Impact Analysis**: Affected systems, projects, costs
4. **Industry Benchmark**: How other government departments or comparable organizations address this
5. **Stakeholder Consultation**: Input from affected parties
6. **Migration Plan**: For existing non-compliant systems

**Approval Process**:
1. **Proposal Submission**: To Enterprise Architecture Team via email/service request
2. **Initial Review**: Enterprise Architect assesses completeness (5 business days)
3. **Stakeholder Consultation**: 2-week feedback period (architecture community, security, compliance)
4. **ARB Review**: Architecture Review Board discusses and votes
5. **CTO Approval**: Final sign-off by CTO/CIO
6. **Communication**: Email to all IT staff, intranet announcement, architecture community briefing
7. **Grace Period**: 90 days for existing systems to achieve compliance (extendable to 180 days with approval)

**Versioning**:
- Major version (e.g., 1.0 → 2.0): Significant changes requiring re-approval
- Minor version (e.g., 1.1 → 1.2): Clarifications, non-substantive updates
- Version history maintained in document control table

**Annual Review Cycle**:
- **Q4 each year**: Scheduled principles review
- **Inputs**: Exception trends, audit findings, new threats, Microsoft roadmap, government policy changes
- **Outputs**: Updated principles document, communication plan, training updates

---

## Appendices

### Appendix A: Glossary

- **BPSS**: Baseline Personnel Security Standard (vetting for civil servants)
- **CHECK**: NCSC scheme for IT health checks (penetration testing)
- **DLP**: Data Loss Prevention
- **Entra ID**: Microsoft's new branding for Azure Active Directory (Azure AD)
- **GDS**: Government Digital Service
- **IAO**: Information Asset Owner
- **M365DSC**: Microsoft 365 Desired State Configuration (IaC tool)
- **NCSC**: National Cyber Security Centre (part of GCHQ)
- **OFFICIAL**: UK Government Security Classification for routine business
- **OFFICIAL-SENSITIVE**: Subset of OFFICIAL requiring enhanced controls
- **PIM**: Privileged Identity Management (just-in-time admin access)
- **SIRO**: Senior Information Risk Owner
- **SPFx**: SharePoint Framework (modern development framework)
- **TCoP**: UK Government Technology Code of Practice
- **WCAG**: Web Content Accessibility Guidelines
- **Zero Trust**: Security model assuming no implicit trust, verify explicitly

### Appendix B: Reference Architecture Diagrams

*(To be developed)*

1. **M365 Logical Architecture**: Tenant structure, Azure AD, workload distribution
2. **Network Diagram**: Connectivity, ExpressRoute (if applicable), VPN, internet breakout
3. **Identity Architecture**: Azure AD, Conditional Access, MFA, PIM
4. **Information Protection Flow**: Sensitivity labels, DLP, encryption
5. **Data Flow Diagram**: External sharing, guest access, cross-border data flows
6. **Integration Architecture**: Power Platform, Microsoft Graph, third-party apps
7. **Disaster Recovery**: Multi-region, backup, BC/DR processes

### Appendix C: Related Documents

*(Links to supporting documentation)*

1. **M365 Configuration Baseline**: M365DSC export of approved tenant configuration
2. **Conditional Access Policy Catalog**: All policies with rationale
3. **Sensitivity Label Taxonomy**: OFFICIAL, OFFICIAL-SENSITIVE definitions
4. **Retention Schedule**: Document types and retention periods
5. **Power Platform DLP Policies**: Approved and blocked connectors
6. **Security Baseline**: CIS Microsoft 365 Foundations Benchmark, NCSC EUD Guidance
7. **Incident Response Playbooks**: Specific procedures for M365 security incidents
8. **Accessibility Guidelines**: WCAG compliance checklist for M365 content
9. **Training Catalog**: Links to M365 learning paths (Microsoft Learn, internal training)
10. **User Guides**: How-to documentation for end users

### Appendix D: Compliance Mapping

**NCSC Cloud Security Principles → M365 Controls**:

| NCSC Principle | M365 Control | Validation |
|----------------|--------------|------------|
| 1. Data in transit protection | TLS 1.3 enforced, certificate pinning | Network trace, Security Score |
| 2. Asset protection and resilience | UK South + UK West geo-redundancy | Tenant configuration |
| 3. Separation between users | Sensitivity labels, tenant isolation | Purview compliance |
| 4. Governance framework | SIRO/IAO appointed, ARB operational | Governance documentation |
| 5. Operational security | Microsoft managed patching, Secure Score | Monthly reports |
| 6. Personnel security | BPSS for all users, SC for admins | HR records |
| 7. Secure development | SPFx security review, code scanning | Code review logs |
| 8. Supply chain security | Microsoft attestations, third-party assessments | Vendor reviews |
| 9. Secure user management | Azure AD, MFA, Conditional Access | Sign-in logs |
| 10. Identity and authentication | Passwordless roadmap, FIDO2 | Authentication methods report |
| 11. External interface protection | DLP, Conditional Access, allowlists | DLP reports |
| 12. Secure service administration | PIM, PAW, admin audit logs | PIM reports |
| 13. Audit information for users | Unified Audit Log, 7-year retention | Audit log validation |
| 14. Secure use of service | Security awareness training | Training completion records |

**Technology Code of Practice → Architecture Principles**:

| TCoP Point | Principle | Status |
|------------|-----------|--------|
| 1. Define user needs | Principle 2 (GDS Standard Compliance) | Mandatory |
| 2. Make things accessible | Principle 4 (Accessibility WCAG 2.2 AA) | Mandatory |
| 3. Be open and use open source | Principle 5 (Open Standards) | Mandatory |
| 4. Make use of open standards | Principle 5 (Open Standards) | Mandatory |
| 5. Use cloud first | Principle 1 (Cloud-First UK Sovereignty) | Mandatory |
| 6. Make things secure | Principle 3 (Security by Design) | Non-Negotiable |
| 7. Make privacy integral | Principle 8 (Privacy by Design) | Mandatory |
| 8. Share, reuse and collaborate | Principle 13 (Collaboration Governance) | Enabled with controls |
| 9. Integrate and adapt technology | Principle 9 (Approved Tech Stack) | Mandatory |
| 10. Make better use of data | Principle 7 (Data Quality and Lifecycle) | Mandatory |

---

## Document Control

| Version | Date | Author | Changes |
|---------|------|--------|---------|
| 1.0 | 2025-10-17 | Enterprise Architecture Team | Initial draft for M365 deployment |

**Approvals** (To be obtained):

| Role | Name | Signature | Date |
|------|------|-----------|------|
| CTO, Cabinet Office | [NAME] | _________ | [DATE] |
| SIRO | [NAME] | _________ | [DATE] |
| CISO | [NAME] | _________ | [DATE] |
| Enterprise Architect | [NAME] | _________ | [DATE] |
| DPO (Data Protection Officer) | [NAME] | _________ | [DATE] |

---

**END OF DOCUMENT**

*This document is OFFICIAL and should be handled in accordance with Government Security Classifications Policy.*
