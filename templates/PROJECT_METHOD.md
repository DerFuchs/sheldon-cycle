# Project Method: The Sheldon Cycle

The Sheldon Cycle is a **model-first workflow for AI-assisted software design**.

Its purpose is to help humans and AI assistants collaborate on system design in a way that keeps the **system model explicit, coherent, and adaptable to reality**.

The core idea is simple:

Reality → Model → Architecture → Implementation

Most software projects jump directly from **idea → code**.  
The Sheldon Cycle deliberately inserts a **modeling phase** between those steps.

This prevents one of the most common failure modes of AI-assisted development:

> AI can implement systems very well.  
> It is much worse at guessing the system model while doing so.

The Sheldon Cycle therefore treats system design as an **iterative modeling process** before and during implementation.

---

## Dialogue-Driven Modeling

The Sheldon Cycle deliberately begins with a **reasoning dialogue between a human and a conversational LLM**.

This phase should **not start with a coding agent**.  
Instead it should happen in a **chat-style environment** such as:

- ChatGPT
- Claude
- similar reasoning-oriented LLM interfaces

In this stage the LLM acts as a **thinking partner**, not as a code generator.

The purpose of the dialogue is to **turn an initially vague idea into a set of explicit system artifacts**.

During this conversation the LLM should guide the human through the modeling process and ensure that the following documents are gradually produced:

- DOMAIN_MODEL.md
- CORE_PRINCIPLES.md
- CONCEPT_MODEL.md
- RELATIONSHIP_MODEL.md
- SYSTEM_MODEL.md
- ARCHITECTURE.md

These artifacts represent the **explicit system model**.

Once created, they become the **persistent context for the rest of the design process**.

A crucial rule of the Sheldon Cycle is that these documents must repeatedly be **re-fed into the LLM as source material**, especially during Phase 7 (Iterative Consistency Refinement).

This allows the AI to:

- cross-check the documents against each other
- detect contradictions
- highlight missing concepts
- enforce consistent terminology

In other words, the design process becomes:

dialogue → artifacts → re-feed → analysis → refinement

The LLM is therefore not used as an autonomous builder but as a **structured reasoning engine that continuously audits and improves the evolving system model**.

---

# Core Principles

The Sheldon Cycle is based on a small number of guiding principles.

## 1. Model First

The system model must become explicit before implementation may begin.

This includes:

- the domain
- the key concepts
- the relationships between concepts
- expected system behavior

Only once these are reasonably stable should architecture and implementation begin.

---

## 2. Architecture Emerges From The Model

Architecture should not be invented independently from the system model.

Instead:

concept model → system model → architecture

If the architecture cannot be explained through the model, the model is incomplete.

---

## 3. Reality Will Break Assumptions

Any model created during planning will eventually collide with reality.

The Sheldon Cycle expects this.

Instead of collapsing into chaos, the workflow includes a structured refinement loop.

---

## 4. Human + AI Collaboration

The Sheldon Cycle assumes **structured collaboration between human reasoning and machine precision**.

Typical responsibilities:

Human:
- domain understanding
- conceptual clarity
- identifying inconsistencies
- deciding between alternatives

AI:
- implementation
- analysis
- surfacing inconsistencies
- generating candidate solutions

Development becomes a **dialogue**, not a one-shot generation task.

---

## 5. Documented Iteration

The Sheldon Cycle relies on **explicit documentation as shared context between human and AI**.

During the bootstrap phase and the iteration phase, the evolving understanding of the system is captured in structured documents (for example: domain descriptions, concept definitions, relationship models, architecture notes).

These documents serve three purposes:

1. **Externalized thinking**  
   Writing things down forces the system model to become explicit.

2. **Shared context for AI**  
   The documents are provided to the AI assistant as source material so it can reason about the system consistently.

3. **Cross-checking the model**  
   The AI can compare the documents against each other to detect:
   - inconsistencies
   - unclear terminology
   - missing concepts
   - conflicting assumptions

This means the design process becomes an **iterative refinement loop driven by documentation**:

draft model → generate documents → cross-check with AI → refine model → update documents

Instead of relying on memory or implicit assumptions, the system model evolves through **versioned artifacts that both humans and AI can reason about**.

---

# The Sheldon Cycle Structure

The Sheldon Cycle has two major phases.

1. Bootstrap Phase (model discovery)
2. Iteration Phase (model refinement)

---

# Phase 1: Bootstrap (Model Discovery)

The bootstrap phase is the **up-front thinking process** used to transform an initially vague idea into a coherent system model.

The bootstrap flow is:

Understanding the domain  
→ Defining core concepts  
→ Modeling relationships  
→ Simulating system behavior  
→ Deriving architecture  
→ Implementation begins

### Understanding the Domain

The first step is understanding the problem space.

Questions to explore:

- What exists in the domain?
- What events happen?
- What constraints exist?
- What does reality look like?

At this stage the goal is **clarity**, not code.

---

### Defining Core Concepts

Next, identify the key entities and ideas the system revolves around.

