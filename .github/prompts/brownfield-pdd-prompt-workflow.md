
# 🏗️ Prompt-Driven Development (PDD) Workflow for Brownfield Projects

This workflow is tailored for enhancing or refactoring **existing software systems**, such as modernizing a monolith, modularizing features, or migrating to microservices. It assumes the LLM has visibility into project structure via tools like GitHub Copilot Agent or Cursor.

---

## 🔹 TIER 1: System Understanding & Modernization Goals

### ✅ PROMPT #1: Project Audit & Modernization Intent
```
Let’s start by understanding the existing system and your modernization goals.

Ask me one question at a time to help you:
- Identify what the system does
- Understand pain points or technical debt
- Clarify what should be preserved
- Define what outcomes you expect from modernization

Once we have that, we’ll start building a high-level product requirements spec for the desired outcome.
The project is: <INSERT CONTEXT>
```

---

### ✅ PROMPT #2: Generate Target-State Product Spec
```
Now that we’ve defined the modernization goals, can you draft a high-level product requirements specification for the **modernized system**?

Include:
- New system goals and core capabilities
- Key user flows or service interactions
- Data boundaries or domains
- Target architecture (e.g., microservices, event-driven, etc.)
- High-level testing and validation criteria
```

---

## 🔹 TIER 2: Domain or Component-Level Deep Dive

This layer zooms into specific code-bound units (e.g., a data domain, API, or business module) and helps redefine them as services or isolated components.

### 🧩 COMPONENT CONVERSION PROMPT
```
We are focused on transforming the component/domain: <COMPONENT_NAME>

Using the codebase context, ask one question at a time to:
- Understand what this component does (data, logic, APIs)
- Identify the inputs, outputs, dependencies, and coupling
- Design its boundaries and ownership as a standalone unit or service
- Handle state, caching, or coordination logic
- Define migration or interface strategy from monolith to service

End with a developer-ready spec to extract and modernize this component.
```

---

### ✅ PROMPT #2 (Per Component): Output Service Specification
```
Based on our deep dive, can you generate a complete specification for turning <COMPONENT_NAME> into a standalone microservice or module?

Include:
- Scope and responsibilities
- Data model or schema
- API contracts and endpoints
- Auth/validation concerns
- Dependency strategy
- Testing strategy (unit + integration)
- Deployment notes
```

---

## 🔹 TIER 3: Migration Planning & Prompt Blueprinting

Break the modernization effort into safe, iterative, testable migration tasks. Feed the service/component specs into this tier.

### ✅ TDD PLANNING PROMPT (Refactor-Aware)
```
Draft a detailed blueprint for refactoring this project in a test-safe, incremental manner. Then break it down into small, dependency-aware tasks that can be done step by step.

Each task should:
- Represent a migration-safe refactor
- Include prompts for LLM support (e.g., move model to new service, stub APIs, update callers)
- Preserve existing functionality and enable rollback if needed
- Include notes on testing, observability, and validation

Use markdown. Tag each prompt with code tags.
```

---

### ✅ NON-TDD PLANNING PROMPT
```
Draft a blueprint for implementing this migration. Break it down into isolated tasks with a clear before/after state, including prompts to assist an LLM in making these changes.

Prioritize safety, gradual rollout, and stakeholder visibility. Use markdown. Tag prompts as text/code. Make sure no task results in an incomplete or dangling feature.
```

---

## ✅ Summary of Workflow

1. **TIER 1** – Understand the current system and define modernization goals
2. **TIER 2** – Explore each domain/component to extract detailed microservice specs
3. **TIER 3** – Plan the refactor with implementation-ready, LLM-usable task prompts

---
