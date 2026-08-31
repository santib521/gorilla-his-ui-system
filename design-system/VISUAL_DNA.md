# Gorilla HIS Visual DNA — Product Craft Standard v1.0

> This document defines the visual character that makes Gorilla HIS recognizable without its logo. It is a design authority, not a styling suggestion.

## 1. Design Ambition

Gorilla HIS is not an admin template with hospital data inserted into it. It is a precision work instrument for clinicians and hospital operations.

Target quality:
- **Purpose-built** — composition follows the clinical/operational decision, not a generic dashboard grid.
- **Quiet confidence** — premium comes from proportion, alignment, typography and restraint, not decoration.
- **High-density clarity** — more useful information with less visual noise.
- **Clinical gravity** — safety signals are unmistakable; everything else stays calm.
- **Crafted, not assembled** — a page must feel authored as one composition, not built from a pile of interchangeable cards.

A successful page should still feel like Gorilla HIS if the logo, module name and brand color are temporarily hidden.

## 2. The Gorilla Signature

### 2.1 One continuous work surface
The primary workspace is a continuous canvas. Do not turn every information group into a floating card.

Use hierarchy in this order:
1. typography and alignment;
2. whitespace rhythm;
3. subtle dividers / tonal surface shift;
4. border only when enclosure has functional meaning;
5. shadow only for elevation that physically overlays another layer (menu, drawer, modal).

### 2.2 Precision rail, not heavy app chrome
Navigation is compact and visually subordinate to the work. The work surface owns the screen.

- Product identity is small and controlled.
- Active navigation uses a precise indicator/tonal treatment, not a large filled pill.
- Module navigation may use a narrow rail plus contextual secondary navigation where appropriate.
- Avoid a large dark rectangle occupying visual weight simply because a sidebar is conventional.

### 2.3 Information has a spine
Every page needs a strong alignment spine: key labels, numbers, tables, timelines and actions share deliberate baselines/columns. Random independent boxes are prohibited.

### 2.4 Numbers are instruments
Operational/clinical numbers must behave like instrument readings:
- tabular/mono numerals where alignment matters;
- unit visually subordinate but attached to value;
- trend and threshold context close to the number;
- never giant marketing numbers;
- never color a number unless the color carries approved meaning.

### 2.5 Action hierarchy is quiet until action is required
Primary action is visually clear but compact. A screen must not be covered with equal-weight buttons.
- routine actions = text/quiet controls;
- primary workflow action = one controlled accent;
- urgent patient-safety action = semantic treatment with icon + label + context.

## 3. Premium Craft Rules

### 3.1 Composition before components
Before choosing components, define:
- **Decision Question:** what must the user know/decide in the first 5 seconds?
- **Primary Evidence:** what information proves that situation?
- **Exception:** what requires attention now?
- **Action:** what is the next safe operational action?
- **Secondary Evidence:** what supports deeper investigation?

The page composition must answer these in this order. Component availability must not dictate the hierarchy.

### 3.2 Asymmetry with discipline
Do not default to 3 equal cards, 4 equal cards, 50/50 columns, or repeated rectangles. Use unequal proportions when information importance is unequal. Alignment must remain rigorous.

### 3.3 Surface discipline
Default workspace surface is flat. Sections can be separated by spacing, rule lines or a very small tonal change. Rounded bordered containers are reserved for real bounded objects, not every section.

### 3.4 Border and radius discipline
Repeated medium-radius bordered cards create generic SaaS appearance. Do not use them as the page grammar. Radius communicates objecthood; if an area is simply part of the workspace, it usually should not be rounded.

### 3.5 Shadow discipline
No ambient card shadows in operational pages. Shadow is for overlays/elevation only.

### 3.6 Color discipline
80–90% of the screen should read as neutral ink/surface. Brand indigo is a controlled interaction accent, not a wash. Teal is brand mark only. Clinical semantic colors are meaning, never decoration.

### 3.7 Typography rhythm
Typography creates hierarchy before containers do.
- Page identity: compact, confident, never poster scale.
- Section label: small/precise, often paired with context or timestamp.
- Body/data: optimized for scanning.
- Metadata: quieter, but not low-contrast enough to impair use.
- Avoid uppercase everywhere; use it sparingly for micro labels only.

## 4. Anti-Template Test — Mandatory

Before PASS, ask:
1. Could this screenshot plausibly be a CRM, fintech, logistics SaaS or generic admin template after changing labels? **If yes → FAIL.**
2. Is the page mainly a collection of rounded rectangles? **If yes → FAIL.**
3. Are major regions equal-sized because a grid was easy, rather than because information importance is equal? **If yes → FAIL.**
4. Does removing color destroy hierarchy? **If yes → FAIL.**
5. Does the primary operational story remain obvious in grayscale? **If no → FAIL.**
6. Is there a clear authored focal path: situation → evidence → exception → action? **If no → FAIL.**
7. Is any AI capability visually themed differently from the HIS? **If yes → FAIL.**

## 5. Archetype: Command / Operational Intelligence

The Command Center is a decision surface, not a dashboard gallery.

### First viewport story
The first viewport must communicate:
1. current hospital operating state;
2. what changed / what is likely to happen;
3. the bottleneck or exception;
4. evidence behind it;
5. the next coordinated action.

### Composition grammar
- **Situation line:** a compact authored summary combining state, time, sync and scenario context.
- **Instrument band:** a restrained row of key measures integrated into the surface; not detached KPI cards.
- **Operational field:** the dominant area — flow, queue, capacity, timeline, matrix or trend chosen from the decision question.
- **Exception lane:** alerts/exceptions embedded adjacent to the evidence they qualify.
- **Decision rail:** narrow, ordered actions with rationale and ownership; not a promotional recommendation card.
- **Detail layers:** secondary tables/timelines below or in contextual drill-down.

The operational field must be visually dominant. AI prediction is annotation/evidence within it, not the hero.

## 6. Gold Standard Rule

No component, layout master or pattern may call itself **Premium**, **World-class**, **Gold**, or **Signature** solely because it passes Factory Gate.

Promotion requires:
- rendered visual review;
- Human Design Approval;
- Anti-Template Test PASS;
- comparison against at least one relevant real Gorilla HIS reference when available;
- evidence that the page was designed around a decision/workflow rather than a generic component grid.

Until Human Design Approval exists, label the artifact **Candidate**, never Master/Gold Standard.

## 7. Extraction Rule

World-class pages come first; reusable primitives are extracted second.

`Human-approved reference page → identify recurring visual grammar → extract component/pattern → Factory enforcement`

Do not reverse this into `generic components → assemble page → declare premium`.
