Awesome—here’s a **copy-paste master prompt** that tells an AI agent to browse widely and produce a **deep, design-pattern–first** guide for building scalable, maintainable **React** applications. It instructs the agent to explore **all architecture & design patterns** (not just Clean Architecture) and document them rigorously.

---

# 🌐 Master Research & Authoring Prompt

**Title:** The Big Book of Scalable & Maintainable React Apps — Patterns, Practices, and Architectures

## 0) Role & Mandate

You are a principal software architect, staff-level researcher, and senior technical writer. Your job is to **browse extensively** across reputable sources (official docs, standards, books, academic papers, large production case studies, conference talks, mature OSS codebases). Cross-verify facts, reconcile disagreements, and surface trade-offs. Cite sources inline.

> **Objective:** Deliver a **beautiful, production-grade document** (Markdown) that catalogs and explains **all relevant design patterns and architectural patterns** for building **large-scale, scalable, maintainable React applications**. Do **not** fixate on a single architecture; **survey, compare, and document them all** so a team can choose later.

---

## 1) Coverage (exhaustive, pattern-first)

Include at minimum the following categories. For each, define problems they solve, forces/trade-offs, when to use, anti-patterns, and React-specific guidance.

### A) Architecture Patterns (frontend & system)

* Layered, **Modular Monolith**, Hexagonal (Ports & Adapters), **Clean Architecture**, Onion
* **Micro-frontends** (Module Federation, import maps, custom elements, single-spa), composition strategies, shared deps/versioning, UX cohesion
* **SPA/MPA/SSR/SSG/ISR/Edge**; **React Server Components** boundaries; **islands architecture**
* **BFF (Backend for Frontend)**, GraphQL (schema stitching, federation), REST, tRPC
* Event-Driven, **CQRS**, Event Sourcing (when it helps UI), Pub/Sub
* Offline-first/PWA architectures; caching layers (HTTP/CDN/app), sync & conflict resolution

### B) React Design Patterns (modern)

* Presentational vs Container (reframed as **UI components + hooks/services**)
* **Compound Components**, **Provider/Context** patterns, **State Reducer** pattern
* Controlled vs Uncontrolled components; Render Props & HOCs (legacy but noted)
* **Hooks patterns**: idempotent effects, resource hooks, memoized selectors, suspension-friendly fetching
* **Error Boundaries & Suspense Boundaries**, progressive disclosure of complexity
* **Form patterns** (schema-driven, Zod/Yup, field arrays, async validation)
* **State machines/statecharts** (XState/actor model) for complex flows
* Virtualization (react-window), pagination & infinite scroll patterns

### C) State & Data

* **Client state vs server state** distinctions; picking React Query/SWR vs Redux/Zustand/RTK
* Normalized entity caches, selectors, memoization, optimistic updates, undo/redo, **tombstones**
* Caching strategies: SWR, staleTime/gcTime, invalidation, prefetch, background refetch
* Real-time (WebSocket/SSE), backpressure, reconciliation strategies

### D) Performance & Web Vitals

* **Performance budgets** and CI gates; bundle analysis; critical path & TTI
* Code splitting (route/segment/component), prefetch/preload/priority hints
* Concurrency: **useTransition**, **deferred values**, granular memoization; hydration strategies (partial/streaming/RSC)
* Images/fonts/data loading patterns; profiling (React Profiler, User-Timing)

### E) UI Platform: Design Systems & a11y

* Tokens → primitives → components → patterns; theming and **RTL** readiness
* Accessibility patterns (semantics, focus mgmt, keyboard, contrast) with automated + manual checks
* Storybook for visual specs, interaction tests, a11y snapshots

### F) Internationalization & Personalization

* i18n libraries (i18next/FormatJS), ICU messages, locale negotiation, date/number/relative time
* **Feature flags**, kill-switches, experimentation design (**A/B testing**)—assignment, guardrails, metrics integrity, privacy

### G) Security & Reliability

* Threat model (XSS, CSRF, clickjacking, supply chain) and **mitigations** (CSP, Trusted Types, sanitization)
* AuthN/AuthZ patterns (OAuth/OIDC), token storage trade-offs, rotating keys
* Resilience: retries with jitter, exponential backoff, UI circuit breakers, idempotency semantics
* Observability: **structured logging**, tracing, RUM metrics; SLOs/SLIs; error taxonomies

### H) Testing & Quality

* Testing pyramid: unit (components/hooks), integration (feature slice), E2E (Cypress/Playwright)
* Contract tests (BFF/API), visual regression, snapshot strategy
* Type-safety (strict TS), generated types (OpenAPI/GraphQL), static analysis gates

