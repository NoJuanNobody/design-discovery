# Design Discovery Skill

Apply rigorous **Design Thinking** and structured **product discovery** to software applications, features, and product design.

Instead of jumping straight from a prompt to UI screens or feature backlogs, **Design Discovery** works through **Problem–Solution Co-Evolution** (Nigel Cross / Donald Schön / Horst Rittel / Christopher Alexander): framing the real human problem, auditing stack constraints, exploring divergent conceptual models (*Parti*), stress-testing the flow through design critique, and converging on vertical build slices.

## Installation

Install globally using [`npx skills`](https://skills.sh):

```bash
npx skills add NoJuanNobody/design-discovery -g
```

Or install into a single project:

```bash
npx skills add NoJuanNobody/design-discovery
```

## Operating Modes

1. **Full Design Discovery** *(Default for new products, features, or raw ideas)* — Walks through a 5-phase discovery loop with interactive checkpoints at **Phase 3 (Conceptual Direction)** and **Phase 4 (Design Critique)**.
2. **Product Design Critique** *(For existing apps, screens, flows, or PRs)* — Audits the current product against the **10-Point Product Design Critique Rubric** (mental model clarity, subtraction test, bolted-on feature check, canvas-to-chrome ratio, and 0 / 1 / 10,000 scale extremes).
3. **Problem Reframing & Concept Workshop** *(For bloated or unfocused products)* — Steps back from the feature backlog, reframes the core user problem, and pitches 2–3 distinct unifying **Conceptual Models**.

## The 5-Phase Discovery Workflow

1. **Problem Framing & Context Discovery** — Distinguish symptoms from root workflow friction, audit stack constraints & opportunities, and separate the **Primary Workspace (80% core value)** from **Supporting Plumbing (secondary chrome)**.
2. **Precedent & Pattern Research** — Extract behavioral and state patterns from best-in-class products across adjacent domains.
3. **Divergent Ideation & Core Conceptual Model** — Generate 2–3 distinct product theses (*Data $\rightarrow$ Interaction $\rightarrow$ Feedback*) with explicit anti-goals.
4. **Reflection-in-Action & Design Critique** — Stress-test cold start (`0` items), first run (`1` item), high-density scale (`10,000` items), dead-end flows, and schema-to-screen honesty.
5. **The Product Design Brief** — Deliver an actionable spec organized into vertical build slices.

## Included Files

- [`SKILL.md`](./SKILL.md) — Core instructions, operating modes, and 5-phase discovery workflow.
- [`references/design-thinking-framework.md`](./references/design-thinking-framework.md) — Design Thinking theory matrix, the 10-Point Product Design Critique Rubric, and the Product Design Discovery Brief template.

## Usage

Trigger in your agent conversations via:
- `/design-discovery`
- *"Run design discovery on this app idea..."*
- *"Critique the product flow and conceptual model of this repo..."*
- *"Help me figure out what to design and build before writing code."*
