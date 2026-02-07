# GDS Service Assessment Preparation Report

> **Template Status**: Beta | **Version**: 2.1.6 | **Command**: `/arckit.service-assessment`

## Document Control

| Field | Value |
|-------|-------|
| **Document ID** | ARC-001-SASS-v1.0 |
| **Document Type** | GDS Service Assessment Preparation Report |
| **Project** | Exchange Online Migration to Microsoft 365 (Project 001) |
| **Classification** | OFFICIAL |
| **Status** | DRAFT |
| **Version** | 1.0 |
| **Created Date** | 2026-02-07 |
| **Last Modified** | 2026-02-07 |
| **Review Cycle** | On-Demand |
| **Next Review Date** | Prior to assessment booking |
| **Owner** | Enterprise Architecture Team, Cabinet Office |
| **Reviewed By** | PENDING |
| **Approved By** | PENDING |
| **Distribution** | Service Owner, Project Team, GDS Assessment Panel |
| **Assessment Phase** | Alpha |
| **Assessment Date** | Not yet scheduled |

## Revision History

| Version | Date | Author | Changes | Approved By | Approval Date |
|---------|------|--------|---------|-------------|---------------|
| 1.0 | 2026-02-07 | ArcKit AI | Initial creation from `/arckit.service-assessment` command | PENDING | PENDING |

---

## Executive Summary

**Overall Readiness**: 🟡 Amber (Nearly Ready)

**Readiness Score**: 10/14 points ready or partially ready

**Breakdown**:
- 🟢 Green: 5 points (Points 9, 10, 11, 13, 14)
- 🟡 Amber: 5 points (Points 1, 2, 3, 4, 5)
- 🔴 Red: 4 points (Points 6, 7, 8, 12)

**Summary**:

The Cabinet Office Exchange Online Migration project demonstrates strong Alpha-phase evidence for security, privacy, technology choices, success metrics, open standards, and service reliability. These strengths stem from comprehensive requirements documentation (48 requirements), detailed stakeholder analysis (10 drivers, 6 goals), a traceability matrix with 100% test coverage, and architecture diagrams showing the M365 solution design.

However, the assessment reveals significant gaps in user research methodology, team documentation, agile practices evidence, iteration history, and open source approach. These gaps are characteristic of an infrastructure migration project where the "service" is primarily an internal IT capability (email) rather than a citizen-facing digital service. The GDS Service Standard was designed for citizen-facing services, and several points require adaptation for internal enterprise migrations. Assessors should be briefed on this context.

The most critical gaps are the lack of a documented multidisciplinary team structure (Point 6), no evidence of agile ceremonies or sprint cadence (Point 7), no iteration log showing design evolution (Point 8), and no open source approach (Point 12). These require 4-6 weeks of remediation work before the project is ready for a formal Alpha assessment.

**Critical Gaps** (Must address before assessment):
- Point 6: No documented multidisciplinary team composition or skills audit
- Point 7: No evidence of agile ceremonies, sprint cadence, or backlog management
- Point 8: No iteration log or evidence of prototype iterations based on user feedback
- Point 12: No open source strategy or public code repository approach defined

**Key Strengths**:
- Exceptional security and privacy evidence (Point 9): 11 NON-NEGOTIABLE security requirements, NCSC Cloud Security Principles mapping, Zero Trust architecture
- Strong success metrics definition (Point 10): Business, technical, and adoption KPIs with baselines and targets
- Well-justified technology choices (Point 11): M365 E5 selection backed by build-vs-buy analysis, evaluation criteria, and TCoP alignment
- Comprehensive reliability planning (Point 14): 99.9% SLA, RPO/RTO defined, DR strategy documented
- Open standards commitment (Point 13): SMTP, OAuth 2.0, Graph API, data portability (PST/EML export)

**Recommended Timeline**:
- Complete critical actions: 4-6 weeks
- Complete high priority actions: 2-3 additional weeks
- Buffer for preparation: 1 week
- **Ready to book after**: approximately 8-10 weeks from today (mid-April 2026)

---

## Service Standard Assessment (14 Points)

### 1. Understand Users and Their Needs

**Status**: 🟡 Partial

**What This Point Means**:
You need to understand your users and their needs through research. This means finding out who your users are, what they're trying to do, and what problems or frustrations they experience.

**Why It Matters**:
If you don't understand your users, you can't build a service that meets their needs. Understanding users drives all design and prioritisation decisions.

**Evidence Required for Alpha**:
- User needs documented from research
- User groups and personas identified
- Prototype testing results with real users
- Evidence of research with diverse user groups

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-STKE-v1.0.md** (lines 55-107)
   - 13 internal stakeholders identified with influence/interest mapping
   - 7 external stakeholders identified
   - Power-Interest grid demonstrating stakeholder segmentation
   - This demonstrates structured stakeholder identification

✅ **ARC-001-STKE-v1.0.md** (lines 112-423)
   - 10 stakeholder drivers analysed in depth (SD-1 to SD-10)
   - Each driver includes context, intensity, enablers, blockers
   - Drivers cover: CTO deadline, cost reduction, SIRO risk acceptance, CISO security, DPO GDPR, directorate continuity, end user disruption, change management, service desk volume, exchange admin career
   - This demonstrates deep understanding of stakeholder motivations

✅ **ARC-001-STKE-v1.0.md** (lines 1171-1182)
   - Pre-migration user survey conducted (n=350, 10% sample)
   - Results: 78% satisfied with current system, 65% want mobile, 45% have concerns, top concern "learning new system" (32%)
   - Preferred training formats: video (40%), written (30%), drop-in (30%)
   - This demonstrates some quantitative user research

✅ **ARC-001-REQ-v1.0.md** (lines 359-372)
   - User experience requirements defined (NFR-U-001, NFR-U-002)
   - Accessibility requirements (WCAG 2.2 AA) specified
   - User persona implied: "medium proficiency users (policy advisors, administrators)"

❌ **Missing**: Formal user research sessions (qualitative interviews, contextual inquiry)
❌ **Missing**: User personas with detailed characteristics, goals, frustrations
❌ **Missing**: Prototype testing results with real users
❌ **Missing**: Research with diverse user groups including people with disabilities
⚠️ **Weak**: Survey is quantitative only (n=350) - no qualitative depth; no disability users included

**Gap Analysis**:
The project has strong stakeholder analysis but weak user research. Stakeholder drivers are well-documented but these represent organisational needs, not end-user needs. The pre-migration survey provides useful quantitative data but lacks qualitative depth. No formal user research sessions have been conducted with civil servants to understand how they actually use email, what problems they face, or what they need from the migration. No prototype testing evidence exists.

**Readiness Rating**: 🟡 Amber

**Strengths**:
- Comprehensive stakeholder mapping with 10 detailed driver analyses
- Quantitative survey data (n=350) providing baseline metrics
- Clear user persona implied through requirements

**Weaknesses**:
- No qualitative user research (interviews, observation)
- No formal user personas document
- No prototype/design testing with real users
- No research with diverse groups or disability users

**Recommendations**:

1. **High**: Conduct 6-8 qualitative user research sessions with civil servants
   - Timeline: 2-3 weeks
   - Owner: User Researcher
   - Evidence to create: User research findings report, user personas, user needs statements

2. **High**: Test OWA/Outlook mobile prototype experience with 5+ users including at least 1 disability user
   - Timeline: 1-2 weeks (can run parallel with above)
   - Owner: User Researcher
   - Evidence to create: Prototype testing report, usability findings, accessibility observations

3. **Medium**: Create formal user personas based on research
   - Timeline: 3-5 days (after research sessions)
   - Owner: User Researcher
   - Evidence to create: 3-4 user personas with goals, pain points, digital confidence levels

**Assessment Day Guidance**:
- **Prepare**: User research playback deck showing methodology, participants, findings
- **Show**: User journey maps, personas, survey results, research wall/board
- **Bring**: User Researcher to present findings
- **Materials**: Survey data, any research session recordings/notes
- **Likely Questions**:
  - "How did you decide what to research?"
  - "How diverse were your research participants?"
  - "What surprised you from your research?"
  - "How has research influenced the migration approach?"

