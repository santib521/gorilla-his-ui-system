# Gorilla HIS Visual DNA — Product Craft Standard v2.4

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

## 9. Thai Typography Craft — HUMAN-APPROVED REFERENCE BASELINE
Typography is primary hierarchy and a **hard usability gate**. The human-approved worklist reference supplied on 2026-09-03 is the current readability floor for Thai operational UI.

### 9.1 Visual character to preserve
Thai UI text should feel:
- open, familiar and immediately readable;
- neither condensed nor overly geometric;
- medium stroke contrast with clear Thai loops/counters;
- calm at dense worklist scale;
- strong enough to scan without looking bold everywhere;
- visually compatible with Latin letters, dates, HN/VN, currency and numeric instruments.

Do **not** use a fashionable font merely because it looks modern. If Thai readability is worse than the approved reference, the candidate fails visual review.

### 9.2 Mockup font stack
For self-contained browser mockups, use a Thai-safe system stack that approximates the approved reference:

`font-family: Tahoma, "Leelawadee UI", Arial, sans-serif;`

Do not fetch Google Fonts/CDN fonts in Factory mockups. Do not rely on an unbundled font that changes dramatically across machines.

For production Angular, a bundled product font may replace this stack only after rendered Thai comparison proves readability is equal or better than the approved reference.

### 9.3 Operational size baseline
At normal desktop density:
- Main operational/table body: **14–15px**.
- Patient name / primary work object: **15px** minimum, usually weight 600.
- Left-navigation item: **14–15px**, active item weight 600.
- Table header / tab / primary filter label: **14px**, weight 600.
- Primary button/action label: **14px** minimum, weight 600 where needed.
- Secondary metadata such as HN/VN/source/date subline: **12.5–13px**.
- Low-priority technical metadata may use **12px**.
- **11px is exceptional only** and must never carry patient identity, operational status, queue meaning, consent state, next action or decision evidence.

A designer may increase sizes when viewing distance or screen density requires it. It should rarely go smaller than this baseline.

### 9.4 Weight discipline
Preferred operational weights:
- 400 = normal reading text;
- 600 = patient identity, table header, active navigation, primary decision label;
- 700 only for selective high-emphasis totals/headings.

Avoid 300/light Thai body text. Avoid synthetic ultra-bold Thai text. Avoid making every label semibold because hierarchy then disappears.

### 9.5 Line-height and vertical rhythm
- Dense Thai operational rows normally target line-height **1.35–1.5**.
- Multi-line rich cells need enough leading so upper/lower Thai marks do not visually collide.
- Do not vertically squeeze Thai text to achieve density; reduce decorative padding first.
- Patient row height must be driven by decision information, not oversized whitespace.

### 9.6 Contrast and color
- Primary operational text must use strong neutral contrast, not pale gray.
- Secondary metadata may be muted but must remain comfortably readable.
- Do not use low-contrast green/blue/gray text for ordinary body copy merely to look refined.
- Color is semantic support, not a substitute for readable weight/contrast.

### 9.7 Mixed Thai / English / numbers
- Dates, HN/VN, quantities and money should align cleanly with Thai text.
- Use tabular numerals when comparison matters.
- Monospace may be used selectively for identifiers/dates, never as the dominant Thai UI font.
- English uppercase should not visually overpower Thai labels.

### 9.8 Rendered Typography Gate — MANDATORY
Before Human Visual Review, inspect the rendered primary worklist at representative desktop scale and compare against the approved reference.

Reviewer must answer:
1. Can Thai labels be read instantly without zooming?
2. Are patient name and primary status more prominent than metadata?
3. Are table headers clear without appearing heavy?
4. Does dense information remain calm rather than cramped?
5. Are Thai marks/loops/counters clean at actual rendered size?
6. Is the candidate at least as readable as the approved reference?

Any `No` = **FAIL — TYPOGRAPHY / READABILITY** and must be fixed before Premium Candidate.

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
8 Is Thai harder to read than the human-approved worklist reference? yes=FAIL Typography.

## 18. Desirability Test
Premium Candidate reaction: “precise, expensive, calm, intentionally designed — I want to use it.”

Clean/neat/usable/professional alone is not Premium.

## 19. Responsive / Adaptive Density
Inspect representative desktop and narrower workspace. Left navigation may compact/collapse, context remains visible, primary action remains discoverable and high-value content uses width intelligently.

Typography must remain readable after density adapts; responsive behavior may not solve narrow space by shrinking operational Thai text below the readability floor.

## 20. Independent Premium Design Review
`design-system/PREMIUM_PRODUCT_DESIGN_GATE.md` is mandatory after build.

`Functional PASS + Design FAIL = Factory FAIL`.
`Functional PASS + Typography FAIL = Factory FAIL`.

## 21. Gold Standard Rule
No artifact may call itself Premium/Gold/Signature solely because Factory Gate passes. Promotion requires rendered visual review, Human Design Approval, Anti-Template PASS, Typography/Readability PASS, Desirability PASS, Gorilla continuity evidence and workflow-authored composition.

## 22. Extraction Rule
`Human-approved reference → extract Visual Grammar → components/patterns → Factory enforcement`.
Never reverse into `generic components → assemble → declare premium`.
