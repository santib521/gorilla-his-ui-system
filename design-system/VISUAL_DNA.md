# Gorilla HIS Visual DNA — Product Craft Standard v2.2

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

BMW Test: same functions, why does Gorilla feel deliberately designed?
iPhone Test: does refinement survive when decoration is removed?
If answer is only color/whitespace/radius/shadow/icons → FAIL.

## 3. Authored Work Surface
Do not turn every information group into a card. Preferred hierarchy tools:
1 typography/alignment;
2 spacing/proportion;
3 tonal surface shift;
4 subtle divider;
5 bounded container only when object behaves as one object;
6 shadow only for real elevation.

Every page needs a visual spine and an authored path:
`Context → Situation → Evidence/Work → Exception → Next Action → Detail`.

## 4. Precision Navigation — Hard Gate
Navigation is subordinate to work.
- Never use a large dark sidebar merely because enterprise templates do.
- Persistent navigation width must be justified by actual labels/actions.
- Prefer compact rail/collapsible navigation/contextual lens when it returns useful width to clinical work.
- Expanded navigation may be used for discovery, but after selection it should collapse/compact when continuous visibility is unnecessary.
- Preserve current module/selection orientation in compact mode.
- Do not allow sidebar + topbar + tabs + secondary navigation to all compete visually.
- Main task must own the largest useful portion of the first viewport.

If navigation visually dominates the task or causes large unused workspace → Design FAIL.

## 5. Space Utilization
Premium is not empty space. Whitespace must improve comprehension.

FAIL when:
- important work is compressed into a narrow region while a large blank region remains;
- fixed max-width/template columns waste desktop space;
- action controls are detached from the object they affect;
- equal-sized cards/grids define the page despite unequal importance.

Use responsive/adaptive width so high-value clinical/operational content uses available space intelligently.

## 6. Surface Architecture
S0 Canvas: low-contrast neutral environment.
S1 Work Surface: primary reading/working plane.
S2 Instrument Surface: compact bounded object for readings/controls.
S3 Elevated Surface: menus/drawers/inspectors.
S4 Semantic Surface: critical/warning/normal/info.

Depth communicates hierarchy/interactivity, not luxury decoration.

## 7. Thai Typography Craft — Mandatory
Typography is primary hierarchy. Thai text is not a fallback concern.

Rules:
- use a local Thai-capable font stack available in target environment; production design must explicitly recommend an approved Thai-capable product font without bundling/distributing font files through Factory artifacts;
- tune Thai line-height and weight for readability; do not reuse cramped Latin metrics blindly;
- body/form/worklist/main tabs/actions normally 13–14px or larger;
- 12px only secondary metadata/compact labels;
- 11px only low-priority technical metadata; never instruction, patient identity, main status or primary action;
- mixed Thai/English must align optically and have coherent weight;
- avoid excessive bold Thai text;
- headings compact/confident, not marketing-sized;
- tabular numerals for IDs/times/metrics where supported;
- use weight/alignment/spacing before increasing size.

If rendered Thai looks like poor OS/browser fallback, cramped, weak or visually inconsistent → Typography FAIL.

## 8. Shape Language
Structural regions: low radius/square.
Interactive controls: moderate radius with crafted states.
Floating contextual objects: larger radius/elevation.
Repeated medium-radius rectangles everywhere = generic SaaS signature → FAIL.

## 9. Color and Light
Disciplined product neutrals + semantic color. Premium is controlled saturation/contrast, not more color. Avoid flat-white hairlines everywhere and gradients/shadows everywhere.

## 10. Motion & Micro-interaction
Motion explains causality. Typical families: micro 120–180ms; control/surface 180–260ms; causal transition 240–360ms. Respect reduced motion. No decorative perpetual animation.

## 11. Composition Before Components
Before choosing components define:
- Decision Question
- Primary Evidence
- Exception
- Primary Action
- Secondary Evidence
- Navigation footprint
- Space utilization plan
- Progressive disclosure plan

Then compose the page. Never start from card/grid/component availability.

## 12. Progressive Disclosure
Intake shows only what is needed to classify/validate/accept work. Case workspace reveals deeper functions after case creation. Rare/advanced detail belongs in contextual drawer/accordion/inspector where appropriate. Persistent context remains compact.

## 13. Component Jewelry Standard
Buttons/tabs/fields/selectors/badges/table headers/focus/hover/pressed/selected/disabled/validation/loading/empty/error must look like one product.

Primary controls normally 36–44px high depending on density. Native/browser/Bootstrap/default-Material-looking controls without Gorilla craft = FAIL.

Tabs require more than underlined text. Safety/context banners must remain distinct in grayscale. Icons must have consistent optical weight.

## 14. Numbers as Instruments
Use tabular numerals where useful; unit subordinate but attached; threshold/delta/time near value; no giant marketing numbers; semantic color only.

## 15. Anti-Template Test — Mandatory
Ask:
1 Could this be CRM/fintech/logistics after labels change? yes=FAIL.
2 Is page mainly dark sidebar + white rounded cards? yes=FAIL.
3 Are major regions equal because grid was easy? yes=FAIL.
4 Does removing color destroy hierarchy? yes=FAIL.
5 Is authored focal path unclear? yes=FAIL.
6 Does it feel AI/template generated? yes=FAIL.
7 Is it tidy but lifeless? yes=FAIL Premium Craft.

## 16. Desirability Test
Premium Candidate reaction: “precise, expensive, calm, intentionally designed — I want to use it.”
Evaluate balance/proportion, surface richness, Thai typography, instrument quality, meaningful depth, micro-interaction, operational visualization, coherent identity and control craftsmanship.

Clean/neat/usable/professional alone is not Premium.

## 17. Responsive / Adaptive Density
Inspect representative desktop and narrower workspace.
- navigation can compact/collapse where appropriate;
- context remains visible;
- tables/workspace adapt without hiding primary action;
- actions wrap intentionally;
- no decorative fixed width creates horizontal failure;
- after patient/task selection, give width back to work when continuous comparison is unnecessary.

## 18. Independent Premium Design Review
`design-system/PREMIUM_PRODUCT_DESIGN_GATE.md` is mandatory after build.

`Functional PASS + Design FAIL = Factory FAIL`.
Builder cannot self-declare Premium. Independent critic must review rendered screenshots. If rendering is blocked: `NOT VERIFIED — HUMAN/RENDER REVIEW REQUIRED`.

## 19. Gold Standard Rule
No artifact may call itself Premium/World-class/Gold/Signature solely because Factory Gate passes. Promotion requires rendered visual review, Human Design Approval, Anti-Template PASS, Desirability PASS, Gorilla continuity evidence and workflow-authored composition.

Until Human Design Approval exists, label artifact Candidate.

## 20. Extraction Rule
`Human-approved reference → extract Visual Grammar → components/patterns → Factory enforcement`.
Never reverse into `generic components → assemble → declare premium`.