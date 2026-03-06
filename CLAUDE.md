# CLAUDE.md

This file provides guidance to AI assistants (Claude and others) working in this repository.

## Project Overview

This repository (`sathvikredde/sat`) is currently in its initial state. As the project grows, this file should be updated to reflect the actual codebase structure, workflows, and conventions.

## Repository State

- **Branch convention**: Feature/task branches follow the pattern `claude/<description>-<session-id>`
- **Remote**: `http://local_proxy@127.0.0.1:59713/git/sathvikredde/sat`
- **Primary development branch**: `claude/add-claude-documentation-Tmmec`

## Git Workflow

### Branching

- Always develop on the designated branch specified in the task context.
- Branch names starting with `claude/` are reserved for AI-assisted development.
- Never push to `main` or `master` directly without explicit permission.

### Commit Messages

Write clear, descriptive commit messages:
- Use the imperative mood ("Add feature" not "Added feature")
- Keep the subject line under 72 characters
- Reference issues or tasks when relevant

### Push Protocol

```bash
# Always use -u to set tracking
git push -u origin <branch-name>
```

On network failures, retry up to 4 times with exponential backoff (2s, 4s, 8s, 16s).

## Development Conventions

### Code Quality

- Prefer editing existing files over creating new ones.
- Avoid over-engineering — only make changes that are directly requested or clearly necessary.
- Do not add docstrings, comments, or type annotations to code you didn't change.
- Keep solutions simple and focused on the task at hand.

### Security

- Never introduce command injection, XSS, SQL injection, or other OWASP Top 10 vulnerabilities.
- Validate input at system boundaries (user input, external APIs); trust internal code guarantees.
- Do not commit secrets, credentials, or `.env` files.

### File Management

- Do not create files unless absolutely necessary.
- Do not create documentation files (`.md`, `README`) unless explicitly requested.
- Remove unused code rather than leaving it commented out.

## AI Assistant Guidelines

### Before Making Changes

1. Read the relevant files before modifying them.
2. Understand existing code before suggesting modifications.
3. Consider the reversibility and blast radius of actions.

### Risky Operations — Confirm Before Executing

Always check with the user before:
- Deleting files or branches
- Force-pushing (`git push --force`)
- Resetting commits (`git reset --hard`)
- Modifying CI/CD pipelines or shared infrastructure
- Sending messages, creating/closing PRs, or posting to external services

### Task Management

For complex multi-step tasks (3+ steps), use the TodoWrite tool to track progress. Mark tasks complete immediately after finishing them — do not batch completions.

## Updating This File

As the project evolves, keep this file up to date with:

- **Project purpose and description** — what does this project do?
- **Directory structure** — layout of key source directories
- **Language and framework** — programming language, major dependencies, versions
- **Build commands** — how to build the project
- **Test commands** — how to run the test suite
- **Lint/format commands** — code style enforcement tools and commands
- **Environment setup** — required environment variables, secrets, toolchain versions
- **CI/CD** — pipeline overview and what must pass before merging
- **Key conventions** — naming, architecture patterns, important decisions

### Template for Future Updates

```markdown
## Project Structure

\`\`\`
<root>/
├── src/          # Source code
├── tests/        # Test suite
├── docs/         # Documentation
└── scripts/      # Dev tooling scripts
\`\`\`

## Tech Stack

- Language: ...
- Framework: ...
- Test runner: ...
- Linter: ...
- Formatter: ...

## Common Commands

\`\`\`bash
# Install dependencies
...

# Run tests
...

# Lint / format
...

# Build
...
\`\`\`

## Environment Variables

| Variable | Description | Required |
|----------|-------------|----------|
| ...      | ...         | Yes/No   |
```