Examples might include:

- users
- tasks
- documents
- transactions
- sessions

Each concept should have a **clear definition**.

---

### Modeling Relationships

Concepts rarely exist in isolation.

Define:

- how concepts relate
- ownership relationships
- lifecycle relationships
- information flow

This step prevents the system from becoming a collection of unrelated features.

---

### Simulating System Behavior

Before writing code, mentally simulate how the system behaves.

Typical questions:

- What happens when a user performs action X?
- What changes in the system state?
- What components interact?

This exposes missing concepts early.

---

### Deriving Architecture

Only after the model is coherent should the architecture be derived.

Architecture should follow naturally from the model.

Examples:

- service boundaries
- modules
- APIs
- data storage structure

---

### Implementation Begins

Once the architecture is stable enough, implementation can start.

AI assistants are extremely useful at this stage because the **system model is now clear**.

---

# Phase 2: Iteration (Model Refinement)

Once implementation begins, reality inevitably challenges the model.

Unexpected edge cases appear.
Assumptions break.
Concepts turn out to be incomplete.

The Sheldon Cycle uses an iteration loop to refine the model.

Observation  
→ Model inconsistency detected  
→ Proposal  
→ Model refinement  
→ Optional architecture update  
→ Implementation continues

---

### Observation

During development, something unexpected happens:

- a feature becomes difficult to implement
- the AI generates conflicting solutions
- the system behaves unexpectedly
- terminology becomes inconsistent

These are signals that the model is incomplete.

---

### Model Inconsistency

Identify the mismatch between reality and the current model.

Typical indicators:

- duplicated concepts
- unclear ownership
- missing entities
- inconsistent terminology

---

### Proposal

A proposal describes a potential improvement to the model.

A proposal should include:

- the problem
- the proposed concept or change
- affected parts of the model
- possible alternatives

This step prevents silent architectural drift.

---

### Model Refinement

If the proposal is accepted, the conceptual model is updated.

Changes might include:

- introducing a new concept
- redefining a relationship
- simplifying an abstraction
- renaming inconsistent terminology

---

### Architecture Update (Optional)

Sometimes the architectural structure must be adjusted to match the refined model.

If the model changes significantly, the architecture should follow.

---

### Implementation Continues

Implementation resumes with the refined model.

The cycle repeats whenever new inconsistencies appear.

---

# Artifacts Produced by the Sheldon Cycle

The Sheldon Cycle does not only produce code.
It produces a **set of structured documents that represent the evolving system model**.

These artifacts are not just documentation — they are the **working model of the system** shared between the human designer and the AI assistant.

During the bootstrap and iteration phases, these documents evolve together with the understanding of the system.

Typical artifacts include:

### Domain Model
Describes the real-world problem space.

Why this matters:

If the domain is poorly understood, every later design decision is built on unstable ground.  
Clarifying the domain early prevents entire architectures from being based on incorrect assumptions about how the real world actually behaves.

Purpose:
- clarify the domain
- identify actors, entities, and events
- capture real-world constraints

---

### Concept Model
Defines the core concepts of the system.

Why this matters:

Many architectural problems originate from unclear terminology.  
When different developers (or the AI) silently use the same word to mean different things, the system model fragments.  
A clear concept model creates a shared vocabulary that keeps the design coherent.

Purpose:
- establish a shared vocabulary
- prevent terminology drift
- make abstractions explicit

---

### Relationship Model
Defines how concepts interact.

Why this matters:

Without an explicit relationship model, systems often degrade into a collection of loosely connected features.  
By defining how concepts interact early, the design gains structural coherence and prevents hidden dependencies from emerging later in the implementation.

Purpose:
- connect concepts into a coherent model
- define ownership and lifecycle relationships
- describe information flow

---

### System Model
Describes how the system behaves dynamically.

Why this matters:

Static models alone cannot reveal behavioral gaps.  
Simulating the system forces the designer to confront real interaction flows and often exposes missing concepts, unclear responsibilities, or impossible state transitions before any code exists.

Purpose:
- simulate the system before code exists
- detect missing concepts
- test internal consistency

Simulation scenarios are captured in SIMULATION.md.

---

### Architecture Notes
Derived from the system model once it stabilizes.

Why this matters:

When architecture is derived from the model instead of invented upfront, structural decisions remain traceable to the underlying concepts.  
This significantly reduces accidental complexity and prevents architecture from drifting away from the system's conceptual foundations.

Purpose:
- translate the conceptual model into implementable structures

---

These artifacts form the **shared context used by both human and AI to reason about the system**.

As the Sheldon Cycle iterates, these documents are continuously refined.
They act as **externalized system thinking** and allow the AI to cross-check the model for inconsistencies.

---

# Expected Outcomes

A project using the Sheldon Cycle should produce:

- a clear domain model
- consistent terminology
- architecture derived from the model
- fewer architectural surprises during implementation
- effective collaboration between humans and AI assistants

The result is not perfect prediction of the future.

The result is a **system design process that survives contact with reality**.
