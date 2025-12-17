# Workflow Design Approach

This document outlines the workflow design approach used across the **CloudPedagogy n8n Workflows** repository.

It complements the repository’s design principles by describing the **architectural patterns, conventions, and implementation choices** that guide how workflows are built, adapted, and reused.

The aim is to provide a clear, flexible baseline for practical, human-centred AI workflows in higher education, research, and professional practice.

---

## 1. Design philosophy

Workflows in this repository are designed to support **judgement, coordination, and reflection**, not to replace human decision-making.

### AI supports judgement, not authority
Generative AI is used for:
- sense-making
- classification
- summarisation
- option generation

AI outputs are treated as **proposals**, not decisions. Final interpretation, prioritisation, and accountability remain with people.

### Human-in-the-loop by default
Where AI is used:
- outputs are reviewable and contestable
- uncertainty or confidence is surfaced where possible
- humans can override or redirect outcomes

This reflects the realities of academic, research, and professional work.

### Logging and traceability as first-class features
Workflows are treated as part of decision-support systems, not just automations.

As a result:
- key actions and classifications are logged
- outcomes can be reviewed retrospectively
- patterns over time can inform improvement

Logging is lightweight by default, but intentional.

---

## 2. Three-layer workflow architecture

To maximise reuse and adaptability, workflows follow a simple three-layer structure.

### Layer 1: Source adapters
Source adapters define how information enters the workflow, for example:
- email (Gmail, Outlook)
- forms (Google Forms, Microsoft Forms)
- scheduled inputs (RSS feeds, APIs)

Early in the workflow, incoming data is **normalised** so downstream logic does not depend on a specific platform.

### Layer 2: Core logic
The core logic expresses the capability being demonstrated and is intentionally tool-agnostic.

It typically includes:
- normalisation of inputs
- AI-assisted classification or synthesis
- rule-based thresholds and guardrails
- confidence checks and escalation paths

This layer should remain stable even if platforms change.

### Layer 3: Destination adapters
Destination adapters define where outputs go, such as:
- notifications (email, Slack, Teams)
- task systems (Planner, Trello, To Do)
- logging and storage (Google Sheets, Excel, SharePoint)

Multiple destination adapters can be enabled or disabled via configuration.

---

## 3. Canonical data model

Early in each workflow, incoming data is converted into a **canonical internal representation**.

Typical fields include:
- source type and identifier
- timestamps
- sender or origin
- subject or title
- plain-text content

Normalising data early ensures that:
- core logic does not depend on specific connectors
- Gmail-based workflows can be repurposed for Outlook
- Google Sheets logging can be swapped for Excel or SharePoint

This approach reduces technical debt and supports long-term reuse.

---

## 4. Google-first baseline (with documented alternatives)

For Phase 1 workflows, Google services are often used as the **default implementation**, including:
- Gmail
- Google Sheets
- Google Forms
- Google Drive

This choice is pragmatic rather than ideological.

Google services typically offer:
- lower permission friction
- easier personal testing
- faster iteration during development

Where Google services are used, **Microsoft alternatives are documented**, such as:
- Outlook instead of Gmail
- Microsoft Forms instead of Google Forms
- Excel Online or SharePoint Lists instead of Google Sheets
- Teams instead of Slack

The underlying architecture allows these adapters to be swapped with minimal changes.

---

## 5. Alignment with the AI Capability Framework

This repository operationalises the **CloudPedagogy AI Capability Framework** through practice rather than description.

Across workflows, the following alignments are intentional:

- **AI Awareness & Orientation**  
  AI outputs are bounded, explainable, and contextualised.

- **Human–AI Co-Agency**  
  Humans retain oversight and decision authority.

- **Applied Practice & Innovation**  
  Workflows address real, everyday academic and research work.

- **Ethics, Equity & Impact**  
  Data minimisation, transparency, and inclusive design are prioritised.

- **Decision-Making & Governance**  
  Routing, thresholds, and audit trails are explicit.

- **Reflection, Learning & Renewal**  
  Logs and summaries enable review and improvement over time.

The framework informs *how* workflows are designed, not just *what* they do.

---

## 6. When to adapt or break the pattern

This design approach provides a baseline, not a constraint.

It may be appropriate to adapt or depart from these patterns when:
- a workflow is fully scheduled and has no human intake
- privacy or sensitivity requires minimal or no logging
- an institution-specific deployment requires platform-first design
- deterministic rules are more appropriate than AI assistance

Such decisions should be intentional and documented.

---

## 7. Purpose of this approach

The purpose of this design approach is to:
- reduce friction when creating new workflows
- ensure consistency and credibility across the repository
- support responsible, human-centred AI use
- make workflows easy to adapt, extend, and reuse

By standardising structure, this approach creates space for creativity where it matters most: solving real problems with care and judgement.