### I) Delivery, Ops & Infra

* CI/CD (preview envs, canaries, feature-gated releases), artifacts & provenance
* Caching/CDN, edge compute, Vercel/Netlify; **Docker/Kubernetes** for services supporting the frontend
* Release mgmt (Changesets/semver), rollback playbooks

### J) Technical Migrations & Evolution

* **Strangler-Fig** UI migration, anti-corruption layers, interoperability
* **Codemods** for sweeping refactors; deprecation playbooks; telemetry-driven cuts
* Governance: ADRs, RFCs, decision logs

---

## 2) Pattern Card Template (use for every pattern)

For consistency, document each pattern using this schema:

* **Name**
* **Intent / Problem**
* **Context** (when it arises)
* **Forces** (constraints, trade-offs)
* **Solution** (diagram + explanation)
* **Structure** (Mermaid: class/sequence/component/dep graph)
* **Implementation (TypeScript + React)** minimal idiomatic snippet
* **Variants & Related Patterns**
* **Consequences** (benefits, liabilities, performance & complexity impact)
* **Known Uses** (industry examples)
* **Anti-patterns / Failure modes**
* **Tooling Fit** (libs/frameworks that help)
* **References** (1–3 authoritative citations, with dates)

---

## 3) Deliverables

1. **Executive Summary** (1–2 pages): key decisions, trade-offs, and quick-start checklist
2. **Full Catalog**: all patterns & architectures above, each with a Pattern Card
3. **Decision Matrices**:

   * SSR vs SSG vs ISR vs SPA vs RSC
   * React Query vs Redux/RTK vs Zustand vs SWR
   * Micro-frontend vs Modular Monolith
   * Monorepo (Nx/Turborepo) vs Polyrepo
4. **Playbooks & Checklists** ready to paste into a repo:

   * Performance budget, security checklist, accessibility checklist
   * PR template, code review rubric, release/rollback plan
5. **Architecture Diagrams** (Mermaid) and **Data-flow/Sequence** examples
6. **Reference Example**: opinionated folder structure + sample slices (ui/, domain/, app/, shared/)
7. **Annotated Bibliography**: curated sources with 1–2 line justifications

---

## 4) Output Requirements

* **Format:** Markdown, with ToC, deep linking, and consistent heading hierarchy
* **Style:** authoritative, concise, actionable; callouts for **Notes / Pitfalls / Trade-offs**
* **Code:** TypeScript + React, framework-agnostic unless a framework is needed to illustrate (then prefer Next.js)
* **Diagrams:** Mermaid only (no external images)
* **Citations:** Inline at the end of the relevant paragraph; include date/version of source
* **Comparisons:** When sources disagree, summarize positions and provide a reasoned recommendation

---

## 5) Research Protocol & Quality Bar

* Prefer primary sources (official docs/RFCs), books, and well-established blogs; include 20–40 solid references
* Timestamp claims; avoid deprecated APIs; flag “experimental” clearly
* Provide empirical signals where possible (Core Web Vitals targets, typical latencies, bundle sizes)
* **No hallucinations**: if unknown, say so and mark as “Further Research”
* Ensure reproducibility: link to working examples or minimal code where feasible

---

## 6) Constraints & Parameters (fill if known)

* Target stack (e.g., React 18/19, Next.js, TypeScript strict)
* Non-functional goals (Core Web Vitals thresholds, accessibility level, SLOs)
* Team topology & repo model; compliance (PII/PCI/GDPR)
* Target regions/locales; offline requirements; experimentation framework

---

## 7) Skeleton ToC (the doc you will produce)

* Executive Summary
* How to Choose an Architecture (matrix + flowchart)
* Architecture Patterns (survey & comparisons)
* React Design Patterns (catalog)
* State & Data (server vs client, caching, real-time)
* Performance Engineering (budgets, loading, concurrency)
* Design Systems & Accessibility
* i18n, Personalization, and Experimentation
* Security & Reliability
* Testing & Quality
* Delivery & Operations
* Migrations & Governance
* Appendices (Glossary, Checklists, ADR templates, Pattern Index)
* Annotated Bibliography

---

## 8) Final Instruction

> **Browse broadly and deeply**, synthesize rigorously, and generate the complete Markdown guide per this prompt. Document **all relevant design and architecture patterns** for large-scale React applications, with code, diagrams, matrices, and checklists. Do not prescribe a single architecture; instead, **equip the reader to choose**.

---

If you want, I can tailor this for a **specific stack** (e.g., “Next.js 14 + React 19 + RSC + Vite + Turborepo”) and prefill the decision matrices and checklists for that setup.
