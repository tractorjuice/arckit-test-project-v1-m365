# Cabinet Office Microsoft 365 Architecture Principles

> **Template Status**: Live | **Version**: 0.11.2 | **Command**: `/arckit.principles`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-GLOBAL-PRIN-v1.2 |
| **Document Type** | Enterprise Architecture Principles |
| **Project** | Microsoft 365 GCC-H Migration (Global) |
| **Classification** | OFFICIAL |
| **Status** | APPROVED |
| **Version** | 1.2 |
| **Created Date** | 2025-10-17 |
| **Last Modified** | 2026-01-26 |
| **Template Version** | 0.11.2 |
| **Review Cycle** | Annual |
| **Next Review Date** | 2027-01-26 |
| **Owner** | Enterprise Architecture Team, Cabinet Office |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | All M365 Project Teams, IT Department |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2025-10-17 | ArcKit AI | Initial creation from `/arckit.principles` command | PENDING | PENDING |
| 1.1 | 2026-01-26 | ArcKit AI | Updated to align with template v0.11.1 format | PENDING | PENDING |
| 1.2 | 2026-01-26 | ArcKit AI | Updated to align with template v0.11.2 format | PENDING | PENDING |

---

## Executive Summary

This document establishes the immutable principles governing the Microsoft 365 deployment and all technology architecture decisions at the Cabinet Office. These principles ensure consistency, security, scalability, accessibility, and alignment with UK Government digital standards across all projects and initiatives.

**Scope**: All M365 workloads, integrations, and technology initiatives at Cabinet Office
**Authority**: Enterprise Architecture Review Board, Cabinet Office CTO
**Compliance**: Mandatory unless exception approved by CTO/CISO
**Regulatory Context**: UK Technology Code of Practice, GDS Service Standard, Government Security Classifications

**Philosophy**: These principles are **technology-agnostic** - they describe WHAT qualities the architecture must have, not HOW to implement them with specific products. Technology selection happens during research and design phases guided by these principles.

---

## I. Strategic Principles

### 1. Cloud-First with UK Sovereignty

**Principle Statement**:
All new solutions MUST leverage cloud-native services hosted in UK data centres to meet data sovereignty and UK Government Technology Code of Practice (TCoP) requirements.

**Rationale**:
Cloud platforms provide resilience, security, and cost efficiency while meeting Cabinet Office obligations under TCoP Point 3 (Use cloud first) and ensuring UK data sovereignty for OFFICIAL classified information.

**Implications**:
- All data stored in UK-based data centres
- Prefer managed cloud services over custom deployments
- Design for cloud-native identity and access management
- Leverage cloud-native security, compliance, and governance tools
- Multi-region resilience within UK geographic boundaries

**Data Sovereignty Requirements**:
- OFFICIAL data: UK regions only
- OFFICIAL-SENSITIVE: UK regions with enhanced encryption
- Customer lockbox controls enabled for vendor support access
- Data residency attestation documented

**Exceptions**:
- Legacy on-premises systems with documented migration roadmap (<24 months)
- Cross-government services requiring specific non-UK integrations (with SIRO approval)
- Edge devices requiring local caching (with encryption)

**Validation Gates**:
- [ ] All workloads configured for UK data residency
- [ ] Infrastructure defined as code and version-controlled
- [ ] Multi-region disaster recovery strategy documented
- [ ] Cost model with financial governance tags defined
- [ ] Data sovereignty attestation signed

---

### 2. Government Digital Service (GDS) Standard Compliance

**Principle Statement**:
All digital services MUST meet the 14-point GDS Service Standard and Technology Code of Practice to ensure accessible, usable, and inclusive government services.

**Rationale**:
Cabinet Office sets the standard for UK Government digital services. All deployments must exemplify best practice in accessibility, user-centred design, and open standards.

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

### 3. Security by Design (NON-NEGOTIABLE)

**Principle Statement**:
All architectures MUST implement UK Government Security Classification Policy with Zero Trust principles. Security is NON-NEGOTIABLE and appropriate to OFFICIAL data handling.

