# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Overview

This is an **ArcKit architecture project** for a Microsoft 365 GCC-H (Government Community Cloud - High) migration. ArcKit is an Enterprise Architecture Governance Toolkit that provides 40 slash commands to generate architecture artifacts through AI-assisted workflows.

## Using ArcKit Commands

Run slash commands directly in Claude Code to generate architecture documents:

```bash
# Foundation
/arckit.principles Create enterprise architecture principles
/arckit.stakeholders Analyze stakeholder drivers for M365 migration

# Business Case
/arckit.risk Create risk register following Orange Book
/arckit.sobc Create Strategic Outline Business Case (Green Book 5-case model)

# Requirements & Data
/arckit.requirements Create comprehensive requirements
/arckit.data-model Create data model with ERD and GDPR compliance

# Research & Strategy
/arckit.research Research technology options with build vs buy analysis
/arckit.wardley Create Wardley Map for strategic positioning

# Procurement
/arckit.sow Generate Statement of Work / RFP
/arckit.evaluate Create vendor evaluation framework

# Design Review
/arckit.hld-review Review High-Level Design
/arckit.dld-review Review Detailed Design

# Operations
/arckit.backlog Generate product backlog from requirements
/arckit.servicenow Create ServiceNow service design
/arckit.traceability Generate traceability matrix

# UK Government Compliance
/arckit.tcop Technology Code of Practice assessment
/arckit.secure Secure by Design assessment (NCSC CAF)
/arckit.service-assessment GDS Service Standard preparation
```

## Repository Structure

```
.arckit/
├── memory/                    # Global architecture principles
│   └── architecture-principles.md
├── templates/                 # Document templates (40+ templates)
└── scripts/bash/              # Helper scripts
    ├── create-project.sh      # Create numbered project directories
    └── generate-document-id.sh # Generate doc IDs (ARC-001-REQ-v1.0)

.claude/commands/              # ArcKit slash commands (arckit.*.md)

projects/
└── 001-exchange-online-migration/
    ├── requirements.md
    ├── sow.md
    ├── evaluation-criteria.md
    ├── traceability-matrix.md
    └── diagrams/
```

## Key Patterns

**Template-Driven Generation**: All commands read templates from `.arckit/templates/` and output to `projects/XXX-name/`. Never generate freeform documents.

**Token Limit Handling**: For large documents (requirements, SOBC, research), commands use the Write tool to save output directly to avoid the 32K token limit. Only a summary is displayed.

**Traceability Chain**: Stakeholders → Goals → Requirements (BR/FR/NFR/INT/DR) → Data Model → Components → User Stories

**Requirement ID Prefixes**:
- BR-xxx: Business Requirements
- FR-xxx: Functional Requirements
- NFR-xxx: Non-Functional (NFR-P-xxx Performance, NFR-SEC-xxx Security, etc.)
- INT-xxx: Integration Requirements
- DR-xxx: Data Requirements

**UK Government Context**: This toolkit targets UK public sector delivery with built-in support for GDS Service Standard, Technology Code of Practice, NCSC CAF, HM Treasury Orange/Green Book, and G-Cloud/DOS procurement.

## Helper Scripts

```bash
# Create a new numbered project directory
.arckit/scripts/bash/create-project.sh --name "project-name" --json

# Generate document IDs
.arckit/scripts/bash/generate-document-id.sh PROJECT_ID DOC_TYPE VERSION
# Example: ARC-001-REQ-v1.0

# List all projects
.arckit/scripts/bash/list-projects.sh
```

## Wardley Map Visualization

Wardley Maps use OnlineWardleyMaps syntax. Copy generated maps to https://create.wardleymaps.ai for visualization.
