# Digital Education Request Router (HE-03)

## Overview
Digital education and learning technology teams often receive a high volume of unstructured requests via email, with varying urgency and unclear routing. This can lead to delays, duplicated effort, and uncertainty about what needs attention first.

The **Digital Education Request Router** is a human-in-the-loop workflow that supports triage and coordination by classifying incoming requests, routing them to the appropriate place, and maintaining a lightweight audit trail.

The workflow uses generative AI to assist sense-making and prioritisation, while keeping judgement, accountability, and decision-making with people.

---

## What this workflow does
- Monitors incoming digital education–related requests (e.g. via email)
- Uses AI to classify requests by category and urgency
- Routes requests to appropriate email inboxes and Slack channels
- Flags uncertain cases for manual triage
- Logs routing decisions and metadata for later review

This workflow **supports decision-making**; it does not automate approvals or outcomes.

---

## Default implementation (Phase 1)
The Phase 1 implementation is designed for ease of testing and individual or small-team use:

- **Intake:** Gmail
- **Visibility:** Slack
- **Routing:** Email
- **Logging:** Google Sheets

These choices are pragmatic and can be adapted to institutional environments.

---

## Alternative adapters
The workflow is designed using adapter patterns and can be repurposed with minimal changes:

- Gmail → Outlook / shared mailbox
- Slack → Microsoft Teams
- Google Sheets → Excel Online or SharePoint List
- Google Forms (optional) → Microsoft Forms

The core workflow logic remains the same.

---

## Setup overview
At a high level, setup involves:

1. Identifying an intake inbox or label for requests
2. Defining routing categories and destinations
3. Configuring email, Slack, and logging credentials in n8n
4. Importing the workflow and adjusting configuration values

Detailed setup instructions will be added as the workflow stabilises.

---

## Design notes
This workflow follows the repository’s shared design conventions:

- **Human-in-the-loop by default**
- **Decision-support, not judgement automation**
- **Transparent logic and inspectable routing**
- **Lightweight logging for traceability**

See:
- `docs/design-principles.md`
- `docs/workflow-design-approach.md`

---

## AI Capability Framework alignment
This workflow demonstrates applied AI capability across multiple domains, including:
- Human–AI Co-Agency
- Applied Practice & Innovation
- Decision-Making & Governance
- Reflection, Learning & Renewal

A short capability commentary is provided in `capability-notes.md`.

---

## Status
**Under active development.**

The workflow is being built iteratively and may change as testing and documentation progress.