**Rationale**:
Cabinet Office handles OFFICIAL and OFFICIAL-SENSITIVE information requiring protective marking controls, secure-by-design architecture, and compliance with National Cyber Security Centre (NCSC) Cloud Security Principles.

**Government Security Classification Tiers**:
1. **OFFICIAL**: Majority of Cabinet Office information (default classification)
2. **OFFICIAL-SENSITIVE**: Subset requiring enhanced handling (Cabinet papers, policy development)
3. **SECRET**: Not handled in standard cloud environments (separate accreditation required)

**NCSC Cloud Security Principles Compliance**:
All 14 NCSC Cloud Security Principles MUST be addressed:
1. Data in transit protection (TLS 1.3+)
2. Asset protection and resilience (UK region redundancy)
3. Separation between users (tenant isolation, sensitivity labels)
4. Governance framework (SIRO, IAO appointed)
5. Operational security (patching, monitoring)
6. Personnel security (Baseline Personnel Security Standard - BPSS minimum)
7. Secure development (DevSecOps)
8. Supply chain security (vendor supply chain assurance)
9. Secure user management (MFA mandatory)
10. Identity and authentication (Conditional Access policies)
11. External interface protection (DLP, access controls)
12. Secure service administration (Privileged Identity Management)
13. Audit information for users (Audit logs, 7-year retention)
14. Secure use of the service (end-user security awareness)

**Zero Trust Pillars**:
1. **Verify explicitly**: Every access request fully authenticated and authorised
2. **Least privilege access**: Just-in-time, just-enough-access (JIT/JEA)
3. **Assume breach**: Minimise blast radius, segment access, verify end-to-end encryption

**Mandatory Security Controls**:
- [ ] Multi-factor authentication (MFA) mandatory for all users (no exceptions)
- [ ] Conditional Access policies enforcing device compliance
- [ ] Information protection with sensitivity labels (OFFICIAL, OFFICIAL-SENSITIVE)
- [ ] Data Loss Prevention (DLP) policies preventing unauthorised sharing
- [ ] Advanced threat protection enabled
- [ ] Encryption at rest (managed keys minimum, customer-managed optional for OFFICIAL-SENSITIVE)
- [ ] Encryption in transit (TLS 1.3+ mandatory)
- [ ] Privileged Identity Management (PIM) for admin roles
- [ ] Risk-based identity protection policies
- [ ] SIEM integration for security monitoring
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
- UK GDPR

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
- **Perceivable**: Alt text, captions, transcripts, sufficient colour contrast (4.5:1 minimum)
- **Operable**: Keyboard navigation, no keyboard traps, sufficient time limits
- **Understandable**: Plain English (reading age 9 per GDS guidelines), consistent navigation
- **Robust**: Compatible with assistive technologies (JAWS, NVDA, ZoomText)

**Content Accessibility**:
- All documents MUST pass Accessibility Checker before publishing
- PDF/A format for archival documents with tagged structure
- Video content MUST have captions and transcripts
- Forms MUST be screen reader accessible
- Colour MUST NOT be the only means of conveying information

**Testing Requirements**:
- Automated testing with accessibility scanning tools
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

### 5. Observability and Operational Excellence

**Principle Statement**:
All systems MUST emit structured telemetry (logs, metrics, traces) enabling real-time monitoring, troubleshooting, and capacity planning.

**Rationale**:
We cannot operate what we cannot observe. Instrumentation is a first-class architectural requirement, not an afterthought.

**Telemetry Requirements**:
- **Logging**: Structured logs with correlation IDs
- **Metrics**: Request volume, latency percentiles (p50, p95, p99), error rates
- **Tracing**: Distributed trace context for request flows
- **Alerting**: Service Level Objective (SLO)-based alerting with actionable runbooks

**Required Instrumentation**:
- Request volume, latency distribution, error rate
- Resource utilisation (CPU, memory, I/O, network)
- Business metrics (transactions, revenue impact, user actions)
- Security events (auth failures, policy violations, suspicious patterns)

