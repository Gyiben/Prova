# CLAUDE.md

This file provides guidance to AI assistants (Claude Code and others) working in this repository.

## Project Overview

**Name**: Prova
**Status**: Newly initialized repository — no source code, dependencies, or build infrastructure yet.

This is a blank-slate project. The sections below document the current state and establish conventions to follow as the project grows.

---

## Repository Structure

```
Prova/
├── README.md       # Project title only — expand as the project develops
└── CLAUDE.md       # This file
```

---

## Git Conventions

### Branching
- **Main branch**: `main` (canonical upstream branch)
- **Feature/AI branches**: `claude/<description>-<session-id>` (e.g., `claude/add-claude-documentation-ENO6o`)
- Never push directly to `main` without a pull request unless explicitly authorized.

### Commit Messages
Use concise, imperative-mood messages:
```
Add user authentication module
Fix null pointer in payment handler
Update README with setup instructions
```
Avoid vague messages like "fix stuff" or "wip".

### Push Workflow
```bash
git push -u origin <branch-name>
```
Retry up to 4 times with exponential backoff (2s, 4s, 8s, 16s) on network failures.

---

## Development Workflow

Since this project has no build system yet, the following steps apply when one is added:

1. **Install dependencies** — document the command here (e.g., `npm install`, `pip install -e .`)
2. **Run tests** — document the command here (e.g., `npm test`, `pytest`)
3. **Lint / format** — document the command here (e.g., `npm run lint`, `ruff check .`)
4. **Build** — document the command here (e.g., `npm run build`, `cargo build`)

Update this file as soon as these are established.

---

## Key Conventions for AI Assistants

### General
- Read files before modifying them — never guess at content.
- Prefer editing existing files over creating new ones.
- Keep changes minimal and focused on the task at hand.
- Do not add unnecessary comments, docstrings, or error handling beyond what is requested.

### Code Quality
- Avoid over-engineering. Solve the immediate problem; don't design for hypothetical future needs.
- Do not add backwards-compatibility shims for code that doesn't need them.
- Delete unused code rather than commenting it out.

### Security
- Never commit secrets, credentials, or API keys.
- Validate input at system boundaries (user input, external APIs); trust internal code.
- Avoid common vulnerabilities: SQL injection, XSS, command injection (OWASP Top 10).

### File Management
- Do not create documentation files (*.md) unless explicitly requested.
- Do not create helper utilities for one-off tasks.

---

## Adding a Technology Stack

When a language/framework is chosen, update this file with:
- How to install dependencies
- How to run the test suite
- How to run linting/formatting
- How to start a development server (if applicable)
- Any environment variable requirements (reference `.env.example`, never commit real values)

---

## Contact & Links
- Issues and PRs should follow the branching conventions above.
