![Sheldon Cycle Banner](branding/sheldon-cycle-banner.svg)

# The Sheldon Cycle

**A model‑first workflow for AI‑assisted software development.**

**Design the system before implementation — and keep refining the model while the AI writes the code.**

LLMs are extremely good at **implementing systems**.  
They are much less reliable at **inventing the system model while coding**.

Or put differently:

**LLMs are great at implementing systems.  
They are terrible at guessing them.**

The Sheldon Cycle helps make that model explicit first.

---

## The Problem

Modern AI‑assisted development often follows a familiar pattern:

```
Prompt → AI invents architecture → AI writes code
```

At first everything feels fast and productive.

The AI generates code.  
The repository fills up.  
Progress seems to happen.

But something subtle goes wrong.

The **system model remains implicit**.

Concepts are fuzzy.  
Relationships are assumed.  
Terminology slowly drifts.  
Architecture emerges accidentally from code.

And eventually reality arrives.

Reality rarely knocks politely on the door.  
Reality tends to show up with a wrecking ball.

By that time, the system has already grown around assumptions nobody explicitly agreed on.

The Sheldon Cycle exists to prevent exactly that.

---

## Core Idea

The central principle of the Sheldon Cycle is simple:

```
Reality → Model → Architecture → Implementation
```

Instead of starting with code, the Sheldon Cycle starts with **understanding reality** and turning that understanding into an explicit model.

That model then guides architecture.

And only then does implementation begin.

This sounds almost obvious.

Yet most projects accidentally follow the opposite path:

```
Idea → Code → Accidental Architecture → Confusion
```

The Sheldon Cycle deliberately avoids that trap.

---

## Dialogue‑Driven Design

The Sheldon Cycle is built around a simple idea:

**Design the system *with* the AI before asking the AI to build it.**

The first phase happens as a **dialogue between a human and a reasoning LLM** (such as ChatGPT or Claude).

In this stage the AI is **not a code generator**.

It acts as a:

- reasoning partner
- modeling assistant
- consistency checker

The goal of the dialogue is to turn a vague idea into an **explicit system model**.

The result of that conversation is a set of artifacts:

```
DOMAIN_MODEL.md
CORE_PRINCIPLES.md
CONCEPT_MODEL.md
RELATIONSHIP_MODEL.md
SYSTEM_MODEL.md
ARCHITECTURE.md
```

These documents represent the **shared understanding of the system**.

They live outside the LLM and can be revisited, refined, and cross‑checked.

---

## One‑Page Overview

The Sheldon Cycle can be summarized as two phases.

```mermaid
flowchart LR

subgraph Bootstrap["Bootstrap Phase — Model Discovery"]
A[Understand the Domain] --> B[Define Core Concepts]
B --> C[Model Relationships]
C --> D[Simulate System Behavior]
D --> E[Derive Architecture]
end

subgraph Iteration["Iteration Phase — Model Refinement"]
F[Observation in Development] --> G[Model Inconsistency]
G --> H[Proposal]
H --> I[Model Refinement]
I --> J[Optional Architecture Update]
J --> F
end

E --> F
```

### Bootstrap Phase

A human and an LLM collaborate to discover the **system model**.

Outputs typically include:

- `DOMAIN_MODEL.md`
- `CORE_PRINCIPLES.md`
- `CONCEPT_MODEL.md`
- `RELATIONSHIP_MODEL.md`
- `SYSTEM_MODEL.md`
- `ARCHITECTURE.md`

These artifacts define how the system is supposed to work.

### Iteration Phase

Once implementation begins, reality inevitably exposes weaknesses in the model.

Instead of patching the code blindly, the Sheldon Cycle loops back:

```
Observation → Inconsistency → Proposal → Model Refinement → Architecture Update
```

The model improves as the system interacts with reality.

---

## Quick Start (with ChatGPT or Claude)

The Sheldon Cycle usually starts as a conversation with an LLM.

Simply tell the model you want to use the method and provide the repository link.

> NOTE: Use this in ChatGPT or Claude chat — **not** in coding agents like Claude Code or Codex.

Example prompt:

```
I want to plan a software project using the Sheldon Cycle.

Please follow the method described here:
https://github.com/DerFuchs/sheldon-cycle

Guide me through the bootstrap phase step by step and help me produce the required documents.
```

The LLM should then guide you through producing:

```
PROJECT_BRIEFING
→ DOMAIN_MODEL
→ CORE_PRINCIPLES
→ CONCEPT_MODEL
→ RELATIONSHIP_MODEL
→ SYSTEM_MODEL
→ ARCHITECTURE
```

Once the model stabilizes, coding agents can take over.

Implementation begins — while the model continues to evolve.

---

## When NOT to Use the Sheldon Cycle

The Sheldon Cycle is not meant for every situation.

You probably **should not use it** when:

### The problem is trivial

If you need a small script or quick automation, modeling may be unnecessary overhead.

### The architecture is already obvious

For simple CRUD applications or well‑understood patterns, the method adds little value.

### You are exploring with throwaway code

Sometimes experimentation is the fastest way to learn.

### The domain is simple

The Sheldon Cycle shines when systems involve **complex concepts or decision logic**.

If the system is mostly plumbing, the full process may be excessive.

In short:

**Use the Sheldon Cycle when misunderstanding the system model would be expensive.**

---

## What Problems This Solves

The Sheldon Cycle helps prevent common AI‑assisted development pitfalls:

- implicit system models
- terminology drift
- architecture emerging accidentally
- hidden assumptions
- AI hallucinating missing concepts
- painful refactoring later

Many teams recognize this pattern:

The AI writes lots of code quickly.

But nobody can clearly explain the system.

The Sheldon Cycle flips that dynamic:

**clarity first, code second.**

---

## Structured Dialogue Instead of Overnight Automation

The Sheldon Cycle intentionally rejects the idea that an AI assistant should simply “build the whole system overnight.”

Instead it treats development as a **conversation between human reasoning and machine precision**.

Human responsibilities:

- understand context
- interpret ambiguity
- challenge assumptions
- make decisions

AI responsibilities:

- structure reasoning
- detect inconsistencies
- suggest improvements
- implement deterministic logic

Development becomes a process of **passing the baton back and forth**.

---

## Templates

The `/templates` directory contains ready‑to‑use project files:

- `PROJECT_BRIEFING.md`
- `PROJECT_METHOD.md`
- `PROJECT_STRUCTURE.md`
- `PROJECT_BOOTSTRAP.md`
- `AI_AGENT_GUIDE.md`
- `PROPOSAL_TEMPLATE.md`
- `DECISION_LOG.md`
- `DESIGN_REVIEW.md`

These files provide the **Design‑OS** for a project.

---

## Philosophy

The Sheldon Cycle draws inspiration from:

- scientific reasoning
- system modeling
- architecture‑first design
- AI‑assisted development

It tries to stay intentionally lightweight.

The goal is not to add bureaucracy.

The goal is simply to **remove architectural illusions before code is written**.

---

## Origin Story

The Sheldon Cycle was not invented as a formal methodology.

It emerged almost accidentally while experimenting with AI-assisted software development.

During those experiments, one pattern became obvious very quickly:

Deep conversations with an LLM about a system design were often **more valuable than the code it produced**.

When the discussion focused on *concepts, relationships, and system behavior*, the AI helped uncover insights that were easy to miss when jumping straight to implementation.

Then another interesting discovery followed.

Whenever the evolving design documents were **fed back into the LLM as context**, the model suddenly became much better at spotting:

- inconsistencies between concepts
- missing entities or relationships
- terminology drift across documents
- architectural contradictions

Instead of reasoning only from the latest prompt, the LLM could now reason across the **entire system model**.

That led to a simple realization:

> AI works best when it helps **think about the system first**,  
> and **implement it only after the model becomes clear**.

The Sheldon Cycle is simply the process that emerged from that discovery.

Or put differently:

If the AI is going to help build the system,  
it might as well help **think about it first**.

---
## Why “Sheldon”?

The name *Sheldon Cycle* is a small nod to **Sheldon Cooper from *The Big Bang Theory***.

Sheldon is known for being extremely precise, methodical, and slightly obsessive about logical consistency.  
He has very little tolerance for vague assumptions and constantly pushes others to clarify what they actually mean.

That is essentially the role the Sheldon Cycle asks the AI to play during system design.

The LLM becomes the slightly pedantic colleague who keeps asking:

> “Wait… what exactly do you mean by that?”

And surprisingly often, that question is exactly what prevents a system design from collapsing later.

In short: the Sheldon Cycle is what happens when you invite a very
detail-oriented physicist into your system design process — and give
him an LLM.

---

## License

MIT