**Log Retention**:
- **Security/audit logs**: As required by compliance (typically 1-7 years)
- **Application logs**: Sufficient for troubleshooting (typically 30-90 days)
- **Metrics**: Long-term trends (typically 1-2 years with aggregation)

**Validation Gates**:
- [ ] Logging, metrics, tracing instrumented
- [ ] Dashboards and alerts configured
- [ ] Service Level Objectives (SLOs) and Service Level Indicators (SLIs) defined
- [ ] Runbooks created for common failure scenarios
- [ ] Capacity planning metrics tracked

---

## II. Data Principles

### 6. Data Sovereignty and Classification

**Principle Statement**:
All data MUST be classified according to Government Security Classifications and stored in UK regions with appropriate protective marking controls.

**Rationale**:
Cabinet Office handles sensitive government information requiring clear classification, UK data residency, and controls aligned with Government Security Policy Framework.

**Data Classification and Handling**:

| Classification | Description | Storage Location | Encryption | Sharing Restrictions |
|----------------|-------------|------------------|------------|---------------------|
| **OFFICIAL** | Routine public sector business | UK regions | TLS 1.3 + AES-256 at rest | Within HMG with need-to-know |
| **OFFICIAL-SENSITIVE** | Damaging if lost/stolen (policy, personnel) | UK regions | Customer-managed keys | Restricted distribution |
| **SECRET** | Serious damage to national interests | N/A - Accredited system | N/A | N/A |

**Data Residency Requirements**:
- **OFFICIAL**: UK data centres (primary), UK (DR)
- **OFFICIAL-SENSITIVE**: UK data centres (primary), UK (DR), customer-managed keys
- **Multi-Geo**: NOT enabled (all data remains in UK)
- **Data Location Validation**: Monthly attestation reports

**Data Loss Prevention (DLP)**:
- Block external sharing of OFFICIAL-SENSITIVE content
- Detect and protect sensitive information types (NI numbers, passport numbers, policy document patterns)
- Prevent upload to personal cloud services
- Alert on bulk downloads exceeding thresholds
- Endpoint DLP for devices accessing services

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
- Anonymised/pseudonymised data for analytics (with DPO approval)

**Validation Gates**:
- [ ] All content labelled with sensitivity classification
- [ ] UK data residency validated
- [ ] DLP policies configured and tested
- [ ] Retention schedules applied
- [ ] GDPR compliance documented

---

### 7. Data Quality and Lineage

**Principle Statement**:
Data pipelines MUST maintain data quality standards and provide end-to-end lineage for auditability and troubleshooting.

**Rationale**:
Poor data quality undermines policy decisions and service delivery. Cabinet Office requires high-quality data with clear ownership and lifecycle management.

**Quality Standards**:
- **Completeness**: No unexpected nulls in required fields
- **Consistency**: Cross-system data reconciliation
- **Accuracy**: Validation rules and constraints enforced at source
- **Timeliness**: Freshness Service Level Agreements (SLAs) defined and monitored

**Lineage Requirements**:
- Source-to-target mapping documented for all data flows
- Transformation logic version-controlled and reviewable
- Data quality metrics tracked per pipeline
- Impact analysis capability for schema changes

**Data Lifecycle Stages**:
1. **Creation/Capture**: Classification at source, quality validation
2. **Active Use**: Accessible to authorised users, version controlled
3. **Review**: Periodic review of accuracy and relevance
4. **Archive**: Moved to long-term storage
5. **Disposal**: Secure deletion after retention period

**Validation Gates**:
- [ ] Data owners assigned for key datasets
- [ ] Quality rules defined and enforced
- [ ] Lifecycle policies configured
- [ ] Data catalogue populated

---

### 8. Single Source of Truth

**Principle Statement**:
Every data domain MUST have a single authoritative source. Derived copies must be clearly labelled and synchronised.

**Rationale**:
Multiple authoritative sources create inconsistency, reconciliation overhead, and data integrity issues.

