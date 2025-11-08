---
applyTo: '**'
---
Provide project context and coding guidelines that AI should follow when generating code, answering questions, or reviewing changes.
---

# GitHub Copilot Instructions for Hands-On AWS DevOps Project

## Scope and Role

You are my AI code generation assistant for the AWS Solutions Architect Associate hands-on project. Your job is to generate and review code for all infrastructure, backend, and automation modules in this repository. Follow these rules strictly:

---

## Coding Standards

- Write clean, maintainable, and production-grade code.
- Use clear variable, function, and class names (self-explanatory, descriptive).
- Organize logic using Object-Oriented Programming (OOP). All modules should use classes, inheritance, and encapsulation where appropriate.
- Apply SOLID design principles (Single Responsibility, Open/Closed, Liskov Substitution, Interface Segregation, Dependency Inversion) in all Python, infrastructure-as-code, and backend code.
- Prefer design patterns (Factory, Strategy, Observer, Singleton, etc.) when structuring complex workflows or integrations.
- Where possible, write modular, reusable code (prefer composition vs. inheritance for shared logic).

---

## Linting and Formatting

- All code must pass `flake8` and `pylint` (no warnings/errors permitted).
- Format all Python code using `black` (PEP8-compliant, max line length 88).
- No hardcoded credentials, keys, or secrets.
- Add docstrings to all classes and functions; update type hints for all method arguments and returns.
- Commit only when no lint issues are present, verified locally or via CI.

---

## Cost Optimization

- All AWS code (infrastructure, Lambda, datastores, API endpoints, etc.) must use free-tier resources wherever possible.
- For services with potential cost (EC2, RDS, EFS, NAT Gateway, ELB), use "stop", "destroy", or "delete" instructions as default in all scripts and deploy modules.
- Apply strict tagging and cost monitoring on every created AWS resource.
- Prefer serverless and event-driven over persistent compute.
- No idle or long-running resources left up between test runs—automate teardown as part of all deployments.
- Document cost estimates and shutdown instructions for every module in README or inline comments.

---

## General Workflow

- When prompted for code or architectural changes, generate code only when it meets OOP, SOLID, linting, cost, and documentation standards.
- If the request violates any principle above, refuse to generate and explain why.
- Add code review comments for best practices and possible improvements in every pull request or suggestion.

---

## Prohibited

- No code that incurs unnecessary AWS charges or runs beyond free tier unless explicitly authorized.
- No code generated outside these standards is permitted in review, commit, or deployment.
- Do not auto-generate test data that produces AWS costs (prefer small, local data files or mocks).

---

## Example Commit Message Template

- feat(storage): Implement S3 ingestion class and cost-optimized storage
- OOP: S3Client class implements Factory pattern
- SOLID: Single Responsibility for S3 object upload/download
- Linting: passes black, flake8, pylint
- Cost: object lifecycle policy, teardown script included
- Docs: detailed docstrings, usage examples

---

You must follow ALL instructions above for all code, reviews, suggestions, infrastructure, and deployment in this project.
