# GEMINI.md - Agent Instructions & Project Guidelines

This document outlines the development standards, workflow expectations, and guidelines for AI agents working on `lipienski.dev`.

---

## 1. Project Overview

- **Project:** `lipienski.dev`
- **Business Focus:** Independent software engineering consultancy specialized in **fixing, improving, and modernizing legacy PHP applications**.
- **Value Proposition & Positioning:** Solo consultancy. Clients get direct, hands-on senior engineering work from the founder—never outsourced or delegated to junior agency staff.
- **Tech Stack:** Modern TypeScript web stack (Astro / Next.js / React, Tailwind CSS).
- **Hosting & CI/CD:** Cloudflare Pages with automatic deployments triggered on Git push to GitHub.
- **Architecture Philosophy:** Performance-first, accessible, conversion-friendly, content-focused, and minimal bloat.

---

## 2. Core Operating Principles

### 2.1. Plan First
- **Workflow:** For non-trivial tasks or architectural modifications, outline a concise implementation plan before writing or changing code.
- **Clarity:** Clearly explain the rationale behind significant decisions or structural changes.

### 2.2. Quality Gates & Verification
Before marking a task as complete:
- **Type Checking:** Run TypeScript checks (e.g., `npm run typecheck` or `tsc --noEmit`) to ensure zero type errors.
- **Linting & Formatting:** Ensure code conforms to linting and formatting rules (e.g., `npm run lint`).
- **Testing:** Run existing test suites (e.g., `npm test`) and add unit or integration tests for new functionality or bug fixes.
- **Build Validation:** Verify that production builds succeed without warnings or errors (e.g., `npm run build`).

### 2.3. Dependency Discipline
- Keep third-party dependencies to a minimum.
- Prefer standard web platform APIs and modern JavaScript/TypeScript capabilities over introducing single-use utility packages.
- Always check compatibility and package footprint before installing new dependencies.

### 2.4. Documentation Integrity
- Keep documentation (such as `README.md`, setup instructions, and architecture notes) synchronized with code changes.
- Preserve meaningful comments and docstrings.
- Update changelogs or project notes when introducing significant features.

### 2.5. Git & Commit Conventions
- Use the **Conventional Commits** specification:
  - `feat:` for new user-facing features
  - `fix:` for bug fixes
  - `docs:` for documentation updates
  - `refactor:` for code refactoring without behavior change
  - `style:` for formatting/styling changes without logic change
  - `test:` for adding or updating tests
  - `chore:` for build tooling, config, or dependency maintenance

---

## 3. Code Standards & Best Practices

### 3.1. TypeScript
- Use strict typing mode. Avoid `any` — use `unknown`, generics, or proper type narrowing instead.
- Define clear interfaces and types for component props, data models, and API responses.
- Prefer immutable data patterns and pure functions where feasible.

### 3.2. Frontend & Styling
- Write semantic, accessible HTML (`aria-*` attributes, keyboard navigability, semantic tags).
- Responsive by default: Mobile-first responsive design using modern CSS / Tailwind CSS.
- Ensure high performance: Optimize assets, keep bundle sizes small, and leverage static generation / server rendering where appropriate.

### 3.3. Project Organization
- Keep component hierarchies clear and modular.
- Co-locate tests, styles, and types with their respective components/modules when appropriate.

### 3.4. Cloudflare Pages & Deployment Considerations
- **Runtime Compatibility:** Ensure code and dependencies are compatible with the Cloudflare Pages runtime (prefer standard Web APIs over Node.js-only builtins if using server-side / edge functions).
- **Static Output:** Ensure build artifacts match Cloudflare Pages output directory configurations (e.g., `dist` for Astro or out directories).
- **CI/CD Reliability:** Ensure production builds are deterministic and pass all quality checks cleanly so automated GitHub deployments succeed consistently.

---

## 4. Brand Voice, Positioning & Content Guidelines

### 4.1. Core Narrative & Value Proposition
- **High-Impact Senior Expertise:** Emphasize that clients work directly with a senior engineer who solves complex problems end-to-end, rather than being handed off to junior developers or account managers.
- **Legacy PHP Modernization Authority:** Focus on pragmatic solutions: upgrading legacy versions (PHP 5.x/7.x to 8.x), refactoring spaghetti code, fixing critical bugs, improving performance/database queries, adding automated test suites, improving developer experience, and modernizing architecture safely without risky full-rewrites.

### 4.2. Tone of Voice
- **Authoritative & Pragmatic:** Confident, direct, and solution-oriented. Avoid buzzword-heavy agency fluff.
- **Transparent & Trustworthy:** Honest technical communication that appeals to CTOs, engineering managers, product owners, and business founders.
- **First-Person / Solo Framing:** Use first-person framing ("I help businesses...", "You work directly with me") to reinforce the dedicated solo consultancy model.

---

## 5. Standard Commands Quick Reference

| Command | Purpose |
|---|---|
| `npm run dev` | Start local development server |
| `npm run build` | Build production assets |
| `npm run preview` | Preview production build locally |
| `npm run lint` | Run linter across the codebase |
| `npm run typecheck` | Run TypeScript compiler checks |
| `npm test` | Run test suite |