**Implications**:
- Identify the system of record for each data domain
- Derived/cached copies are read-only and clearly labelled as such
- Synchronisation strategy defined for all derived copies
- Avoid bidirectional synchronisation (creates split-brain scenarios)

**Validation Gates**:
- [ ] System of record identified for each data entity
- [ ] Derived copies documented with sync frequency
- [ ] No bidirectional sync without conflict resolution strategy
- [ ] Master data management (MDM) strategy for shared reference data

---

## III. Integration Principles

### 9. Loose Coupling

**Principle Statement**:
Systems MUST be loosely coupled through published interfaces, avoiding shared databases, file systems, or tight runtime dependencies.

**Rationale**:
Loose coupling enables independent deployment, technology diversity, team autonomy, and system evolution without breaking dependencies.

**Implications**:
- Communicate through published APIs or asynchronous events
- No direct database access across system boundaries
- Each system manages its own data lifecycle
- Shared libraries kept minimal (favour duplication over coupling)
- Avoid distributed transactions across systems

**Validation Gates**:
- [ ] Systems communicate via APIs or events, not database
- [ ] No shared mutable state
- [ ] Each system has independent data store
- [ ] Deployment of one system doesn't require deployment of another
- [ ] Interface changes versioned with backward compatibility

---

### 10. Interoperability and Open Standards

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

**Data Portability**:
- Users can export data in open formats
- No proprietary lock-in for citizen data
- Migration paths to alternative solutions documented

**Cross-Government Integration**:
- GOV.UK Verify / One Login integration
- Government Digital Identity (GDI) alignment
- Cross-government APIs follow GDS API standards
- Shared platforms (e.g., GOV.UK Notify, GOV.UK Pay) prioritised

**Exceptions**:
- Specialised functionality where no open standard exists (document with rationale)
- Legacy integrations during migration period (max 18 months with roadmap)

**Validation Gates**:
- [ ] Open standards compliance verified
- [ ] Data export capability in open formats tested
- [ ] API specifications published (OpenAPI 3.0+)
- [ ] Cross-government interoperability tested where applicable

---

### 11. Asynchronous Communication

**Principle Statement**:
Systems SHOULD use asynchronous communication for non-real-time interactions to improve resilience and decoupling.

**Rationale**:
Asynchronous patterns reduce temporal coupling, improve fault tolerance, and enable better scalability.

**When to Use Async**:
- Non-real-time business processes (order fulfilment, batch jobs)
- Event notification and pub/sub patterns
- Long-running operations that don't require immediate response
- Integration with unreliable or slow external systems

**When Synchronous is Acceptable**:
- Real-time user interactions requiring immediate feedback
- Query operations (read-only, idempotent)
- Transactions requiring immediate consistency

**Validation Gates**:
- [ ] Async patterns used for non-real-time flows
- [ ] Message durability and delivery guarantees defined
- [ ] Event schemas versioned and published
- [ ] Dead letter queues and error handling configured

---

## IV. Quality Attributes

### 12. Scalability and Elasticity

**Principle Statement**:
All systems MUST be designed to scale horizontally to meet demand, with the ability to dynamically adjust capacity based on load.

**Rationale**:
Business demand is unpredictable and variable. Systems must handle both growth and traffic spikes without manual intervention or architectural changes.

**Implications**:
- Design for stateless components that can be replicated
- Avoid hard-coded limits or fixed capacity assumptions
- Plan for distributed deployment across multiple compute nodes
- Use load balancing to distribute traffic across instances
- Implement auto-scaling based on demand metrics

**Validation Gates**:
- [ ] System can scale horizontally (add more instances)
- [ ] No single points of failure that limit scaling
- [ ] Load testing demonstrates capacity growth with added resources
- [ ] Scaling metrics and triggers defined
- [ ] Cost model accounts for variable capacity

---

### 13. Resilience and Fault Tolerance

**Principle Statement**:
All systems MUST gracefully degrade when dependencies fail and recover automatically without data loss or manual intervention.