---

### 2. Solve a Whole Problem for Users

**Status**: 🟡 Partial

**What This Point Means**:
Work towards creating a service that solves a whole problem for users. This means understanding the full context of what users are trying to do, not just the government part.

**Why It Matters**:
Users don't think in terms of organisational boundaries. They need email to work reliably across all their tasks, devices, and contexts.

**Evidence Required for Alpha**:
- User journey maps showing end-to-end experience
- Problem definition beyond government touchpoints
- Understanding of user context before/after service interaction
- Identification of pain points in current experience

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 39-57)
   - Executive summary defines complete problem scope: 3,500 users, on-prem Exchange 2016 end-of-support
   - End-to-end scope: migration, mobile access, security controls, decommission
   - In-scope/out-of-scope clearly defined

✅ **ARC-001-REQ-v1.0.md** (lines 111-251)
   - 15 functional requirements covering complete email journey: mailbox migration, identity, data residency, Conditional Access, sensitivity labels, DLP, Defender, retention, eDiscovery, Intune, audit log, shared mailboxes, mail flow rules, OWA, Outlook desktop
   - This demonstrates the full service scope is covered

✅ **ARC-001-STKE-v1.0.md** (lines 296-327)
   - SD-7 (End Users) identifies: "Continue working productively with minimal learning curve, reliable email access, and clear guidance"
   - Context: users range from digitally confident to digitally anxious, many used on-prem Outlook 10+ years

✅ **ARC-001-DIAG-001-v1.0.md** (lines 41-100)
   - C4 Container diagram shows end-to-end architecture: user → Outlook clients → Exchange Online → mailbox storage, including all integrations (AD, Intune, Defender, Purview, Sentinel, cross-government email)

❌ **Missing**: Formal user journey maps
❌ **Missing**: Pain point analysis of current email experience
⚠️ **Weak**: Problem is defined from IT perspective (migration) rather than user perspective (email needs)

**Gap Analysis**:
The project comprehensively defines the technical scope of the migration but frames it from an IT perspective. User journey maps showing the end-to-end email experience (from sending to receiving, from desktop to mobile, from internal to cross-government) do not exist. However, for an Alpha assessment of an internal migration, the clear problem definition and complete scope coverage are reasonable.

**Readiness Rating**: 🟡 Amber

**Strengths**:
- Complete scope definition with clear in/out boundaries
- 15 functional requirements covering entire email lifecycle
- Architecture diagram showing end-to-end solution

**Weaknesses**:
- No formal user journey maps
- Problem framed from IT/migration perspective, not user perspective
- Pain points of current experience not systematically documented

**Recommendations**:

1. **High**: Create 2-3 user journey maps covering key scenarios
   - Timeline: 1 week
   - Owner: Service Designer / User Researcher
   - Evidence to create: Journey maps for: (1) daily email usage, (2) migration experience, (3) mobile access setup

2. **Medium**: Document current pain points from survey data and stakeholder interviews
   - Timeline: 3 days
   - Owner: User Researcher
   - Evidence to create: Pain point catalogue linked to migration benefits

**Assessment Day Guidance**:
- **Prepare**: User journey maps (even simple ones), scope definition diagram
- **Show**: C4 container diagram showing end-to-end architecture
- **Bring**: Product Manager to explain scope decisions
- **Likely Questions**:
  - "How does this service fit into the wider user experience?"
  - "What happens when users switch between devices?"
  - "How do you handle the transition period during migration?"

---

### 3. Provide a Joined Up Experience Across All Channels

**Status**: 🟡 Partial

**What This Point Means**:
Create a joined up experience across all channels. Users should be able to complete their tasks regardless of which channel they use, and switching between channels should be seamless.

**Why It Matters**:
Civil servants access email from desktop Outlook, OWA (browser), and mobile devices. The experience must be consistent and seamless across all channels.

**Evidence Required for Alpha**:
- Channels identified and mapped
- Integration strategy defined
- Consistent branding and messaging planned
- Understanding of user channel preferences

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 236-251)
   - FR-014 (OWA), FR-015 (Outlook Desktop): Both channels defined with acceptance criteria
   - FR-010 (Intune MDM): Mobile channel defined with device compliance requirements

✅ **ARC-001-DIAG-001-v1.0.md** (lines 45-63)
   - Container diagram shows 4 user channels: OWA, Outlook Desktop, Outlook Mobile, Admin Center
   - Relationships show each channel connecting to Exchange Online

✅ **ARC-001-STKE-v1.0.md** (line 1180)
   - Survey shows channel preferences: 65% want mobile access
   - BR-004 targets 100% users accessing via OWA/mobile

✅ **ARC-001-REQ-v1.0.md** (lines 143-148)
   - FR-004 (Conditional Access) defines different access levels per channel/context:
     - Compliant device: full access
     - Non-compliant device (personal laptop): read-only via OWA
     - Non-UK IP: blocked or additional auth

❌ **Missing**: Formal channel strategy document
❌ **Missing**: Channel switching testing plan
⚠️ **Weak**: Channels defined technically but not from user experience perspective

**Gap Analysis**:
Multiple channels are identified and architecturally defined (OWA, desktop, mobile). Conditional Access policies provide differentiated but consistent security across channels. However, there is no formal channel strategy or evidence of how users will experience switching between channels. For Alpha, the channel identification and technical integration is adequate.

**Readiness Rating**: 🟡 Amber

**Strengths**:
- All email channels identified and architecturally defined
- Conditional Access provides channel-appropriate security
- User survey shows channel demand (65% want mobile)

**Weaknesses**:
- No formal channel strategy document
- No evidence of channel switching user testing
- Experience described technically, not from user perspective

**Recommendations**:

1. **Medium**: Document channel strategy in 1-page summary
   - Timeline: 2 days
   - Owner: Product Manager
   - Evidence to create: Channel strategy showing Outlook Desktop, OWA, Mobile with use cases and access levels

2. **Medium**: Include channel switching scenarios in user testing
   - Timeline: During prototype testing (see Point 1)
   - Owner: User Researcher
   - Evidence to create: Channel switching test results

**Assessment Day Guidance**:
- **Prepare**: Channel diagram showing all access points
- **Show**: C4 diagram highlighting OWA, Desktop, Mobile channels
- **Bring**: Technical Lead to explain Conditional Access channel differentiation
- **Likely Questions**:
  - "What happens when a user starts on desktop and needs to continue on mobile?"
  - "How do you handle users with no smartphone?"

---

### 4. Make the Service Simple to Use

**Status**: 🟡 Partial

**What This Point Means**:
Build a service that's simple, intuitive, and comprehensible so people can succeed the first time they use it. This means using simple language, minimising steps, and following established patterns.

**Why It Matters**:
3,500 users with varying digital skills need to transition seamlessly. Complexity creates support burden and reduces adoption.

**Evidence Required for Alpha**:
- Prototype usability testing conducted
- Design iterations based on user feedback
- Simple language and clear instructions
- Task completion rates in testing

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 361-366)
   - NFR-U-001: "Intuitive for medium proficiency users (policy advisors, administrators)"
   - Standards: Microsoft Fluent Design, responsive mobile, modern browsers supported
   - Onboarding: Microsoft Learn modules, contextual help, quick reference guides

✅ **ARC-001-STKE-v1.0.md** (lines 535-570)
   - Goal G-4: "Achieve 80% user proficiency within 1 month post-migration"
   - Training programme defined: LMS modules, Champions network (50), multiple formats
   - Success metrics: 100% training completion, NPS >70

✅ **ARC-001-REQ-v1.0.md** (lines 95-100)
   - BR-006: "80%+ user proficiency within 1 month" with success criteria

❌ **Missing**: Usability testing results
❌ **Missing**: Design iterations based on feedback
❌ **Missing**: Task completion rates
⚠️ **Weak**: Simplicity defined as requirements/goals but not tested

**Gap Analysis**:
The project defines simplicity requirements and adoption targets but has not conducted usability testing. The reliance on Microsoft's existing Outlook/OWA interface mitigates some risk (users are familiar with Outlook). The training programme and Champions network are well-planned. For Alpha, the requirements and training plan are adequate, but some prototype testing of the migration experience (MFA setup, Intune enrollment) would strengthen the case.

