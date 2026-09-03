# Gorilla HIS Visual DNA — Product Craft Standard v2.5

> Highest visual-design authority. Gorilla HIS is a precision clinical/operational instrument, not an admin template. Premium means controlled proportion, typography, density, interaction craft and authored workflow composition.

## 1. Design Ambition
Target: Purpose-built, quiet confidence, high-density clarity, clinical gravity, crafted-not-assembled, desirable to use, refined at touchpoint level.

A successful page still feels Gorilla HIS if logo/module/brand color are hidden.

## 2. Premium Mental Model
BMW and Apple/iPhone are quality benchmarks, not visual references to copy.

`BMW cockpit discipline × Apple interaction discipline × Hospital-grade information density × Gorilla HIS continuity`.

Translate:
- Proportion → information hierarchy/composition/navigation footprint
- Cockpit → clinical/operational workspace
- Control feel → buttons/filters/selectors/task actions
- Typography → reading priority/Thai readability/numerical instrumentation
- Fit & finish → alignment/rhythm/icon/control detail
- Brand DNA → recognizable Gorilla continuity

## 3. Gorilla Shell Continuity — LEFT NAVIGATION HARD RULE
The default Gorilla HIS product shell preserves the **left-side menu/navigation bar**.

- Keep it visually subordinate to the task.
- Compact/collapsible rail behavior is allowed and encouraged.
- Current module selection/orientation must remain obvious.
- Module workspace owns the majority of useful viewport width.
- Do not replace the Gorilla left menu with a top-only navigation simply because a supplied benchmark uses one.
- A Human-approved Gold Standard may explicitly supersede this rule.

## 4. Authored Work Surface
Do not turn every information group into a card. Preferred hierarchy tools:
1 typography/alignment;
2 spacing/proportion;
3 tonal surface shift;
4 subtle divider;
5 bounded container only when object behaves as one object;
6 shadow only for real elevation.

Every page needs a visual spine:
`Context → Situation → Evidence/Work → Exception → Next Action → Detail`.

## 5. Navigation Precision
Navigation must never visually dominate the task. Avoid giant dark sidebars. Preserve useful width through compact rail/collapse behavior while retaining left-side continuity.

Do not allow sidebar + topbar + tabs + secondary navigation to all compete visually.

## 6. Benchmark No-Regression — HARD GATE
When a user supplies a credible reference/mockup, first identify the visual/product qualities it demonstrates well: hierarchy, scanability, density, rhythm, action clarity, status encoding, navigation efficiency, **typographic readability** and polish.

A new Gorilla candidate must not be materially worse in those demonstrated qualities without a documented workflow/safety reason.

Target:
`Preserve proven strengths → Correct business/UX defects → Exceed reference`.

Do not defend a weaker design by citing Factory rules.

## 7. Space Utilization
Premium is not empty space. Whitespace must improve comprehension.

FAIL when:
- important work is compressed while large blank regions remain;
- fixed max-width/template columns waste desktop space;
- actions are detached from the objects they affect;
- equal cards/grids define unequal work.

## 8. Surface Architecture
S0 Canvas: low-contrast neutral environment.
S1 Work Surface: primary reading/working plane.
S2 Instrument Surface: compact bounded readings/controls.
S3 Elevated Surface: menus/drawers/inspectors.
S4 Semantic Surface: critical/warning/normal/info.

Depth communicates hierarchy/interactivity, not decoration.

## 9. Thai Typography Craft — SARABUN REFERENCE AUTHORITY
Typography is primary hierarchy and a **hard usability gate**.

The user-approved HTML reference supplied on 2026-09-03 is the current Thai typography authority for Gorilla HIS operational mockups. Its defining typography is **Sarabun for Thai/normal UI text**, with **JetBrains Mono only for numeric/identifier instrumentation**, and a compact 13px base density.

### 9.1 Primary font family — HARD RULE
Preferred product typography:

`font-family: "Sarabun", "Leelawadee UI", Tahoma, sans-serif;`

Numeric/identifier instrumentation may use:

`font-family: "JetBrains Mono", Consolas, monospace;`

