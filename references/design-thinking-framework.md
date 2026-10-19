# Design Thinking & Product Discovery Framework Reference

This reference supports the [`design-discovery`](../SKILL.md) skill. It distills foundational design thinking theory (Horst Rittel's *Wicked Problems*, Donald Schön's *Reflection-in-Action*, Nigel Cross's *Problem–Solution Co-Evolution*, Christopher Alexander's *Pattern Language*, and studio design methodology) into practical tools for **product design and software discovery**.

---

## 1. Core Design Thinking Concepts for Product Design

| Design Thinking Principle | Origin & Theory | Product Design Application | Key Discovery Question |
| :--- | :--- | :--- | :--- |
| **Wicked Problem Framing** | **Rittel & Webber (1973):** Design problems are ill-defined; you only truly understand the problem by testing candidate solutions. | Don't take feature requests at face value. Unpack *why* the user feels friction and what workflow constraint is causing it. | *"If we solve what the user asked for, what deeper problem remains unsolved?"* |
| **Problem–Solution Co-Evolution** | **Nigel Cross & Kees Dorst:** Great designers don't freeze requirements first; they oscillate between reframing the problem and sketching solutions. | Pair every problem statement with 2–3 concrete conceptual sketches so the options expose hidden requirements early. | *"How does seeing Option A vs. Option B change what we think the real priority is?"* |
| **The Core Conceptual Model (*Parti*)** | **Peter Rowe / Studio Theory:** The single governing idea or organizing diagram that holds a design together. | The mental model the user forms of your product (e.g., *Spreadsheet*, *Timeline*, *Infinite Canvas*, *Command Queue*). Every feature must fit this model. | *"What is the one core metaphor of this product, and which features violate it?"* |
| **Reflection-in-Action** | **Donald Schön (1983):** A designer makes a move, the medium "talks back" (revealing friction or surprises), and the designer adapts. | Build thin vertical slices or interactive flows early so real data, latency, and edge cases "talk back" before UI polish begins. | *"Where is the current prototype or codebase 'talking back' and resisting our design?"* |
| **Core Canvas vs. Supporting Plumbing** | **Louis Kahn (*Served vs. Servant*) & Beaux-Arts (*Poché*):** Keep human spaces open and calm; hide mechanical ducts and pipes inside thick walls. | Keep 80%+ of visual weight on the user's primary task. Tuck settings, sync state, billing, and metadata into progressive disclosure or background layers. | *"Why is administrative or system plumbing competing for attention with the user's primary canvas?"* |
| **Workflow Choreography** | **Spatial Sequencing:** Guiding a person from entry threshold to primary activity naturally, without needing signs everywhere. | Design the transition from **Cold Start (0 items)** $\rightarrow$ **First Action** $\rightarrow$ **Daily Flow** so the layout itself teaches the user what to do next. | *"If we deleted all onboarding tooltips and help text, would the user still know what to do first?"* |
| **Material / Stack Honesty** | **Tectonic Design (KVA MATx):** Let the physical capabilities of your materials generate the design rather than faking another medium. | Design around what your tech stack does best (e.g., local-first instant filtering, streaming AI responses, keyboard navigation, live multiplayer cursors). | *"Are we designing natively for our stack's strengths, or forcing it to imitate a static form?"* |
| **Pattern Decomposition** | **Christopher Alexander (1964/1977):** Break complex systems into loosely coupled patterns at the seams where "misfits" occur. | Identify the highest-friction seams in the product (e.g., guest-to-authenticated, draft-to-published, local-to-cloud) and design explicit transitions for them. | *"Where are the seams between subsystems where user state or context gets dropped?"* |

---

## 2. The 10-Point Product Design Critique Rubric

Use this checklist during **Phase 4 (Design Critique)** or when auditing an existing product/feature:

1. **The 5-Second Mental Model Test:** Can a user explain how the objects in this app relate to each other using at most 3 boxes and 2 arrows? If it takes 12 boxes, the conceptual model is muddled.
2. **The Subtraction Test:** Point to each nav item, panel, toolbar, or step in the flow: *"What breaks for the user if we delete this completely or merge it into the main view?"*
3. **The "Bolted-On Feature" Check:** Spot features that feel like an extra tab, modal, or floating button tacked onto the product. How can they be unified into the core conceptual model—or cut?
4. **The High-Frequency Adjacency Check:** Which two actions does a user perform within 5 seconds of each other? Are they immediately adjacent on screen, or separated by navigation/modals?
5. **The Canvas-to-Chrome Ratio:** Does the user's actual work/content occupy at least 80% of the screen and mental focus, or is the viewport dominated by sidebars, headers, badges, and toggles?
6. **The Scale Extremes Check (0, 1, 10,000):**
   * **0 items (Empty State):** Does it invite immediate creation or feel like a dead end?
   * **1 item:** Does the layout still look intentional?
   * **10,000 items:** How do search, filtering, pagination, and visual density hold up under heavy real-world usage?
7. **The Dead-End Flow Check:** Does the user ever enter a modal, sub-page, or error state where they lose their place or have to click "Back" multiple times to continue working?
8. **The Vertical Slice (Schema-to-Screen) Check:** Does the database schema and state layer actually support this UI cleanly, or will engineers have to write hacky glue code to make the mockup work?
9. **The Latency & Feedback Honesty Check:** What happens during the 200ms–5s when the network or model is working? Is there optimistic feedback, streaming, or progressive skeleton state?
10. **The Self-Evident Hierarchy Check:** Without reading labels, does visual weight, contrast, and grouping make the primary action unmistakable?

---

## 3. Product Design & Discovery Brief Template

Use this structure when outputting the final deliverable of a **Design Discovery** session:

```markdown
# Product Design Discovery Brief: [Product / Feature Name]

## 1. Problem Framing & Context
* **The Surface Request:** [What was initially asked for]
* **The Reframed Core Problem:** [The underlying human/workflow problem and why current solutions fail]
* **Context & Constraints:** [Existing codebase invariants, technical stack strengths, and environment boundaries]

---

## 2. Core Conceptual Model (The Product Thesis)
* **Governing Thesis:** [1-sentence conceptual model that defines how the product works]
* **Anti-Goals (What We Will Not Build):** [Features or complexity intentionally excluded to keep the product sharp]

### Conceptual & State Diagram
[Mermaid diagram showing how User Mental Model <-> UI Workspace <-> State/Data Model connect]

---

## 3. Information Architecture & Hierarchy
* **Primary Workspace (Core Value — 80% Focus):**
  * [Workspace / View]: [Primary user actions, immediate feedback loop, key data shown]
* **Supporting Chrome & Plumbing (Tucked Away):**
  * [Background / Secondary System]: [How config, sync, permissions, or edge cases stay out of the way]
* **Key Workflow Adjacencies:**
  * [Action A] <-> [Action B]: [Why they live together in the same context]

---

## 4. User Journey & State Choreography
1. **Cold Start / Threshold (0 Items):** [How a new user starts immediately without friction]
2. **Core Loop (Reflection-in-Action):** [User action -> immediate system response -> refinement]
3. **Scale State (1,000–10,000+ Items):** [How navigation, filtering, or density adapts at scale]
4. **Edge & Failure States:** [How offline, latency, or errors are handled gracefully]

---

## 5. Design Critique Resolutions
* **Risk / Tension 1:** [Key flaw or trade-off uncovered during critique] -> **Design Resolution:** [How we solved it]
* **Risk / Tension 2:** [Key flaw or trade-off uncovered during critique] -> **Design Resolution:** [How we solved it]

---

## 6. Vertical Build Slices (Implementation Sequence)
1. **Slice 1 — The Core Loop (Data + State + Unstyled Functional Flow):** [Prove the conceptual model works end-to-end]
2. **Slice 2 — Thresholds & Scale (Empty State, Search/Density, Edge Cases):** [Make the flow resilient]
3. **Slice 3 — Craft & Polish (Hierarchy, Motion, Keyboard Physics):** [Refine the tactile product experience]
```