**Readiness Rating**: 🟡 Amber

**Strengths**:
- Clear usability requirements targeting medium-proficiency users
- Comprehensive training programme with multiple formats
- Champions network for peer support

**Weaknesses**:
- No usability testing conducted
- No evidence of iterating based on user feedback on migration experience
- Task completion rates unknown

**Recommendations**:

1. **High**: Test MFA setup and Intune enrollment experience with 5 representative users
   - Timeline: 1 week
   - Owner: User Researcher / Change Manager
   - Evidence to create: Usability test results, task completion rates for MFA/Intune setup

2. **Medium**: Review training materials for plain language and simplicity
   - Timeline: 3 days
   - Owner: Content Designer
   - Evidence to create: Reviewed training materials with readability score

**Assessment Day Guidance**:
- **Prepare**: Training plan summary, quick reference guides samples
- **Show**: Outlook/OWA interface walkthrough, MFA setup journey
- **Bring**: Change Manager to present adoption strategy
- **Likely Questions**:
  - "How will you support users who struggle with MFA?"
  - "What's your approach for users with low digital confidence?"

---

### 5. Make Sure Everyone Can Use the Service

**Status**: 🟡 Partial

**What This Point Means**:
The service must be accessible to everyone who needs to use it, including people with disabilities. This is a legal requirement under the Public Sector Bodies (Websites and Mobile Applications) Accessibility Regulations 2018.

**Why It Matters**:
Approximately 1 in 5 UK adults has a disability. All civil servants must be able to access email regardless of disability or assistive technology use.

**Evidence Required for Alpha**:
- Accessibility considerations documented
- WCAG 2.2 AA compliance planned
- Testing with assistive technology planned
- Full accessibility audit not required at Alpha (but plan needed)

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 367-372)
   - NFR-U-002: "WCAG 2.2 AA compliance (legal requirement under Public Sector Accessibility Regulations 2018)"
   - Features: keyboard navigation, screen reader compatibility (JAWS, NVDA), high contrast mode, adjustable fonts
   - Testing: Pa11y, Axe DevTools (automated), manual keyboard/screen reader testing, user testing with disabled users

✅ **ARC-001-REQ-v1.0.md** (lines 236-241)
   - FR-014: OWA accessibility with WCAG 2.2 AA, screen reader (NVDA) testing

✅ **ARC-001-TRAC-v1.0.md** (lines 242-243)
   - Test cases defined: TC-FR-014-01 (Pa11y automated testing), TC-FR-014-02 (NVDA screen reader testing)
   - 100% test coverage for accessibility requirements

✅ **ARC-000-PRIN-v1.0.md** (lines 214-259)
   - Principle 4: "Accessibility and Inclusion (WCAG 2.2 AA Minimum)" with comprehensive requirements

❌ **Missing**: Accessibility testing results (appropriate for Alpha - testing planned)
❌ **Missing**: Accessibility statement draft
❌ **Missing**: Testing with disabled users
⚠️ **Weak**: Accessibility is specified in requirements but no testing evidence yet

**Gap Analysis**:
Accessibility is well-addressed in requirements and architecture principles. WCAG 2.2 AA is mandated as a legal requirement with specific testing tools (Pa11y, Axe, NVDA) and test cases defined. However, no testing has been conducted - this is appropriate for Alpha where the focus is on planning. The key risk is reliance on Microsoft's OWA accessibility (generally good but must be verified). For Alpha, the detailed planning and requirements are sufficient.

**Readiness Rating**: 🟡 Amber

**Strengths**:
- WCAG 2.2 AA explicitly mandated as legal requirement
- Specific testing tools identified (Pa11y, Axe, NVDA, JAWS)
- Test cases defined with full traceability
- Architecture principle dedicated to accessibility

**Weaknesses**:
- No testing conducted yet (planned for Beta)
- No accessibility statement drafted
- No testing with disabled users

**Recommendations**:

1. **Medium**: Draft accessibility testing plan for pilot phase
   - Timeline: 3 days
   - Owner: Accessibility Specialist / QA Lead
   - Evidence to create: Accessibility test plan with timeline, tools, and participant recruitment

2. **Medium**: Begin accessibility statement template
   - Timeline: 2 days
   - Owner: Content Designer
   - Evidence to create: Draft accessibility statement for the email service

**Assessment Day Guidance**:
- **Prepare**: Accessibility requirements summary, testing plan, OWA accessibility features demo
- **Show**: NFR-U-002 requirements, test cases, Microsoft's accessibility documentation for OWA
- **Bring**: Anyone with accessibility expertise
- **Likely Questions**:
  - "How will you test with assistive technologies?"
  - "What's your plan for users with different access needs?"
  - "How do you handle sensitivity labels with screen readers?"

---

### 6. Have a Multidisciplinary Team

**Status**: 🔴 Not Ready

**What This Point Means**:
Put in place a sustainable multidisciplinary team that can design, build, and operate the service. The team should have all the skills needed to deliver.

**Why It Matters**:
A multidisciplinary team ensures all perspectives are represented in service design and delivery decisions.

**Evidence Required for Alpha**:
- Team composition documented
- Key roles filled: Product Manager, User Researcher, Tech Lead, Designer, Delivery Manager
- Skills audit showing capability coverage
- Team co-located or good remote working practices

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-STKE-v1.0.md** (lines 1070-1092)
   - RACI matrix defines decision authority for: budget, timeline, security, configuration, go/no-go
   - Roles identified: CTO, Finance Director, SIRO, CISO, DPO, Enterprise Architect, Exchange Admin, Change Manager, Project Manager, Service Desk Manager

✅ **ARC-001-SOW-v1.0.md** (vendor requirements)
   - Vendor team requirements: Project Manager (PMP/PRINCE2), Technical Lead (MS-100/101/203), Security Lead (CISSP/CISM)
   - Knowledge transfer requirements defined

❌ **Missing**: Documented internal team composition with named individuals
❌ **Missing**: Skills audit showing capability coverage
❌ **Missing**: Evidence of User Researcher, Service Designer, Content Designer roles
❌ **Missing**: Team structure diagram or team page
❌ **Missing**: Evidence of co-location or remote working practices

**Gap Analysis**:
This is a significant gap. While the RACI matrix shows governance roles and the SOW defines vendor team requirements, there is no documented internal multidisciplinary team. Key GDS roles (User Researcher, Service Designer, Content Designer) are not evidenced. The project appears to be governance/architecture-led rather than multidisciplinary-team-led. This is the most likely point to receive a Red rating at assessment.

**Readiness Rating**: 🔴 Red

**Strengths**:
- Clear governance structure with RACI
- Vendor team requirements well-defined

**Weaknesses**:
- No documented internal multidisciplinary team
- Missing key GDS roles: User Researcher, Service Designer, Content Designer
- No skills audit
- No evidence of team co-location or working practices

**Recommendations**:

1. **Critical**: Document the full project team composition with roles, responsibilities, and named individuals
   - Timeline: 1 week
   - Owner: Delivery Manager / Product Manager
   - Evidence to create: Team page showing all roles filled, skills matrix, team structure diagram

2. **Critical**: Ensure User Researcher and Service Designer roles are filled (or explain approach)
   - Timeline: 2-3 weeks
   - Owner: Product Manager
   - Evidence to create: Named individuals or plan for how user research and service design are covered

3. **High**: Document team ways of working (co-location, ceremonies, communication)
   - Timeline: 1 week
   - Owner: Delivery Manager
   - Evidence to create: Team charter or working agreement

**Assessment Day Guidance**:
- **Prepare**: Team structure diagram, skills matrix, photos/bios of team
- **Show**: How the team works together, decision-making process
- **Bring**: As many team members as possible - panel wants to see the team
- **Likely Questions**:
  - "Who is your user researcher and how do they feed into decisions?"
  - "How does the team make decisions when there are competing priorities?"
  - "Is this team sustainable beyond the migration?"

---

### 7. Use Agile Ways of Working

**Status**: 🔴 Not Ready

**What This Point Means**:
Create the service using agile, iterative user-centred methods. This means working in sprints, iterating based on user feedback, and being able to respond to change.