Rules:
- **Sarabun is the visual target for Thai UI**, not Tahoma.
- Tahoma is fallback only; it must never be treated as the design target.
- Do not use monospace for Thai prose, patient names, labels or status text.
- Do not choose another Thai font merely because it is available unless Human Review approves it as equal/better.
- Production Angular should bundle/serve the approved product font through the application asset pipeline.
- Self-contained Factory mockups must not silently depend on an external CDN. If Sarabun cannot be embedded/served within the mockup environment, use the fallback stack but mark typography as `NOT FULLY VERIFIED` until rendered with Sarabun in an approved environment.

### 9.2 Visual character to preserve
The approved Sarabun reference feels:
- open and familiar in Thai;
- narrow enough for dense hospital tables without looking condensed;
- clean at 12–14px;
- readable with medium weight rather than oversized type;
- calm across long Thai labels;
- compatible with English workflow terms such as Worklist, Consult, Request, Active, Consent and Alive;
- compatible with dates, HN/VN, currency, score and quota values.

The target is **compact readability**, not large typography.

### 9.3 Operational size scale — REFERENCE-DERIVED
Use the approved HTML density as the default desktop baseline:
- Body/root: **13px**.
- Main worklist/table body: **12–13px** (`text-xs` style density is acceptable with Sarabun).
- Patient name / primary work object: **13px**, usually weight 600–700 depending hierarchy.
- Table header: **12–13px**, weight 600.
- Tabs / worklist section tabs: **12px**, weight 600.
- Left navigation item: **12–13px**, weight 500; active item may use 600.
- Form label / field text / button label: **12–13px**.
- Page/workspace heading: **14px** (`text-sm`) and weight 700.
- Executive/major section heading: **16px** (`text-base`) where justified.
- KPI main number: **20px** (`text-xl`) when it is the dominant reading.
- KPI sub-number: **14px** (`text-sm`).
- Secondary explanation/metadata: **11px**.
- Very-low-priority shell/version/subtitle metadata: **10px** only.

Do **not** force 14–15px for every operational row. Density comes from Sarabun's readable form, disciplined weight, spacing and contrast.

### 9.4 Weight discipline
Preferred weights:
- 400 = normal body/readable detail;
- 500 = navigation/default emphasized label;
- 600 = table header, tabs, active navigation, important labels/actions;
- 700 = page heading, patient/critical primary identity when needed, KPI emphasis.

Avoid 300/light for operational Thai text. Do not make the whole interface semibold/bold.

### 9.5 Line height and vertical rhythm
- Dense operational body: **1.35–1.5** line-height.
- Table cells normally use compact padding roughly equivalent to 10–12px vertical only when information density justifies it.
- Multi-line rich cells need enough leading for Thai upper/lower marks.
- Reduce decorative padding/card height before shrinking essential text below the reference scale.
- Large whitespace around small Thai text is a typography/composition failure.

### 9.6 Contrast and color
Reference behavior:
- body text uses strong slate/dark-neutral contrast;
- secondary text uses muted slate but remains readable;
- semantic green/amber/blue highlights status and action, not ordinary prose;
- white work surfaces on a soft slate canvas support reading;
- dark shell text must maintain high contrast.

Never compensate for weak typography with stronger color alone.

### 9.7 Mixed Thai / English / numbers
- Thai remains Sarabun.
- Dates, HN/VN, amounts, quota counts and scores may use JetBrains Mono/Consolas selectively.
- `font-mono` is an instrument treatment, not a body style.
- Mixed Thai/English labels should remain visually balanced; English uppercase is secondary unless it is an established operational label.
- Use tabular numerals when side-by-side comparison matters.

### 9.8 Component-specific typography grammar
Use the approved reference grammar unless workflow needs otherwise:
- Top product title: 14px bold; subtitle 10px muted.
- Role selector/profile: 10–12px.
- Sidebar section caption: 11px uppercase/letter-spaced; menu 12px medium.
- Worklist KPI captions: 11–12px; main KPI 20px; active-card sublabels 10px and values 14px.
- Worklist toolbar/search/filter: 12px.
- Worklist table: 12px body/header; patient identity may rise to 13px/600–700.
- Modal/form container: 12px body; modal heading 14px bold; supporting note 10–11px.
- Status chip/type label: 10px when short and secondary; do not use 10px for patient identity, next action or substantive clinical/social-work evidence.

### 9.9 Density rule — IMPORTANT
Do not confuse readability with making everything larger.

