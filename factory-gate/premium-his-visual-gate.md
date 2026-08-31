# Gorilla HIS — Premium HIS Visual Gate v3.0

This gate evaluates rendered product quality. It supplements functional QA and clinical safety rules.

**Code compliance alone cannot PASS Premium.** When rendering is unavailable, mark `VISUAL REVIEW LIMITATION`.

## VG-01 Product Character
Question: Does the page feel purpose-built for hospital work rather than generic software?

PASS:
- clinical/operational seriousness;
- crafted product identity;
- dense but controlled information;
- no AI-showcase visual language.

## VG-02 Decision Hierarchy
Question: Can the intended user grasp the situation/decision within ~5 seconds?

PASS when:
`Situation → Evidence → Exception → Action` is visually obvious before secondary detail.

## VG-03 Icon Language
PASS:
- Font Awesome semantic mapping from `icon-rules.md`;
- no Emoji UI;
- no external Font Awesome CDN/Kit;
- no unnecessary custom icon where approved mapping exists.

## VG-04 Authored Composition
PASS:
- proportion follows information importance;
- composition is not an equal-card/equal-column convenience grid;
- the page has a deliberate focal path and alignment spine.

FAIL:
- repeated boxes are the architecture;
- a generic dashboard template would produce essentially the same screenshot.

## VG-05 Surface Architecture
Evaluate S0 Canvas / S1 Work / S2 Instrument / S3 Elevated / S4 Semantic.

PASS:
- depth/tonal change communicates hierarchy/interactivity;
- work surface remains dominant;
- elevated objects actually behave as elevated objects.

FAIL:
- flat white + hairlines everywhere;
- shadow/card treatment everywhere;
- decorative “luxury” surfaces without functional hierarchy.

## VG-06 Typography Craft
PASS:
- page title is controlled;
- technical labels, values, units, metadata and narrative have distinct roles;
- numerical comparison is optically precise;
- typography creates hierarchy before container decoration.

## VG-07 Instrument Quality
Operational metrics should feel like readings, not spreadsheet cells.

PASS when decision-relevant context is integrated, e.g.:
- target / threshold;
- delta;
- micro-trend;
- forecast;
- time-to-threshold;
- safe operating range.

Not every metric requires every element.

## VG-08 Color Discipline
PASS:
- refined neutral majority;
- Precision Indigo used for interaction/intelligence accent;
- Teal used with brand restraint;
- clinical semantic colors retain strict meaning;
- saturation is controlled.

## VG-09 Data Visualization Quality
PASS when visualization answers a decision question.

Preferred families when relevant:
- micro sparkline;
- threshold/capacity rail;
- Operational Flow Spine;
- forecast band;
- time-to-threshold;
- bed/queue/matrix field.

FAIL when charts exist only because “dashboard should have charts.”

## VG-10 Interaction Craft
PASS:
- hover/pressed/selected states feel deliberate;
- task/scenario/state transition explains causality;
- motion is restrained;
- controls feel like product controls, not prototype buttons.

## VG-11 AI / Intelligence Integration
PASS:
- prediction/recommendation is connected to operational evidence;
- recommendation states projected impact/rationale where Blueprint supports it;
- AI is not a separate visual theme.

Preferred grammar:
`Current state → trajectory → expected threshold → intervention → projected impact`.

## VG-12 Information Density
PASS:
- first viewport contains meaningful work;
- useful density is preserved;
- visual hierarchy prevents cognitive overload.

Premium does not mean excessive whitespace.

## VG-13 Anti-Template Test
FAIL if changing labels could plausibly turn the screenshot into generic CRM/fintech/logistics/admin software.

Also FAIL if:
- major regions are equal because grid is easy;
- repeated medium-radius cards dominate;
- hierarchy depends mainly on brand color.

## VG-14 Dryness / Barren Test
FAIL when the interface feels:
- sterile;
- bureaucratic;
- unfinished;
- like a styled spreadsheet;
- like a wireframe with production typography.

Premium restraint must still contain product feeling through:
- proportion;
- surface hierarchy;
- typography;
- instrumentation;
- visualization;
- interaction detail.

## VG-15 Desirability Test
Human-facing question:
**Does this feel precise, calm, expensive and intentionally designed — something a professional would want to use repeatedly?**

PASS cannot be earned by gradients/glass/shadows alone.

Evidence should include:
- coherent visual identity;
- refined material/surface feel;
- custom workflow-specific visual grammar;
- tactile control hierarchy;
- detail/fit-and-finish;
- meaningful delight.

If the strongest reaction is only “clean / neat / usable / professional,” keep status **Candidate**.

---

# Quality Benchmark Tests

## BMW Test
Same feature set does not imply same design quality.

Ask:
“What makes this page materially more designed than another HIS with identical functions?”

Valid evidence:
proportion, material/surface, instrumentation, control feel, data visualization, motion, fit-and-finish, coherence.

Color/logo/icons alone are insufficient.

## iPhone Test
Ask:
- Is it still refined after decoration is reduced?
- Does depth improve comprehension?
- Does every interaction feel deliberate?
- Is useful complexity simplified rather than merely hidden?

A page that is flashy fails. A page that is barren also fails.

---

# Command Center / Operational Intelligence Interpretation

Do not use a fixed layout formula.

The page should normally make these understandable in the first viewport:
1. current operating state;
2. trajectory / time-to-threshold;
3. bottleneck;
4. evidence;
5. intervention / projected impact.

Potential visual primitives:
- Hospital Instrument Band;
- Operational Flow Spine;
- Capacity / threshold visualization;
- embedded exception;
- Intelligence Intervention;
- contextual timeline;
- scenario transition.

`premium-operational-layout.html` is deprecated and does not provide Premium evidence.

---

# Result

For each gate record:
`PASS / FAIL / N/A / VISUAL REVIEW LIMITATION`

P0 Design FAIL:
- VG-01
- VG-02
- VG-08 when semantic safety is violated
- VG-11 when AI theme overrides HIS language
- VG-13

Premium Candidate cannot be recommended for Human Approval if VG-05, VG-06, VG-07, VG-10, VG-14 or VG-15 materially fail.

Only Human Design Approval may confirm Premium quality.