**Why It Matters**:
Agile working ensures the team can adapt to changing needs, incorporate user feedback quickly, and deliver value incrementally.

**Evidence Required for Alpha**:
- Agile ceremonies established (standups, retros, planning)
- Sprint cadence defined (typically 1-2 weeks)
- User stories and backlog maintained
- Iterative approach to prototyping

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 569-581)
   - Phased delivery approach: Pilot (Month 3), Phase 1-3 (Months 5-9), Stabilization, Decommission
   - This demonstrates incremental delivery but not necessarily agile

✅ **ARC-001-STKE-v1.0.md** (lines 1086-1092)
   - Escalation path defined (Project Manager → Steering Committee → CTO → Permanent Secretary)
   - Weekly steering committee mentioned

❌ **Missing**: Evidence of agile ceremonies (standups, retrospectives, sprint planning)
❌ **Missing**: Sprint cadence or iteration length
❌ **Missing**: User stories or product backlog (ArcKit has requirements, not user stories)
❌ **Missing**: Sprint boards or velocity tracking
❌ **Missing**: Retrospective outputs or actions

**Gap Analysis**:
This is a significant gap. The project uses a phased waterfall-style delivery approach (Pilot → Phase 1 → Phase 2 → Phase 3) rather than agile sprints. Requirements are documented as traditional requirements (BR, FR, NFR) rather than user stories. There is no evidence of agile ceremonies. For an infrastructure migration, a phased approach is defensible, but the team should demonstrate how agile principles are applied within each phase.

**Readiness Rating**: 🔴 Red

**Strengths**:
- Phased delivery approach with pilot validation
- Iterative improvement implied through phased rollout

**Weaknesses**:
- No evidence of agile ceremonies
- No sprint cadence or backlog
- Requirements in traditional format, not user stories
- No retrospective evidence

**Recommendations**:

1. **Critical**: Establish and document agile ceremonies (even lightweight ones)
   - Timeline: 1 week to establish, 2-3 sprints to demonstrate
   - Owner: Delivery Manager
   - Evidence to create: Sprint board (Trello/Jira), ceremony schedule, retrospective outputs

2. **Critical**: Convert key requirements into user stories format
   - Timeline: 1 week
   - Owner: Product Manager / Business Analyst
   - Evidence to create: Product backlog with user stories (run `/arckit:backlog` to generate)

3. **High**: Conduct and document at least 2 retrospectives
   - Timeline: 2-4 weeks (after 2 sprints)
   - Owner: Delivery Manager
   - Evidence to create: Retrospective notes showing actions taken

**Assessment Day Guidance**:
- **Prepare**: Sprint board, ceremony schedule, example retrospective output
- **Show**: How the team plans and delivers work in iterations
- **Bring**: Delivery Manager to explain agile approach
- **Likely Questions**:
  - "What does a typical sprint look like?"
  - "How do you prioritise work in your backlog?"
  - "What did your last retrospective uncover?"
  - "How do you respond when things don't go to plan?"

---

### 8. Iterate and Improve Frequently

**Status**: 🔴 Not Ready

**What This Point Means**:
Make sure you have the capacity, people, and technical infrastructure to iterate and improve the service frequently. This means releasing changes regularly and learning from them.

**Why It Matters**:
Services improve through iteration. The team should demonstrate that they're learning and adapting based on what they discover.

**Evidence Required for Alpha**:
- Prototype iterations documented
- Changes based on user feedback
- Multiple design options explored
- Learning log showing insights and pivots

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (revision history, line 28-29)
   - Document has been through 2 versions (v1.0 and v1.1), showing some iteration
   - Requirements updated to align with new template format

✅ **ARC-001-STKE-v1.0.md** (lines 843-864)
   - Conflict analysis showing how competing stakeholder needs were resolved
   - This demonstrates design thinking and trade-off resolution

❌ **Missing**: Prototype iteration log
❌ **Missing**: Design options explored and rationale for choices
❌ **Missing**: User feedback leading to changes
❌ **Missing**: Learning log or decision journal

**Gap Analysis**:
This is a significant gap for Alpha. There is no evidence of prototype iterations, design options explored, or changes made based on user feedback. The ArcKit artifacts show document versioning but not service design iteration. The stakeholder conflict analysis demonstrates some decision-making but not user-driven iteration. A learning log or Architecture Decision Records (ADRs) would strengthen this point significantly.

**Readiness Rating**: 🔴 Red

**Strengths**:
- Document iterations showing some evolution
- Stakeholder conflict analysis demonstrates trade-off thinking

**Weaknesses**:
- No prototype iterations documented
- No design options explored
- No user feedback driving changes
- No learning log

**Recommendations**:

1. **Critical**: Create a learning log / decision journal documenting key decisions and what influenced them
   - Timeline: 1 week (retrospective creation)
   - Owner: Product Manager
   - Evidence to create: Learning log with 10+ entries showing decisions, rationale, what was learned

2. **Critical**: Document Architecture Decision Records (ADRs) for key technology choices
   - Timeline: 1 week
   - Owner: Enterprise Architect
   - Evidence to create: ADRs via `/arckit:adr` covering M365 selection, hybrid migration approach, Conditional Access design

3. **High**: Conduct and document at least one prototype iteration cycle
   - Timeline: 2 weeks
   - Owner: User Researcher / Service Designer
   - Evidence to create: Before/after showing how a design changed based on user feedback

**Assessment Day Guidance**:
- **Prepare**: Learning log, ADRs, any evidence of design evolution
- **Show**: How the team has adapted their approach based on what they've learned
- **Bring**: Product Manager and Technical Lead
- **Likely Questions**:
  - "What have you learned so far that has changed your approach?"
  - "Can you give an example of something you tried that didn't work?"
  - "How has user research influenced your design?"

---

### 9. Create a Secure Service Which Protects Users' Privacy

**Status**: 🟢 Ready

**What This Point Means**:
Evaluate what data and information the service will be collecting, storing, and providing. Understand and address security threats. Put appropriate legal, privacy, and security measures in place.

**Why It Matters**:
The service handles OFFICIAL and OFFICIAL-SENSITIVE government data. A security breach could have ministerial-level consequences.

**Evidence Required for Alpha**:
- Threat model created (or planned)
- Security risks identified and assessed
- GDPR compliance approach defined
- Data protection impact assessment approach defined
- Privacy considerations documented

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 303-335)
   - 5 security NFRs (NFR-SEC-001 to NFR-SEC-005) all marked CRITICAL NON-NEGOTIABLE
   - MFA enforcement, RBAC with PIM, TLS 1.3 + AES-256 encryption, secrets management, vulnerability management

✅ **ARC-001-REQ-v1.0.md** (lines 337-357)
   - 3 compliance NFRs (NFR-C-001 to NFR-C-003) all marked CRITICAL NON-NEGOTIABLE
   - UK GDPR, Government Security Classifications, Public Records Act

✅ **ARC-001-REQ-v1.0.md** (lines 143-216)
   - Security functional requirements: FR-004 (Conditional Access/Zero Trust), FR-005 (Sensitivity Labels), FR-006 (DLP), FR-007 (Defender for O365), FR-011 (Audit Log)

✅ **ARC-000-PRIN-v1.0.md** (lines 140-211)
   - Principle 3: "Security by Design (NON-NEGOTIABLE)" with comprehensive NCSC Cloud Security Principles mapping, Zero Trust pillars, mandatory controls checklist

✅ **ARC-001-STKE-v1.0.md** (lines 173-232)
   - SIRO driver (SD-3) and CISO driver (SD-4) with detailed security context
   - Goal G-3: SIRO sign-off with 14/14 NCSC principles compliance target
   - Goal G-5: Zero security incidents during migration

✅ **ARC-001-DIAG-002-v1.0.md** (lines 41-100)
   - Sequence diagram showing Zero Trust authentication flow: MFA, Conditional Access evaluation, legacy auth blocking

✅ **ARC-001-REQ-v1.0.md** (lines 555-565)
   - 8 risks identified including data breach during migration (R-006), DLP misconfiguration (R-008)

