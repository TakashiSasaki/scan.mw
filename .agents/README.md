# Project-Specific Agent Skills

The `.agents/` directory is the canonical location for project-specific agent aid files, skills, procedures, and scripts.

## Core Concepts

* **`.agents/`** is for project-specific agent aid files.
* **`.agents/skills/`** is the canonical location for common agent skills.
* **`AGENTS.md`** (at the repository root) is the common entry point for agents to know about these skills. It instructs agents to look here before executing tasks.
* **Consolidation**: Instead of duplicating long, agent-specific instructions in prompts or scattered text files, we aggregate them here as common skills so that any coding agent can leverage them.

## Security Rules

**NEVER** store the following in this directory:
* Secrets (e.g., passwords, API keys, database credentials)
* Tokens (e.g., GitHub PATs, OAuth tokens)
* Authentication Cookies
* Local device-specific configurations or absolute paths

Always use `.env.example` or placeholder variables when providing examples in skills or scripts.
