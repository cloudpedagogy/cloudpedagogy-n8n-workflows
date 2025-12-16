# Credentials and Secrets

Many workflows in this repository require access to external services such as AI APIs, email systems, document platforms, or messaging tools. This document provides general guidance on managing credentials and secrets safely when using n8n.

Credential handling is the responsibility of the user or organisation running the workflow.

---

## General principles

When working with credentials in n8n:

- Never commit API keys, passwords, or secrets to GitHub.
- Use n8n’s built-in credential manager to store secrets securely.
- Limit credentials to the minimum permissions required.
- Test workflows using non-sensitive data before live use.

All workflow files in this repository are provided without embedded credentials.

---

## Using n8n credentials

n8n manages credentials separately from workflow logic.

- Credentials are created and stored in n8n, not in workflow JSON files.
- Workflow nodes reference credentials by name.
- Different credentials can be substituted without modifying workflow logic.

This separation allows workflows to be shared safely and adapted across contexts.

---

## Environment variables

Where supported, some workflows may reference credentials using environment variables.

- Environment variables should be defined in your n8n runtime environment.
- Do not include `.env` files or secret values in version control.
- Refer to the official n8n documentation for supported environment variable patterns.

---

## AI service credentials

If workflows use generative AI services (e.g. OpenAI or similar):

- Review provider terms of service and data usage policies.
- Be mindful of what content is sent to external APIs.
- Avoid submitting personal, confidential, or sensitive institutional data unless appropriate safeguards are in place.

AI-generated outputs should always be reviewed by a human before use.

---

## Email and messaging credentials

Workflows that send email or messages may require:

- Gmail, Outlook, or SMTP credentials
- Slack, Microsoft Teams, or similar service tokens

When using shared or institutional accounts:
- Use approved service accounts where possible
- Ensure usage aligns with organisational policy

---

## Institutional considerations

For use within universities, research institutes, or public bodies:

- Ensure workflows align with local data protection and security requirements
- Confirm whether additional approvals are required for AI-enabled services
- Maintain auditability and human oversight where outputs inform decisions

---

## Further guidance

For detailed information on credential management, refer to:
https://docs.n8n.io/credentials/