✅ **ARC-001-TRAC-v1.0.md** (lines 136-152)
   - 18 security test cases defined with 100% coverage

**Gap Analysis**:
This is the project's strongest point. Security evidence is exceptional, with 11 NON-NEGOTIABLE security requirements, NCSC Cloud Security Principles mapping, Zero Trust architecture with sequence diagrams, SIRO/CISO stakeholder engagement, and comprehensive risk identification. For Alpha, this exceeds expectations. The only gap is that the threat model and penetration test are planned but not yet completed - this is appropriate timing.

**Readiness Rating**: 🟢 Green

**Strengths**:
- 11 NON-NEGOTIABLE security requirements with specific controls
- NCSC Cloud Security Principles fully mapped
- Zero Trust architecture with authentication sequence diagrams
- SIRO and CISO actively engaged with clear sign-off process
- 18 security test cases with 100% coverage

**Weaknesses**:
- Threat model not yet completed (planned for Month 3)
- DPIA not yet documented (planned)

**Recommendations**:

1. **Medium**: Create threat model document (strengthen already-strong evidence)
   - Timeline: 2 weeks
   - Owner: Security Architect / CISO
   - Evidence to create: Threat model using NCSC methodology

**Assessment Day Guidance**:
- **Prepare**: Security architecture overview, NCSC mapping, risk register
- **Show**: Sequence diagram for Zero Trust auth, sensitivity labels demo
- **Bring**: Security Lead / CISO representative
- **Likely Questions**:
  - "How do you handle OFFICIAL-SENSITIVE data?"
  - "What's your approach to threat modelling?"
  - "How do you respond to security incidents?"

---

### 10. Define What Success Looks Like and Publish Performance Data

**Status**: 🟢 Ready

**What This Point Means**:
Work out what success looks like for your service and identify metrics which will tell you what's working and what can be improved. Collect and use performance data from all channels.

**Why It Matters**:
Without defined success metrics, you cannot know whether the service is meeting user needs or delivering value.

**Evidence Required for Alpha**:
- Success metrics defined (user satisfaction, completion rates, cost per transaction)
- Baseline measurements identified
- Data collection approach planned
- KPIs aligned to user needs

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 514-541)
   - Business Metrics: TCO reduction (£2M → £1.2M), availability (98.5% → 99.9%), NPS (45 → 70), IT effort (40 → 15 hrs/week), mobile adoption (20% → 70%)
   - Technical Metrics: Migration success (99%), email latency (<30s p95), availability (99.9%), security incidents (50% reduction), data loss (zero)
   - Adoption Metrics: Training completion (100%), OWA users (30%), mobile users (70%), service desk tickets (<100/week)

✅ **ARC-001-STKE-v1.0.md** (lines 427-817)
   - 6 goals with detailed success metrics, baselines, targets, measurement methods
   - 4 outcomes with leading and lagging indicators
   - Measurement frequency defined (monthly, quarterly, annually)

✅ **ARC-001-REQ-v1.0.md** (lines 69-72)
   - BR-002: "TCO analysis shows £800K savings, monthly cost tracking"

**Gap Analysis**:
This is a strong point. Comprehensive success metrics are defined across business, technical, and adoption categories with clear baselines, targets, and measurement methods. The stakeholder analysis links metrics to goals and outcomes. For Alpha, this is excellent. The only gap is that data collection isn't yet active - but that's appropriate for Alpha.

**Readiness Rating**: 🟢 Green

**Strengths**:
- Comprehensive metrics across 3 categories with baselines and targets
- Goals-to-outcomes traceability with leading/lagging indicators
- Clear measurement methods (M365 dashboards, surveys, ServiceNow)

**Weaknesses**:
- Data collection not yet active (appropriate for Alpha)
- No published performance dashboard yet

**Recommendations**:

1. **Medium**: Map the 4 mandatory GDS KPIs (cost per transaction, user satisfaction, completion rate, digital take-up) to existing metrics
   - Timeline: 2 days
   - Owner: Product Manager
   - Evidence to create: GDS KPI mapping document

**Assessment Day Guidance**:
- **Prepare**: Metrics summary table with baselines, targets, measurement methods
- **Show**: Goals-to-outcomes traceability from stakeholder analysis
- **Bring**: Product Manager
- **Likely Questions**:
  - "How will you know if the migration is successful?"
  - "What are your four mandatory KPIs?"
  - "When will you start publishing performance data?"

---

### 11. Choose the Right Tools and Technology

**Status**: 🟢 Ready

**What This Point Means**:
Choose tools and technology that let you create a good service in a cost-effective way. Minimise the cost of changing direction in future.

**Why It Matters**:
Technology choices affect service quality, cost, and sustainability. The right choices enable; wrong choices constrain.

**Evidence Required for Alpha**:
- Technology options explored
- Build vs buy analysis completed
- Technology spikes/proof of concepts conducted
- Technology choices justified against requirements
- Cost analysis for technology options

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 39-50)
   - Clear rationale for M365: TCoP Point 3 (cloud-first), existing M365 E5 licenses, Exchange 2016 end-of-support
   - Cost analysis: £2.95M/year → £2.15M/year (£800K savings)

✅ **ARC-001-EVAL-v1.0.md** (lines 37-46)
   - Formal vendor evaluation framework with 100-point scoring
   - Category 1: Migration Methodology (35 points) including tooling evaluation
   - Architecture Principle Alignment bonus (+3 points)

✅ **ARC-001-SOW-v1.0.md**
   - Formal procurement via RFP-CAB-2025-001
   - Detailed requirements for vendor technology approach
   - Budget breakdown showing technology cost allocation

✅ **ARC-001-DIAG-001-v1.0.md**
   - C4 Container diagram showing technology components with maturity scores (Wardley evolution)
   - Components range from Commodity (0.90-0.95) to Product (0.68-0.75) maturity

✅ **ARC-000-PRIN-v1.0.md** (lines 830-846)
   - Technology Code of Practice mapping showing all 10 TCoP points addressed

**Gap Analysis**:
Technology choice is exceptionally well-justified. M365 E5 was selected based on existing licensing, TCoP compliance, NCSC security principles, and cost analysis. A formal vendor evaluation framework exists for selecting the migration partner. Architecture diagrams include Wardley evolution scores showing technology maturity. For Alpha, this exceeds expectations.

**Readiness Rating**: 🟢 Green

**Strengths**:
- Technology justified against requirements, TCoP, and cost analysis
- Formal vendor evaluation framework (100 points)
- Architecture diagrams with technology maturity scores
- Procurement process documented via SOW

**Weaknesses**:
- No formal technology spike or proof of concept documented (M365 is established platform)

**Recommendations**:

None critical. Consider documenting pilot migration results as technology validation evidence for Beta assessment.

**Assessment Day Guidance**:
- **Prepare**: Technology rationale summary, cost comparison, TCoP mapping
- **Show**: C4 diagram with technology components, evaluation criteria
- **Bring**: Technical Lead / Enterprise Architect
- **Likely Questions**:
  - "Why did you choose M365 over alternatives?"
  - "How does your technology choice support TCoP?"
  - "What's your plan for managing vendor lock-in?"

---

### 12. Make New Source Code Open

**Status**: 🔴 Not Ready

**What This Point Means**:
Make all new source code open and reusable, and publish it under appropriate licences. Or if you can't do this, explain why.

**Why It Matters**:
Open source enables code reuse across government, reduces costs, and improves code quality through external review.

**Evidence Required for Alpha**:
- Open source approach decided
- Security and IP considerations addressed
- Code repository approach defined

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-000-PRIN-v1.0.md** (line 840)
   - TCoP mapping: "TCoP 5: Use open source → Principle 10: Interoperability & Open Standards"

❌ **Missing**: Open source strategy or approach document
❌ **Missing**: Decision on what code/configuration can be made open
❌ **Missing**: Public code repository or plan for one
❌ **Missing**: Rationale if code cannot be open (e.g., security configuration)

**Gap Analysis**:
This is a significant gap. The project is an M365 SaaS migration with limited custom code - most "code" is configuration (Conditional Access policies, DLP rules, PowerShell scripts). There is no documented decision about making configuration-as-code open, nor any explanation of why code might not be shareable. For Alpha, the team needs at least a clear position on open source, even if it's "most configuration contains security-sensitive settings and cannot be published."

