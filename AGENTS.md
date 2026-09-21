# Manager_Project — Agent Working Rules

## Project principle

Manager_Project is a long-term modular management system.

The business scope may expand over time. Agents must avoid designing the
system around only the current feature list.

Prefer:

- modular architecture
- clear responsibilities
- maintainable code
- explicit business rules
- extensible modules
- versioned rules when regulations may change

## Core agents

The core development team consists of:

- Coordinator
- Architect
- Backend
- Frontend
- QA

Additional specialist agents may be added later without replacing the core
team.

Examples:

- Tax Agent
- Reporting Agent
- Document Agent
- Security Agent
- DevOps Agent
- Data Agent

## Git workflow

Never develop directly on `main`.

Use feature branches such as:

- feature/person-management
- feature/project-management
- feature/budget-allocation
- fix/login-validation
- refactor/database-services

Normal workflow:

Requirement
→ Design
→ Implementation
→ Test
→ Pull Request
→ Review
→ Merge

Do not force-push or rewrite shared history unless explicitly required.

## Scope control

Agents must not silently expand the requested scope.

When requirements are unclear:

1. Record assumptions.
2. Choose the smallest extensible solution.
3. Avoid inventing unnecessary business rules.
4. Keep future-changing rules configurable where appropriate.

## Architecture rules

Separate:

- presentation
- application logic
- business/domain logic
- persistence
- external integrations

Do not place authoritative business or financial rules only in frontend code.

## Database rules

Database changes must consider:

- migration
- existing data
- constraints
- relationships
- indexes
- recovery

Never delete migrations merely to make development easier.

Important historical or financial data should not be destructively deleted
without an explicit design decision.

Money must not use unsafe floating-point arithmetic.

## Security rules

Never trust client-side authorization.

Server-side code must enforce permissions and data scope.

Validate all user/external input.

Never commit:

- passwords
- API keys
- access tokens
- database credentials
- production secrets

Use environment variables and `.env.example`.

## Definition of Done

A task is complete only when relevant requirements are satisfied, including:

- implementation
- validation
- authorization
- error handling
- tests
- migrations
- documentation
- acceptance criteria verification

## Agent responsibilities

### Coordinator

Analyzes requests, decomposes work, identifies dependencies and assigns agents.

### Architect

Owns architecture, data models, module boundaries and major technical
decisions.

### Backend

Owns server-side implementation, APIs, persistence and business logic.

### Frontend

Owns pages, components, forms, dashboards and user interaction.

### QA

Verifies acceptance criteria, tests, regressions and permission behavior.

## Decision records

Important technical decisions should be documented under:

docs/decisions/

## Guiding principle

Design for change without introducing unnecessary complexity.
