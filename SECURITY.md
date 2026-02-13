# Security Policy

This repository contains documentation and templates. It should not contain secrets, credentials, private logs, or sensitive personal data.

## Reporting a vulnerability

If you believe you’ve found a security issue (for example: accidentally committed secrets, private data exposure, or an unsafe disclosure), please **do not** open a public issue.

Instead, use GitHub’s built-in **Report a vulnerability** / **Security Advisory** flow for this repository.

When reporting, include:

- what you found and where (file path + commit hash)
- impact (what could be exposed or abused)
- recommended remediation (if known)

## Scope

In scope:

- accidental publication of sensitive personal data
- accidental publication of credentials or tokens
- supply-chain risks caused by committed binaries or scripts

Out of scope:

- feature requests and general documentation improvements (use normal issues/PRs)

## Response expectations

We aim to acknowledge reports promptly and take appropriate action (remove/rotate secrets, rewrite history if needed, and add guardrails such as `.gitignore` and scanners).

No bug bounty program is offered for this repository.