**Readiness Rating**: 🔴 Red

**Strengths**:
- TCoP open source principle acknowledged

**Weaknesses**:
- No open source strategy
- No decision on what can be shared
- No repository approach

**Recommendations**:

1. **Critical**: Document open source approach for M365 migration
   - Timeline: 3 days
   - Owner: Technical Lead / Enterprise Architect
   - Evidence to create: Open source position paper explaining: (a) what configuration-as-code exists, (b) what can be published (sanitised PowerShell scripts, architecture documentation), (c) what cannot (security configuration) and why, (d) plan for sharing with other government departments

2. **High**: Publish non-sensitive migration scripts/documentation on GitHub
   - Timeline: 1-2 weeks
   - Owner: Exchange Administrator
   - Evidence to create: Public GitHub repository with migration documentation templates, PowerShell validation scripts (sanitised)

**Assessment Day Guidance**:
- **Prepare**: Open source position paper, examples of what will be shared
- **Show**: Plan for sharing useful assets with other government departments
- **Bring**: Technical Lead
- **Likely Questions**:
  - "What code/configuration will you make open?"
  - "Why can't certain things be open? What's the security justification?"
  - "How will other departments benefit from your work?"

---

### 13. Use and Contribute to Open Standards, Common Components and Patterns

**Status**: 🟢 Ready

**What This Point Means**:
Build on open standards and common components and patterns from inside and outside government. If you develop new patterns or tools, share them publicly.

**Why It Matters**:
Open standards ensure interoperability, avoid vendor lock-in, and enable cross-government integration.

**Evidence Required for Alpha**:
- Common components identified (GOV.UK Notify, Pay, etc.)
- API standards considered (RESTful, OpenAPI)
- Data standards identified
- GOV.UK Design System usage planned (if citizen-facing)

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 397-412)
   - NFR-I-001: Open standards compliance (SMTP, IMAP, OAuth 2.0, Microsoft Graph API)
   - NFR-I-002: Cross-government integration (SMTP/TLS to *.gov.uk, Exchange Federation, Azure AD B2B)
   - NFR-I-003: Data portability (PST, EML, MSG export in open formats)

✅ **ARC-000-PRIN-v1.0.md** (lines 436-473)
   - Principle 10: Comprehensive open standards requirements
   - Compulsory standards: ODF 1.2, SMTP, iCalendar, vCard, HTML5, OAuth 2.0/OIDC, SAML 2.0
   - Cross-government integration: GOV.UK Verify/One Login, GDI alignment, GDS API standards

✅ **ARC-001-TRAC-v1.0.md** (lines 170-174)
   - 100% test coverage for interoperability requirements

**Gap Analysis**:
Open standards are well-addressed. The project mandates SMTP, OAuth 2.0, Graph API, and data portability in open formats. Cross-government email integration is defined. Architecture principles comprehensively list compulsory open standards. GOV.UK Design System is not applicable (this is an internal M365 service, not a citizen-facing web service). For Alpha, this is strong.

**Readiness Rating**: 🟢 Green

**Strengths**:
- Comprehensive open standards mandated (SMTP, OAuth 2.0, Graph API)
- Cross-government interoperability defined
- Data portability in open formats (PST, EML)
- Architecture principles align with Open Standards Board requirements

**Weaknesses**:
- GOV.UK Design System not applicable (internal service)
- No contribution back to common patterns yet (appropriate for Alpha)

**Recommendations**:

None critical. Consider documenting how the M365 migration approach could be reused by other departments.

**Assessment Day Guidance**:
- **Prepare**: Open standards compliance table, cross-government integration plan
- **Show**: Architecture principles open standards section
- **Bring**: Technical Lead
- **Likely Questions**:
  - "What open standards are you using?"
  - "How do you ensure data portability and avoid lock-in?"
  - "How does your service integrate with other government systems?"

---

### 14. Operate a Reliable Service

**Status**: 🟢 Ready

**What This Point Means**:
Minimise service downtime and have a plan to deal with it when it does happen. Meet the agreed service level and support users.

**Why It Matters**:
Email is a critical business service. Unreliable email disrupts government operations and affects public service delivery.

**Evidence Required for Alpha**:
- Reliability requirements defined
- Uptime targets set
- High-level resilience approach planned

**Evidence Found in ArcKit Artifacts**:

✅ **ARC-001-REQ-v1.0.md** (lines 275-289)
   - NFR-A-001: 99.9% uptime SLA, max 43 min unplanned downtime/month
   - NFR-A-002: RPO 15 min, RTO 4 hr, automatic UK West failover <15 min
   - NFR-A-003: Fault tolerance with circuit breaker, retry, timeout, bulkhead patterns

✅ **ARC-001-REQ-v1.0.md** (lines 388-392)
   - NFR-M-003: Operational runbooks for incident response, rollback procedures

✅ **ARC-001-STKE-v1.0.md** (lines 610-643)
   - Goal G-6: "Maintain 99.9% Email Availability" with baseline (98.5%) and target (99.9%)
   - Measurement via M365 Service Health dashboard, synthetic monitoring

✅ **ARC-001-TRAC-v1.0.md** (lines 120-126)
   - Test cases for availability (TC-NFR-A-001-01), DR (TC-NFR-A-002-01), fault tolerance (TC-NFR-A-003-01)
   - 3 DR test cases defined

✅ **ARC-001-REQ-v1.0.md** (lines 555-565)
   - Risk register with 8 risks including mitigation strategies

**Gap Analysis**:
Service reliability is well-planned. Clear SLA (99.9%), RPO/RTO targets, fault tolerance patterns, and DR strategy are defined. The improvement from 98.5% (current) to 99.9% (target) is documented. Microsoft's SLA underpins the reliability guarantee. For Alpha, the detailed requirements and testing plan are more than sufficient.

**Readiness Rating**: 🟢 Green

**Strengths**:
- 99.9% SLA with measurable targets
- RPO/RTO defined (15 min/4 hr)
- Fault tolerance patterns specified
- Improvement from current 98.5% baseline documented

**Weaknesses**:
- Runbooks and incident response not yet created (planned for pilot)
- DR testing not yet performed (planned for pilot)

**Recommendations**:

None critical. Ensure runbooks are created before Beta assessment.

**Assessment Day Guidance**:
- **Prepare**: Reliability requirements summary, SLA targets, DR approach
- **Show**: Architecture diagram highlighting UK South/UK West redundancy
- **Bring**: Technical Lead
- **Likely Questions**:
  - "What happens when things go wrong?"
  - "How quickly can you recover from a failure?"
  - "What's your approach to monitoring and alerting?"

---

## Evidence Inventory

**Complete Traceability**: Service Standard Point → ArcKit Artifacts

| Service Standard Point | ArcKit Artifacts | Status | Critical Gaps |
|------------------------|------------------|--------|---------------|
| 1. Understand users | STKE, REQ | 🟡 Partial | Qualitative user research sessions |
| 2. Solve whole problem | REQ, STKE, DIAG-001 | 🟡 Partial | User journey maps |
| 3. Joined up experience | REQ, DIAG-001, STKE | 🟡 Partial | Channel strategy document |
| 4. Simple to use | REQ, STKE | 🟡 Partial | Usability testing results |
| 5. Everyone can use | REQ, PRIN, TRAC | 🟡 Partial | Accessibility test plan |
| 6. Multidisciplinary team | STKE, SOW | 🔴 Not Ready | Team composition document |
| 7. Agile ways of working | REQ | 🔴 Not Ready | Sprint board, ceremonies evidence |
| 8. Iterate frequently | REQ revisions | 🔴 Not Ready | Learning log, ADRs |
| 9. Secure and private | REQ, PRIN, STKE, DIAG-002, TRAC | 🟢 Ready | None |
| 10. Success metrics | REQ, STKE | 🟢 Ready | GDS KPI mapping |
| 11. Right tools | REQ, EVAL, SOW, DIAG-001, PRIN | 🟢 Ready | None |
| 12. Open source | PRIN (TCoP mapping) | 🔴 Not Ready | Open source position paper |
| 13. Open standards | REQ, PRIN, TRAC | 🟢 Ready | None |
| 14. Reliable service | REQ, STKE, TRAC | 🟢 Ready | None |

