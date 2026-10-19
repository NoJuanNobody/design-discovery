---
name: design-discovery
description: >-
  Apply design thinking and structured product discovery to software
  applications, features, and product design. Use when the user asks to run
  design discovery, product discovery, apply design thinking to an app or idea,
  frame a product problem, explore conceptual models, critique a product flow,
  or use "/design-discovery" to figure out what to design and build before
  writing code.
---

# Design Discovery: Design Thinking for Product Design

This skill applies rigorous **Design Thinking** to **software product design and application discovery**. It bridges the gap between a raw idea (or an existing app that feels unfocused) and a clear, build-ready product design.

Instead of jumping straight to UI screens or feature backlogs—and instead of generic sticky-note brainstorming—**Design Discovery** works through **Problem–Solution Co-Evolution** (Nigel Cross / Donald Schön): framing the real human problem, mapping context and constraints, exploring divergent conceptual models, stress-testing the design through critique, and converging on a coherent product architecture.

For deeper frameworks, mental models, and the product critique rubric, see [references/design-thinking-framework.md](./references/design-thinking-framework.md).

---

## Operating Modes

Choose the mode that matches where the user is in the product lifecycle:

1. **Full Design Discovery (Default for new products, features, or vague ideas):**
   Walk through Phases 1–5 below, pausing at **Phase 3 (Conceptual Direction)** and **Phase 4 (Design Critique)** to align with the user (`ask_question` when available).
2. **Product Design Critique (For existing apps, screens, flows, or PRs):**
   Inspect the current product/codebase, infer its underlying conceptual model, and run a sharp, constructive **Design Critique** using the rubric in [references/design-thinking-framework.md](./references/design-thinking-framework.md). Focus on user mental models, information hierarchy, flow friction, and feature bloat.
3. **Problem Reframing & Concept Workshop (For bloated or stuck products):**
   Step back from the feature list, reframe the core user problem, and pitch 2–3 distinct **Conceptual Models** so the user can choose a single unifying product thesis and cut what doesn't belong.

---

## The 5-Phase Design Discovery Workflow

### Phase 1: Problem Framing & Context Discovery (Empathize & Define)

Before sketching solutions, uncover the real problem and the environment the product lives in.

1. **Reframe the "Wicked Problem":**
   * What is the user actually trying to accomplish (Jobs-to-be-Done), and what makes it painful, slow, or fragile today?
   * Distinguish **symptoms** (what the user asks for) from the **root problem** (why they need it).
2. **Audit the Context & Constraints (If a codebase or product already exists):**
   * Inspect the existing app, data models, technical stack, and workflows.
   * Identify **Hard Constraints** (invariants, data structures, platform boundaries, latency) vs. **Design Opportunities** (native strengths of the stack—like instant local state, streaming, or real-time sync—that can make the UX feel effortless).
3. **Map Core Value vs. Supporting Chrome:**
   * **Primary Workspace (Core Value):** Where does the user spend 80% of their time creating or consuming value?
   * **Supporting Plumbing (Secondary Chrome):** What configuration, settings, auth, and edge-case handling must be tucked out of the way so it never competes with the primary task?

### Phase 2: Precedent & Pattern Research (Cross-Domain Inspiration)

Do not just copy direct competitors' UI. Look at **how analogous problems are solved structurally**:

* Identify **2–3 Reference Products or Interaction Patterns**—including at least one from an adjacent domain (e.g., how linear issue trackers handle keyboard speed, how audio/video editors handle timeline state, how multiplayer canvases handle presence, or how consumer apps handle zero-friction onboarding).
* Extract the **behavioral pattern** (how state, feedback, density, or navigation works), not the visual skin.

### Phase 3: Divergent Ideation & The Core Conceptual Model (Ideate)

Use **abductive reasoning** (*"What could be?"*) to generate **2–3 genuinely distinct Product Directions / Conceptual Models** (also known in design theory as the *Parti*—the central organizing idea):

For each option, define:
* **The Conceptual Model (1-Sentence Thesis):** What is the mental model the user holds in their head? (e.g., *"An inbox where every item is a runnable workflow"* vs. *"A spatial canvas where documents and data live side-by-side"*).
* **How the Loop Works (Data $\rightarrow$ Interaction $\rightarrow$ Feedback):** How the underlying data model maps directly to what the user sees and manipulates.
* **Trade-offs & Anti-Goals:** What this direction intentionally leaves out to stay simple and sharp.

> **Interactive Checkpoint:** Present the problem synthesis and the 2–3 Conceptual Models to the user. Use `ask_question` (if available) or a direct prompt to choose or combine a direction before detailing the design.

### Phase 4: Reflection-in-Action & Design Critique (Prototype & Stress-Test)

Once a conceptual direction is chosen, stress-test it as if leaning over a drafting table with the user (*Reflection-in-Action*):

1. **Mental Model Alignment:** Can a new user understand how the product works in 5 seconds without reading a tutorial?
2. **Journey & Thresholds:** What happens in the first 10 seconds (**0-item cold start**)? What happens in the **core daily loop**? What happens at **10,000 items** (high-density scale)?
3. **Hierarchy & Noise Check:** Is secondary plumbing (settings, metadata, status chrome) cluttering the primary workspace?
4. **Dead-End & Edge-Case Check:** Where does the user get stuck, lose context (e.g., nested modals, page reloads), or wait on slow feedback?
5. **System Honesty:** Does the underlying data schema and technical architecture cleanly support this UX without brittle workarounds?

### Phase 5: The Product Design Brief (Converge & Specify)

Deliver a clear, actionable **Product Design & Discovery Brief** (as an artifact or project markdown file) using the template in [references/design-thinking-framework.md](./references/design-thinking-framework.md):

1. **Problem Framing & Target Outcome** (The reframed user problem + success criteria)
2. **Core Conceptual Model & Anti-Goals** (The governing thesis + Mermaid diagram of the user mental model and system state)
3. **Information Architecture & Spatial Hierarchy** (Primary workspace vs. secondary utilities, key adjacencies)
4. **End-to-End User Flows** (Cold start / onboarding $\rightarrow$ core interaction loop $\rightarrow$ scale/edge states)
5. **Vertical Build Slices** (How to build and validate the core loop first before polishing secondary features)

---

## Quality Checklist

Before completing a Design Discovery session, verify:
- [ ] The **core problem** is framed around human intent and workflow friction, not just a list of requested features.
- [ ] The **Conceptual Model** can be explained in one sentence and drawn in 3–5 boxes.
- [ ] **Primary Workspace** (core value) and **Secondary Chrome** (settings/plumbing) are cleanly separated.
- [ ] The design accounts for **0 items (empty state)**, **1 item (first run)**, and **10,000 items (scale)**.
- [ ] Data model, state management, and UI flows align vertically with no magical/unbuildable leaps.
