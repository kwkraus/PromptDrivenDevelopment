
# Prompt-Driven Development (PDD) Workflow for Greenfield Projects

This structured 3-tiered system helps you scale prompt-driven ideation and implementation across small and large feature sets. Use this to generate comprehensive specifications and prompt blueprints ready for developers or LLMs.

---

## TIER 1: Product-Level Ideation

### PROMPT #1: Initial Brainstorming
```
Ask me one question at a time so we can develop a thorough, step-by-step spec for this idea. Each question should build on my previous answers, and our end goal is to have a detailed specification I can hand off to a developer. Let’s do this iteratively and dig into every relevant detail. Remember, only one question at a time. Here’s the idea: 

<IDEA>
```

---

### PROMPT #2: Compile Developer-Ready Product Spec
```
Now that we’ve wrapped up the brainstorming process, can you compile our findings into a comprehensive, developer-ready specification? Include all relevant requirements, architecture choices, data handling details, error handling strategies, and a testing plan so a developer can immediately begin implementation.
```

---

## TIER 2: Feature-Level Deep Dive (NEW)

Use this tier to explore **each feature from Tier 1** in depth. Repeat this process for each one.

### FEATURE DEEP DIVE PROMPT
```
We are now focusing on a core feature: <FEATURE_NAME>

Let’s define this feature in developer-ready detail. I want you to ask one question at a time. Each answer should refine your understanding and shape the spec for this feature. Our goal is to produce:

- A complete specification of this feature (function, UI/UX, interactions, edge cases)
- Data requirements, validations, and constraints
- Error and exception handling
- Integration points with other features or systems
- A testing plan

At the end, summarize everything in a final developer-ready feature spec.
```

---

### PROMPT #2 (Per Feature): Compile Feature Spec
```
Now that we’ve explored this feature in detail, can you compile a comprehensive, developer-ready spec for just this feature?
```

---

## TIER 3: Planning & Prompt Blueprinting

Use either the TDD or Non-TDD planning prompt depending on how you want to structure implementation.

### TDD PLANNING PROMPT
```
Draft a detailed, step-by-step blueprint for building this project. Then, once you have a solid plan, break it down into small, iterative chunks that build on each other. Look at these chunks and then go another round to break it into small steps. Review the results and make sure that the steps are small enough to be implemented safely with strong testing, but big enough to move the project forward. 

Iterate until you feel that the steps are right sized for this project. From here you should have the foundation to provide a series of prompts for a code-generation LLM that will implement each step in a test-driven manner.

Prioritize best practices, incremental progress, and early testing, ensuring no big jumps in complexity at any stage. Make sure that each prompt builds on the previous prompts, and ends with wiring things together. There should be no hanging or orphaned code that isn't integrated into a previous step.

Make sure and separate each prompt section. Use markdown. Each prompt should be tagged as text using code tags. The goal is to output prompts, but context, etc. is important as well.

<SPEC>
```

---

### NON-TDD PLANNING PROMPT
```
Draft a detailed, step-by-step blueprint for building this project. Then, once you have a solid plan, break it down into small, iterative chunks that build on each other. Look at these chunks and then go another round to break it into small steps. Review the results and make sure that the steps are small enough to be implemented safely, but big enough to move the project forward.

Iterate until you feel that the steps are right sized for this project. From here you should have the foundation to provide a series of prompts for a code-generation LLM that will implement each step.

Prioritize best practices, and incremental progress, ensuring no big jumps in complexity at any stage. Make sure that each prompt builds on the previous prompts and ends with wiring things together. There should be no hanging or orphaned code that isn't integrated into a previous step.

Make sure and separate each prompt section. Use markdown. Each prompt should be tagged as text using code tags. The goal is to output prompts, but context, etc. is important as well.

<SPEC>
```

---

## Summary of Workflow

1. **TIER 1** – Define your product and its core features
2. **TIER 2** – Explore each feature in detail and generate a developer-ready spec per feature
3. **TIER 3** – Generate implementation prompts (TDD or Non-TDD) for code-gen based development