**Rationale**:
Failures are inevitable in distributed systems. The architecture must assume failures will occur and design for resilience rather than perfect reliability.

**Implications**:
- Implement circuit breakers for external dependencies
- Use timeouts on all network calls
- Retry with exponential backoff for transient failures
- Graceful degradation when non-critical services fail
- Automated health checks and recovery
- Avoid cascading failures through bulkhead isolation

**Validation Gates**:
- [ ] Failure modes identified and mitigated
- [ ] Chaos engineering or fault injection testing performed
- [ ] Recovery Time Objective (RTO) and Recovery Point Objective (RPO) defined
- [ ] Automated failover tested
- [ ] Degraded mode behaviour documented

---

### 14. Performance and Efficiency

**Principle Statement**:
All systems MUST meet defined performance targets under expected load with efficient use of computational resources.

**Performance Targets** (define for each system):
- **Response Time**: p50, p95, p99 latency targets
- **Throughput**: Requests per second, transactions per minute
- **Concurrency**: Simultaneous user/request capacity
- **Resource Efficiency**: CPU/memory utilisation targets

**Implications**:
- Performance requirements defined before implementation
- Load testing performed before production deployment
- Performance monitoring continuous, not just point-in-time
- Optimise hot paths identified through profiling
- Caching strategies for expensive operations

**Validation Gates**:
- [ ] Performance requirements defined with measurable targets
- [ ] Load testing performed at expected capacity
- [ ] Performance metrics monitored in production
- [ ] Capacity planning model defined

---

### 15. Availability and Reliability

**Principle Statement**:
All systems MUST meet defined availability targets with automated recovery and minimal data loss.

**Availability Targets** (define for each system):
- **Uptime SLA**: e.g., 99.9% (43.8 min downtime/month), 99.95%, 99.99%
- **Recovery Time Objective (RTO)**: Maximum acceptable downtime
- **Recovery Point Objective (RPO)**: Maximum acceptable data loss

**High Availability Patterns**:
- Redundancy across availability zones / data centres
- Automated health checks and failover
- Active-active or active-passive configurations
- Regular disaster recovery testing

**Validation Gates**:
- [ ] Availability SLA defined
- [ ] RTO and RPO requirements documented
- [ ] Redundancy strategy implemented
- [ ] Failover tested regularly
- [ ] Backup and restore procedures validated

---

### 16. Maintainability and Evolvability

**Principle Statement**:
All systems MUST be designed for change, with clear separation of concerns, modular architecture, and comprehensive documentation.

**Rationale**:
Software spends most of its lifetime in maintenance. Design decisions should optimise for understandability and modifiability.

**Implications**:
- Modular architecture with clear boundaries
- Separation of concerns (business logic, data access, presentation)
- Code is self-documenting with meaningful names
- Architecture Decision Records (ADRs) for significant choices
- Automated testing to enable confident refactoring

**Validation Gates**:
- [ ] Architecture documentation exists and is current
- [ ] Module boundaries clear with defined responsibilities
- [ ] Automated test coverage enables safe refactoring
- [ ] Architecture Decision Records (ADRs) document key choices

---

## V. Development Practices

### 17. Infrastructure as Code

**Principle Statement**:
All infrastructure MUST be defined as code, version-controlled, and deployed through automated pipelines.

**Rationale**:
Manual infrastructure changes create drift, inconsistency, and undocumented state. Infrastructure as Code (IaC) enables repeatability, auditability, and disaster recovery.

**Implications**:
- All infrastructure defined in declarative code
- Infrastructure changes go through code review
- Environments are reproducible from code
- No manual changes to production infrastructure
- Infrastructure versioned alongside application code

**Validation Gates**:
- [ ] Infrastructure defined as code
- [ ] Infrastructure code version-controlled
- [ ] Automated deployment pipeline for infrastructure
- [ ] No manual infrastructure changes in production

---

### 18. Automated Testing

**Principle Statement**:
All code changes MUST be validated through automated testing before deployment to production.

