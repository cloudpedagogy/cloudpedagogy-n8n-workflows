# Design Principles

The workflows in this repository are designed to support professional practice in higher education, research, and operational contexts. This document outlines the principles that guide how workflows are designed and how they are intended to be used.

These principles apply across all workflows unless explicitly stated otherwise.

---

## Human-in-the-loop

Workflows are designed to support human judgement, not replace it.

Where generative AI is used, outputs are intended as drafts, summaries, or prompts for further consideration. Final interpretation, decision-making, and accountability remain with the human user.

---

## Decision-support, not automation of judgement

Workflows may assist with:
- synthesising information
- identifying patterns or themes
- drafting or structuring content

They do not automate:
- academic judgement
- managerial decisions
- institutional approvals
- ethical or governance determinations

---

## Transparency and inspectability

Workflow logic is visible within n8n and can be inspected, modified, and adapted by users.

This transparency supports:
- trust in automated processes
- local adaptation and improvement
- informed oversight and review

---

## Privacy-by-default

Workflows are designed to minimise unnecessary handling of personal or sensitive data.

Users should:
- test workflows with non-sensitive data
- anonymise inputs where possible
- ensure alignment with local data protection requirements

No workflow in this repository is intended to bypass institutional data governance processes.

---

## Adaptability and local context

Workflows are designed to be adaptable rather than prescriptive.

Users are encouraged to:
- modify prompts and logic to reflect local practice
- add approval or review steps where appropriate
- integrate workflows into existing processes rather than replacing them wholesale

---

## Responsible use of generative AI

Where generative AI is used:
- limitations and uncertainties should be recognised
- outputs should be critically reviewed
- claims or summaries should be checked against original sources

Workflows are intended to support reflective and responsible engagement with AI technologies.

---

## Use at scale

When workflows are used beyond individual or small-team contexts, additional considerations may apply, including:
- governance and approval processes
- auditability and record-keeping
- role clarity and responsibility

Optional capability notes accompanying some workflows provide further guidance for use at scale.

