# Setting up n8n

The workflows in this repository require an existing n8n instance. This document provides general guidance on setting up n8n and importing workflows from this repository.

These instructions are intentionally high-level and tool-agnostic. Individual workflow READMEs will describe any additional requirements.

---

## What is n8n?

n8n is a workflow automation platform that allows you to connect services, APIs, and tools into automated workflows. It can be run as a hosted service or self-hosted.

All workflows in this repository are provided as `.json` files that can be imported directly into n8n.

---

## Running n8n

You can use n8n in one of two common ways:

### Option 1: n8n Cloud
- Managed, hosted version of n8n
- No server setup required
- Suitable for most individual users and small teams

See: https://n8n.io

### Option 2: Self-hosted n8n
- Typically run using Docker
- Suitable for users who require local control or institutional hosting
- Requires basic server or Docker knowledge

Refer to the official n8n documentation for current installation instructions.

---

## Importing a workflow

To import a workflow from this repository:

1. Download the workflow `.json` file from GitHub.
2. Open your n8n instance.
3. Go to **Workflows** → **Import**.
4. Upload the `.json` file.
5. Review the workflow nodes and configuration.

Imported workflows will appear in your workflow list and can be edited before execution.

---

## Configuring credentials

Most workflows require one or more external service credentials (for example, OpenAI, Google, Microsoft, or email services).

- Credentials are configured inside n8n using its built-in credential manager.
- API keys and secrets should **never** be committed to GitHub.
- See `docs/credentials.md` for guidance on managing credentials safely.

---

## Testing workflows

Before using a workflow in live contexts:

- Test with **non-sensitive or dummy data**
- Run workflows manually to review outputs
- Check AI-generated outputs carefully before acting on them

Many workflows are designed to support review and decision-making rather than automated execution.

---

## Notes on institutional use

If you are using these workflows in an institutional context:

- Ensure alignment with local data protection, security, and acceptable use policies
- Use appropriate service accounts where required
- Add human approval or review steps before outputs are shared or acted upon

---

## Further documentation

For detailed platform instructions, refer to the official n8n documentation:
https://docs.n8n.io