**Test Pyramid**:
- **Unit Tests**: Fast, isolated, high coverage (70-80% of tests)
- **Integration Tests**: Test component interactions (15-20% of tests)
- **End-to-End Tests**: Critical user journeys (5-10% of tests)

**Required Test Types**:
- Functional tests (does it work?)
- Performance tests (is it fast enough?)
- Security tests (is it secure?)
- Resilience tests (does it handle failures?)

**Validation Gates**:
- [ ] Automated tests exist and pass before merge
- [ ] Test coverage meets defined thresholds
- [ ] Critical paths have end-to-end tests
- [ ] Performance tests run regularly

---

### 19. Continuous Integration and Deployment

**Principle Statement**:
All code changes MUST go through automated build, test, and deployment pipelines with quality gates at each stage.

**Pipeline Stages**:
1. **Source Control**: All changes committed to version control
2. **Build**: Automated compilation and packaging
3. **Test**: Automated test execution
4. **Security Scan**: Dependency and code vulnerability scanning
5. **Deployment**: Automated deployment to environments

**Quality Gates**:
- All tests must pass
- No critical security vulnerabilities
- Code review approval required
- Deployment requires production readiness checklist

**Validation Gates**:
- [ ] Automated CI/CD pipeline exists
- [ ] Pipeline includes security scanning
- [ ] Deployment is automated and repeatable
- [ ] Rollback capability tested

---

## VI. Exception Process

### Requesting Architecture Exceptions

Principles are mandatory unless a documented exception is approved by the Enterprise Architecture Review Board.

**Valid Exception Reasons**:
- Technical constraints that prevent compliance
- Regulatory or legal requirements
- Transitional state during migration
- Pilot/proof-of-concept with defined end date

**Exception Request Requirements**:
- [ ] Justification with business/technical rationale
- [ ] Alternative approach and compensating controls
- [ ] Risk assessment and mitigation plan
- [ ] Expiration date (exceptions are time-bound)
- [ ] Remediation plan to achieve compliance

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
- All approved exceptions tracked in central registry
- Quarterly reviews: Re-assess necessity, extend or revoke
- Annual exception audit: Identify patterns, update principles if systemic exceptions

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

## VII. Governance and Compliance

### Architecture Review Gates

All projects must pass architecture reviews at key milestones:

**Discovery/Alpha**:
- [ ] Architecture principles understood
- [ ] High-level approach aligns with principles
- [ ] No obvious principle violations

**Beta/Design**:
- [ ] Detailed architecture documented
- [ ] Compliance with each principle validated
- [ ] Exceptions requested and approved
- [ ] Security and data principles validated

**Pre-Production**:
- [ ] Implementation matches approved architecture
- [ ] All validation gates passed
- [ ] Operational readiness verified

### Enforcement

- Architecture reviews are **mandatory** for all projects
- Principle violations must be remediated before production deployment
- Approved exceptions are time-bound and reviewed quarterly
- Retrospective reviews for compliance on live systems

---

## VIII. Appendix

### Principle Summary Checklist

| # | Principle | Category | Criticality | Validation |
|---|-----------|----------|-------------|------------|
| 1 | Cloud-First UK Sovereignty | Strategic | HIGH | Data residency attestation |
| 2 | GDS Standard Compliance | Strategic | HIGH | Service assessment |
| 3 | Security by Design | Strategic | CRITICAL | Threat model, pen testing |
| 4 | Accessibility (WCAG 2.2 AA) | Strategic | CRITICAL | Accessibility audit |
| 5 | Observability | Strategic | HIGH | Metrics, logs, traces |
| 6 | Data Sovereignty | Data | CRITICAL | Compliance audit |
| 7 | Data Quality & Lineage | Data | MEDIUM | Quality metrics |
| 8 | Single Source of Truth | Data | HIGH | Data lineage |
| 9 | Loose Coupling | Integration | HIGH | Deployment independence |
| 10 | Open Standards | Integration | HIGH | Standards compliance |
| 11 | Asynchronous Communication | Integration | MEDIUM | Async patterns used |
| 12 | Scalability | Quality | HIGH | Load testing |
| 13 | Resilience | Quality | CRITICAL | Chaos testing, RTO/RPO |
| 14 | Performance | Quality | HIGH | Load testing |
| 15 | Availability | Quality | CRITICAL | SLA monitoring |
| 16 | Maintainability | Quality | MEDIUM | Documentation, tests |
| 17 | Infrastructure as Code | DevOps | HIGH | IaC coverage |
| 18 | Automated Testing | DevOps | HIGH | Test coverage |
| 19 | CI/CD | DevOps | HIGH | Pipeline exists |