The approved reference demonstrates that **Sarabun 13px base + strong hierarchy + compact spacing** can be more readable than a larger but poorly chosen font.

When information feels hard to read, check in this order:
1. font family;
2. font weight;
3. contrast;
4. line-height;
5. alignment/grouping;
6. padding/whitespace;
7. only then increase font size.

### 9.10 Rendered Typography Gate — MANDATORY
Before Human Visual Review, render the primary worklist at representative desktop scale and compare it with the approved Sarabun HTML reference.

Reviewer must answer:
1. Does the candidate visibly use Sarabun or an approved visually equivalent Thai font?
2. Is Thai text at least as crisp/readable as the reference without being larger everywhere?
3. Does the candidate preserve the reference's compact density?
4. Are patient identity and primary actions more prominent than metadata?
5. Are table header, navigation and forms clearly differentiated by weight/contrast rather than excessive size?
6. Are numbers/identifiers treated as instruments without making Thai text monospaced?
7. Does the rendered page remain calm at real desktop scale?

Any `No` = **FAIL — TYPOGRAPHY / READABILITY**.

If Sarabun cannot actually render in the test environment, result is `BLOCKED/NOT FULLY VERIFIED — APPROVED FONT NOT RENDERED`; do not call Typography PASS based only on CSS declaration.

## 10. Shape Language
Structural regions: low radius/square.
Interactive controls: moderate radius with crafted states.
Floating contextual objects: larger radius/elevation.
Repeated rounded rectangles everywhere = generic SaaS signature → FAIL.

## 11. Color and Light
Disciplined neutrals + semantic color. Premium is controlled saturation/contrast, not more color.

## 12. Motion & Micro-interaction
Motion explains causality. Respect reduced motion. No decorative perpetual animation.

## 13. Composition Before Components
Before choosing components define:
- Decision Question
- Primary Evidence
- Exception
- Primary Action
- Secondary Evidence
- Navigation footprint
- Space utilization plan
- Progressive disclosure plan

Then compose the page.

## 14. Progressive Disclosure
Intake shows only what is needed to classify/validate/accept work. Deeper functions appear in the case workspace. Rare detail belongs in contextual drawer/accordion/inspector when appropriate.

## 15. Component Jewelry Standard
Buttons/tabs/fields/selectors/badges/table headers/focus/hover/pressed/selected/disabled/validation/loading/empty/error must look like one product.

## 16. Numbers as Instruments
Use tabular numerals where useful; unit subordinate but attached; threshold/delta/time near value; semantic color only.

## 17. Anti-Template Test
Ask:
1 Could this be CRM/fintech/logistics after labels change? yes=FAIL.
2 Is page mainly sidebar + generic rounded cards? yes=FAIL.
3 Are major regions equal because grid was easy? yes=FAIL.
4 Does removing color destroy hierarchy? yes=FAIL.
5 Is authored focal path unclear? yes=FAIL.
6 Does it feel AI/template generated? yes=FAIL.
7 Is it tidy but lifeless? yes=FAIL Premium Craft.
8 Is Thai harder to read than the human-approved Sarabun reference? yes=FAIL Typography.

## 18. Desirability Test
Premium Candidate reaction: “precise, expensive, calm, intentionally designed — I want to use it.”

Clean/neat/usable/professional alone is not Premium.

## 19. Responsive / Adaptive Density
Inspect representative desktop and narrower workspace. Left navigation may compact/collapse, context remains visible, primary action remains discoverable and high-value content uses width intelligently.

Typography may adapt slightly but must preserve the Sarabun reference character, hierarchy and minimum readability.

## 20. Independent Premium Design Review
`design-system/PREMIUM_PRODUCT_DESIGN_GATE.md` is mandatory after build.

`Functional PASS + Design FAIL = Factory FAIL`.
`Functional PASS + Typography FAIL = Factory FAIL`.

## 21. Gold Standard Rule
No artifact may call itself Premium/Gold/Signature solely because Factory Gate passes. Promotion requires rendered visual review, Human Design Approval, Anti-Template PASS, Typography/Readability PASS, Desirability PASS, Gorilla continuity evidence and workflow-authored composition.

## 22. Extraction Rule
`Human-approved reference → extract Visual Grammar → components/patterns → Factory enforcement`.
Never reverse into `generic components → assemble → declare premium`.