**Summary**:
- ✅ Strong evidence: Points 9, 10, 11, 13, 14
- ⚠️ Adequate but needs strengthening: Points 1, 2, 3, 4, 5
- ❌ Critical gaps: Points 6, 7, 8, 12

---

## Assessment Preparation Checklist

### Critical Actions (Complete within 2 weeks)

Priority: Complete these before booking assessment - they address Red ratings

- [ ] **Document multidisciplinary team composition**
  - Point: 6 (Multidisciplinary team)
  - Timeline: 5 days
  - Owner: Delivery Manager / Product Manager
  - Outcome: Team structure document with roles, named individuals, skills matrix

- [ ] **Document open source approach for M365 migration**
  - Point: 12 (Open source)
  - Timeline: 3 days
  - Owner: Technical Lead / Enterprise Architect
  - Outcome: Open source position paper explaining what can/cannot be shared and why

- [ ] **Create learning log with key decisions and rationale**
  - Point: 8 (Iterate frequently)
  - Timeline: 5 days
  - Owner: Product Manager
  - Outcome: Learning log with 10+ entries showing decisions and learnings

- [ ] **Establish agile ceremonies and document sprint cadence**
  - Point: 7 (Agile working)
  - Timeline: 5 days to establish, then ongoing
  - Owner: Delivery Manager
  - Outcome: Ceremony schedule, sprint board, initial backlog

### High Priority Actions (Complete within 4 weeks)

Priority: Should complete to strengthen Amber points to Green

- [ ] **Conduct 6-8 qualitative user research sessions**
  - Point: 1 (Understand users)
  - Timeline: 2-3 weeks
  - Owner: User Researcher
  - Outcome: User research report, personas, user needs statements

- [ ] **Generate product backlog from requirements**
  - Point: 7 (Agile working)
  - Timeline: 1 week
  - Owner: Product Manager (run `/arckit:backlog`)
  - Outcome: Prioritised user stories in backlog format

- [ ] **Create Architecture Decision Records (ADRs)**
  - Point: 8 (Iterate frequently)
  - Timeline: 1 week
  - Owner: Enterprise Architect (run `/arckit:adr`)
  - Outcome: ADRs documenting key technology and design decisions

- [ ] **Test MFA/Intune enrollment experience with users**
  - Point: 4 (Simple to use)
  - Timeline: 1 week
  - Owner: User Researcher / Change Manager
  - Outcome: Usability test results, task completion rates

- [ ] **Create 2-3 user journey maps**
  - Point: 2 (Solve whole problem)
  - Timeline: 1 week
  - Owner: Service Designer / User Researcher
  - Outcome: Journey maps for daily email, migration experience, mobile setup

- [ ] **Conduct and document 2+ retrospectives**
  - Point: 7, 8 (Agile, Iterate)
  - Timeline: 4 weeks (after 2 sprints)
  - Owner: Delivery Manager
  - Outcome: Retrospective notes with actions taken

### Medium Priority Actions (Nice to Have)

Priority: Strengthens overall case but not blocking

- [ ] **Map 4 mandatory GDS KPIs to existing metrics**
  - Point: 10 (Success metrics)
  - Timeline: 2 days
  - Owner: Product Manager
  - Outcome: GDS KPI mapping document

- [ ] **Draft accessibility test plan for pilot**
  - Point: 5 (Everyone can use)
  - Timeline: 3 days
  - Owner: Accessibility Specialist / QA Lead
  - Outcome: Test plan with timeline, tools, participants

- [ ] **Document channel strategy**
  - Point: 3 (Joined up experience)
  - Timeline: 2 days
  - Owner: Product Manager
  - Outcome: 1-page channel strategy (desktop, OWA, mobile)

- [ ] **Create threat model document**
  - Point: 9 (Secure and private)
  - Timeline: 2 weeks
  - Owner: Security Architect
  - Outcome: Threat model using NCSC methodology

- [ ] **Publish sanitised migration scripts on GitHub**
  - Point: 12 (Open source)
  - Timeline: 1-2 weeks
  - Owner: Exchange Administrator
  - Outcome: Public GitHub repository with reusable migration assets

---

## Assessment Day Preparation

### Timeline and Booking

**Current Readiness**:
Not ready to book. 4 Red-rated points require remediation before booking. Recommend completing critical actions (2 weeks) and at least 2 sprints of agile evidence (4 weeks) before booking.

**Recommended Booking Timeline**:
- Complete critical actions: 2 weeks
- Run 2 sprints for agile evidence: 4 weeks
- Complete high priority actions: 2-3 additional weeks (parallel)
- Buffer for preparation: 1 week
- **Ready to book after**: Mid-April 2026 (approximately 10 weeks)

**How to Book**:
1. Contact GDS Central Digital & Data Office assessment team
2. Book 5 weeks in advance minimum
3. Assessments typically on Tuesday, Wednesday, or Thursday
4. Duration: 4 hours
5. Provide: Service name ("Cabinet Office Exchange Online Migration"), department ("Cabinet Office"), phase ("Alpha"), preferred dates

### Documentation to Share with Panel

**Send 1 week before assessment**:

Required documentation:
- [ ] Project overview (1-2 pages) - Use Executive Summary from ARC-001-REQ-v1.0.md
- [ ] User research repository or summary - From user research sessions (to be conducted)
- [ ] Service architecture diagrams - `ARC-001-DIAG-001-v1.0.md` (C4 Container) and `ARC-001-DIAG-002-v1.0.md` (Sequence)
- [ ] Prototype/demo environment URL - OWA test environment (if available)

Recommended documentation:
- [ ] `ARC-001-STKE-v1.0.md` - Stakeholder analysis and user needs
- [ ] `ARC-001-REQ-v1.0.md` - Requirements (highlight user stories/NFRs)
- [ ] `ARC-001-TRAC-v1.0.md` - Traceability showing test coverage
- [ ] `ARC-001-PRCO-v1.0.md` - Principles compliance assessment
- [ ] Team composition document (to be created)
- [ ] Learning log (to be created)

Optional supplementary:
- [ ] `ARC-001-SOW-v1.0.md` - Procurement approach
- [ ] `ARC-001-EVAL-v1.0.md` - Technology evaluation criteria
- [ ] Training materials samples
- [ ] Security architecture overview

### Who Should Attend

**Core Team** (required):
- ✅ **Product Manager / Service Owner** - Overall service vision and decisions
- ✅ **User Researcher** - User needs, research findings (ensure this role is filled)
- ✅ **Technical Lead / Enterprise Architect** - Technology choices, architecture
- ✅ **Delivery Manager** - Agile practices, team dynamics

**Alpha-Specific Additions**:
- ✅ **Lead Designer / Service Designer** - Migration experience design
- ✅ **Business Analyst** - Requirements, user stories
- ✅ **Change Manager** - Adoption strategy, training approach

**Optional Attendees**:
- CTO (Executive Sponsor) - for context, may not stay whole time
- CISO or Security Lead - for security questions
- Exchange Administrator - for technical deep dives

### Show and Tell Structure

**4-Hour Assessment Timeline**:

**0:00-0:15 - Introductions and Context**
- Team introductions (all members present their role and experience)
- Service overview: "Migration of 3,500 Cabinet Office mailboxes from Exchange 2016 to Exchange Online"
- Context: TCoP compliance, cost savings, hardware end-of-support deadline

**0:15-1:00 - User Research and Needs (Points 1, 2, 3, 4)**
- User Researcher presents:
  - Survey findings (n=350) and qualitative research results
  - User personas and needs statements
  - User journey maps
  - How user needs informed migration approach (phased, training, support)
- Change Manager presents:
  - Adoption strategy, Champions network, training programme
  - Prototype testing results (MFA/Intune enrollment)
- Be ready to discuss: diversity of participants, accessibility considerations

