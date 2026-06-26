# CLAUDE.md - Backend

## Project Overview 

This project is a personal AI-powered Knowledge Base.

The purpose of this project is learning:

- Backend development
- Layered Architecture
- PostgreSQL
- SQL
- AI integration
- Vector databases
- FastAPI

Do not over-engineer solutions. Prefer readability and maintainability over cleverness.

---

## Tech Stack

- FastAPI
- PostgreSQL
- SQLAlchemy
- Alembic
- Pydantic
- Python 3.13+

---

## Architecture

Follow Layered Architecture.

Request Flow:

API (Controller)
↓
Service
↓
Repository
↓
Database

Controllers should only:

- Receive HTTP requests
- Validate input
- Call services
- Return HTTP responses

Controllers should NOT contain business logic.

Services should:

- Contain all business logic
- Validate business rules
- Coordinate repositories
- Throw domain/business exceptions

Repositories should:

- Only access the database
- Never contain business logic
- Never raise HTTP exceptions

---

## Folder Structure

app/
api/
services/
repositories/
database/
schemas/
exceptions/
core/
utils/

---

## Database

Use PostgreSQL.

Use Alembic for migrations.

Never manually modify the production schema.

Use SQLAlchemy ORM.

When SQL becomes complex, prefer writing explicit SQL instead of forcing everything through the ORM.

---

## Coding Standards

- Follow SOLID principles where practical.
- Keep functions small.
- Prefer composition over large classes.
- Avoid duplicate logic.
- Use descriptive names.
- No magic strings.
- No global mutable state.

---

## Error Handling

Controllers return HTTPExceptions.

Services raise business/domain exceptions.

Repositories only raise database-related exceptions.

Never return HTTPException from repositories or services.

---

## Dependency Injection

Use FastAPI dependency injection.

Avoid creating dependencies manually inside services.

---

## Validation

Validate request payloads using Pydantic schemas.

Never trust client input.

---

## Logging

Log unexpected failures.

Do not log secrets.

---

## AI Assistant Behavior

Do not implement features immediately.

When asked to build something:

1. Explain the architecture.
2. Explain why each layer exists.
3. Suggest improvements if necessary.
4. Generate code only after the architecture is clear.

Prefer teaching over simply generating code.

When reviewing code:

- Look for architectural problems.
- Look for SOLID violations.
- Look for duplicated logic.
- Look for SQL issues.
- Look for performance concerns.
- Look for security issues.

Always explain WHY a change is recommended.
