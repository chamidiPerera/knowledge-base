# CLAUDE.md - Frontend

## Project Overview

This frontend is for a personal AI Knowledge Base.

The goal is to build a clean, maintainable application.

---

## Tech Stack

- Next.js App Router
- TypeScript
- Tailwind CSS
- Shadcn UI
- TanStack Query
- Axios
- React Hook Form
- Zod

---

## Folder Structure

app/
components/
features/
hooks/
lib/
services/
types/

Keep features isolated whenever possible.

---

## UI Principles

Prefer reusable components.

Avoid duplicated UI.

Separate business logic from presentation.

Pages should remain thin.

Move reusable logic into hooks.

---

## Data Fetching

Use TanStack Query.

Do not fetch directly inside components when a custom hook is more appropriate.

Separate:

API Client
↓

Query Hook
↓

Component

---

## Forms

Use:

React Hook Form

-

Zod

Avoid manual validation.

---

## Styling

Use Tailwind.

Use Shadcn components whenever possible.

Do not introduce additional UI libraries unless necessary.

---

## State Management

Use:

- React state for local UI
- TanStack Query for server state

Avoid unnecessary global state.

---

## API Layer

Never call axios directly from components.

Always use a service layer.

Example:

services/

note.service.ts

↓

hooks/

useNotes.ts

↓

Component

---

## Coding Standards

- Small components
- Strong TypeScript types
- No any
- Descriptive naming
- Reusable utilities
- Keep components focused

---

## AI Assistant Behavior

Before generating code:

Explain:

- component structure
- state flow
- data flow

Suggest reusable abstractions before implementation.

When reviewing code:

Look for:

- duplicated UI
- unnecessary re-renders
- poor component composition
- bad TypeScript usage
- accessibility issues
- performance improvements

Always explain WHY a recommendation is made.