**1:00-1:45 - Service Demonstration (Points 2, 3, 4, 5)**
- Show the M365 experience:
  - OWA login with MFA (live demo)
  - Desktop Outlook with Autodiscover
  - Mobile Outlook with Intune enrollment
  - Sensitivity labels and DLP in action
- Accessibility features walkthrough
- Channel switching demonstration

**1:45-2:30 - Technical Architecture and Security (Points 9, 11, 12, 13, 14)**
- Technical Lead / Enterprise Architect presents:
  - C4 Container diagram - architecture overview
  - Sequence diagram - Zero Trust authentication
  - Technology choice rationale (M365 E5, UK data residency)
  - Security: NCSC mapping, Conditional Access, DLP, sensitivity labels
  - Open standards: SMTP, OAuth 2.0, Graph API, data portability
  - Open source position
  - Reliability: 99.9% SLA, RPO/RTO, DR strategy
- Use actual ArcKit diagrams on screen

**2:30-3:00 - Team and Ways of Working (Points 6, 7, 8, 10)**
- Delivery Manager presents:
  - Team composition and skills
  - Sprint cadence and ceremonies
  - Retrospective examples
  - Backlog management approach
- Product Manager presents:
  - Success metrics and KPIs
  - Learning log highlights
  - How decisions are made
- Show: Sprint board, backlog, retrospective outputs

**3:00-3:45 - Open Q&A**
- Panel asks questions across all 14 points
- Team responds with evidence from ArcKit artifacts
- Reference specific documents and line numbers

**3:45-4:00 - Panel Deliberation**
- Team steps out for panel discussion

### Tips for Success

**Do**:
- ✅ Show real work, not polished presentations (max 10 slides if any)
- ✅ Have people who did the work present it
- ✅ Be honest: "This is an internal migration, not a citizen-facing service"
- ✅ Explain how GDS principles apply to infrastructure migration
- ✅ Demonstrate strong security and compliance (your biggest strength)
- ✅ Show enthusiasm for user adoption and reducing disruption
- ✅ Reference ArcKit artifacts by name as evidence

**Don't**:
- ❌ Over-prepare presentations - panel wants to see real artifacts
- ❌ Hide the fact that this is primarily an IT migration
- ❌ Use heavy technical jargon without explanation
- ❌ Let senior leaders dominate - panel wants to hear from doers
- ❌ Argue with panel feedback
- ❌ Rush through security (it's your strongest area)

**Materials to Have Ready**:
- OWA demo environment with test accounts and MFA configured
- Laptops for team members to show their work
- ArcKit artifacts bookmarked in browser tabs
- C4 and sequence diagrams on screen (or printed large)
- Sprint board accessible (Trello/Jira)
- Backup screenshots/video if demo breaks

---

## After the Assessment

### If You Pass (Green)

**Immediate Actions**:
- [ ] Celebrate with the team
- [ ] Share assessment report with CTO, SIRO, steering committee
- [ ] Plan for Beta phase assessment (after pilot completion)
- [ ] Book Beta assessment (target: post-pilot, approximately Month 4-5)

**Continuous Improvement**:
- [ ] Continue user research throughout pilot and phases
- [ ] Update ArcKit artifacts as service evolves
- [ ] Maintain GDS Service Standard compliance
- [ ] Re-run `/arckit:service-assessment PHASE=beta` before Beta assessment

### If You Get Amber

**Immediate Actions**:
- [ ] Create "tracking amber evidence" document
- [ ] Assign owners to each amber point
- [ ] Set deadlines for addressing amber issues (within 3 months)
- [ ] Schedule regular check-ins with GDS assessment team

### If You Fail (Red)

**Immediate Actions**:
- [ ] Review assessment report carefully with team
- [ ] Identify root causes of red ratings
- [ ] Create action plan to address each red point
- [ ] Re-run `/arckit:service-assessment PHASE=alpha` weekly to track progress
- [ ] Book reassessment once red issues resolved (typically 3-6 months)

---

## Next Steps

### This Week

**Immediate actions** (within 7 days):
1. Document multidisciplinary team composition (Point 6) - most critical gap
2. Create learning log retrospectively documenting key decisions (Point 8)
3. Write open source position paper (Point 12)

**Quick wins** (can complete in 1-2 days):
- Map 4 mandatory GDS KPIs to existing metrics (Point 10)
- Document channel strategy on 1 page (Point 3)

### Next 2 Weeks

**Priority actions**:
1. Establish agile ceremonies and sprint cadence (Point 7)
2. Generate product backlog from requirements (`/arckit:backlog`) (Point 7)
3. Create Architecture Decision Records (`/arckit:adr`) (Point 8)
4. Begin user research recruitment (Point 1)

### Next 4 Weeks

**Strengthening actions**:
1. Complete 6-8 user research sessions and create personas (Point 1)
2. Create user journey maps (Point 2)
3. Test MFA/Intune enrollment usability (Point 4)
4. Complete 2 retrospectives to demonstrate agile practices (Point 7, 8)
5. Draft accessibility test plan (Point 5)

### Continuous Improvement

**Weekly**:
- [ ] Re-run `/arckit:service-assessment PHASE=alpha` to track progress
- [ ] Update this report as evidence is gathered
- [ ] Review checklist and mark completed items
- [ ] Sprint planning includes Service Standard prep tasks

**Fortnightly**:
- [ ] Team review of assessment readiness
- [ ] Practice show and tell with colleagues (mock assessment)
- [ ] Gather feedback on presentation approach

**Before Booking**:
- [ ] All 4 critical actions complete (Points 6, 7, 8, 12)
- [ ] At least 10/14 points rated Green or Amber with no Red
- [ ] Team confident and prepared
- [ ] Documentation ready to share
- [ ] Demo environment tested and working

---

## Resources

### GDS Service Standard Resources

**Official Guidance**:
- [Service Standard](https://www.gov.uk/service-manual/service-standard) - All 14 points explained
- [What happens at a service assessment](https://www.gov.uk/service-manual/service-assessments/how-service-assessments-work) - Assessment process
- [Book a service assessment](https://www.gov.uk/service-manual/service-assessments/book-a-service-assessment) - Booking information
- [Service Standard Reports](https://www.gov.uk/service-standard-reports) - Browse 450+ published assessment reports

**Phase-Specific Guidance**:
- [Alpha phase](https://www.gov.uk/service-manual/agile-delivery/how-the-alpha-phase-works) - What to do in alpha
- [Beta phase](https://www.gov.uk/service-manual/agile-delivery/how-the-beta-phase-works) - What to do in beta
- [Live phase](https://www.gov.uk/service-manual/agile-delivery/how-the-live-phase-works) - What to do when live

### Related ArcKit Commands

**Complementary Analysis**:
- `/arckit:analyze` - Comprehensive governance quality analysis
- `/arckit:traceability` - Requirements traceability matrix
- `/arckit:principles-compliance` - Architecture principles compliance (already generated: ARC-001-PRCO-v1.0.md)

**Generate Missing Evidence**:
- `/arckit:backlog` - Generate product backlog with user stories (addresses Point 7)
- `/arckit:adr` - Document architectural decisions (addresses Point 8)
- `/arckit:tcop` - Technology Code of Practice assessment (strengthens Points 11, 13)
- `/arckit:secure` - Secure by Design assessment (strengthens Point 9)
- `/arckit:data-model` - Data model with GDPR compliance (strengthens Point 9)
- `/arckit:diagram` - Additional architecture diagrams

## External References

| Document | Type | Source | Key Extractions | Path |
|----------|------|--------|-----------------|------|
| *None provided* | — | — | — | — |

---

**Generated by**: ArcKit `/arckit.service-assessment` command
**Generated on**: 2026-02-07
**ArcKit Version**: 2.1.6
**Project**: Exchange Online Migration to Microsoft 365 (Project 001)
**Model**: Claude Opus 4.6

**Next Actions**:
1. Review this report with your team
2. Prioritize critical actions in sprint planning
3. Re-run `/arckit:service-assessment PHASE=alpha` weekly to track progress
4. Use checklist to track completion of preparation tasks

---

*Good luck with your assessment! Remember: assessments are conversations about your service, not exams. Show your work, explain your thinking, and be open to feedback. The panel wants you to succeed.*