### NCSC Cloud Security Principles Mapping

| NCSC Principle | Architecture Principle | Validation |
|----------------|------------------------|------------|
| 1. Data in transit protection | 3. Security by Design | TLS 1.3 enforcement |
| 2. Asset protection and resilience | 1. Cloud-First UK Sovereignty | UK region redundancy |
| 3. Separation between users | 6. Data Sovereignty | Sensitivity labels |
| 4. Governance framework | VII. Governance | SIRO/IAO appointed |
| 5. Operational security | 5. Observability | Patching, monitoring |
| 6. Personnel security | 3. Security by Design | BPSS clearance |
| 7. Secure development | 19. CI/CD | DevSecOps pipeline |
| 8. Supply chain security | 3. Security by Design | Vendor assessments |
| 9. Secure user management | 3. Security by Design | MFA mandatory |
| 10. Identity and authentication | 3. Security by Design | Conditional Access |
| 11. External interface protection | 6. Data Sovereignty | DLP policies |
| 12. Secure service administration | 3. Security by Design | PIM for admins |
| 13. Audit information | 5. Observability | 7-year log retention |
| 14. Secure use of service | 3. Security by Design | Security training |

### Technology Code of Practice Mapping

| TCoP Point | Architecture Principle | Status |
|------------|------------------------|--------|
| 1. Define user needs | 2. GDS Standard Compliance | Mandatory |
| 2. Make things accessible | 4. Accessibility (WCAG 2.2 AA) | Mandatory |
| 3. Use cloud first | 1. Cloud-First UK Sovereignty | Mandatory |
| 4. Make use of open standards | 10. Interoperability & Open Standards | Mandatory |
| 5. Use open source | 10. Interoperability & Open Standards | Mandatory |
| 6. Make things secure | 3. Security by Design | Non-Negotiable |
| 7. Make privacy integral | 6. Data Sovereignty | Mandatory |
| 8. Share, reuse and collaborate | 9. Loose Coupling | Enabled with controls |
| 9. Integrate and adapt technology | 10. Interoperability & Open Standards | Mandatory |
| 10. Make better use of data | 7. Data Quality & Lineage | Mandatory |

### Glossary

- **BPSS**: Baseline Personnel Security Standard (vetting for civil servants)
- **CHECK**: NCSC scheme for IT health checks (penetration testing)
- **DLP**: Data Loss Prevention
- **GDS**: Government Digital Service
- **IAO**: Information Asset Owner
- **NCSC**: National Cyber Security Centre (part of GCHQ)
- **OFFICIAL**: UK Government Security Classification for routine business
- **OFFICIAL-SENSITIVE**: Subset of OFFICIAL requiring enhanced controls
- **PIM**: Privileged Identity Management (just-in-time admin access)
- **SIRO**: Senior Information Risk Owner
- **TCoP**: UK Government Technology Code of Practice
- **WCAG**: Web Content Accessibility Guidelines
- **Zero Trust**: Security model assuming no implicit trust, verify explicitly

---

**Generated by**: ArcKit `/arckit.principles` command
**Generated on**: 2026-01-26
**ArcKit Version**: 0.11.2
**Project**: Microsoft 365 GCC-H Migration (Global)
**AI Model**: Claude Opus 4.5

---

*This document is OFFICIAL and should be handled in accordance with Government Security Classifications Policy.*
