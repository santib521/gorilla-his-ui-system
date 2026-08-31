# Gorilla HIS Data Visualization Rules v1.0

> Visualization exists to improve a clinical/operational decision. It is not dashboard decoration.

## 1. Decision-first rule

Before drawing a chart, state the question it answers.

Examples:
- Is pressure rising or resolving?
- Where is patient flow accumulating?
- How long until safe capacity is exceeded?
- Which ward/queue contributes most to the bottleneck?
- What changes if the proposed intervention is executed?

No decision question = no chart.

## 2. Preferred Gorilla visualization families

### 2.1 Micro Sparkline
Use beside an instrument reading for short trend context.
- minimal axes;
- current point and important threshold may be marked;
- do not use decorative area gradients.

### 2.2 Threshold / Capacity Rail
Use for current state vs safe operating range.
- current marker;
- target/threshold marker;
- optionally forecast marker;
- semantic color only for actual warning/critical state.

### 2.3 Operational Flow Spine
Use for sequential hospital flow such as:
`Arrival → Triage → Treatment → Bed Assignment → Ward → Discharge`.

Encode operational meaning, not just nodes and arrows:
- queue volume;
- velocity / wait;
- pressure intensity;
- bottleneck;
- downstream capacity;
- trend direction.

The user should perceive pressure before reading every number.

### 2.4 Forecast Band
Use when showing predicted trajectory.
- actual/history visually distinct from forecast;
- horizon stated;
- uncertainty/confidence represented when available;
- threshold visible when relevant.

### 2.5 Time-to-Threshold
Use when time is more actionable than percentage.

Example:
`97.1% occupancy · ≈46 min to effective capacity`.

### 2.6 Operational Matrix / Field
Use when spatial scanning is operationally meaningful:
- bed field;
- queue matrix;
- ward capacity;
- housekeeping state;
- task field.

Avoid decorative tile mosaics. Each cell/tile must encode real state.

## 3. Visual hierarchy

A visualization normally contains:
1. current state;
2. trend/trajectory;
3. threshold/target;
4. exception;
5. optional forecast/intervention effect.

Do not give every layer equal visual weight.

## 4. Color

- Neutral data is neutral.
- Indigo may identify selection/current analytical focus.
- Red/orange/green retain semantic meaning.
- Do not create rainbow categorical dashboards without a strong requirement.
- Color must never be the only carrier of critical meaning.

## 5. Typography and numerics

- numbers use tabular alignment when comparison matters;
- unit is subordinate;
- timestamps/horizon are explicit;
- chart labels are concise;
- precision should match operational reality; avoid meaningless decimals.

## 6. Interaction

Preferred interactions:
- hover/focus reveals exact context;
- selection highlights connected evidence across the page;
- scenario changes transition actual affected values/flows;
- drill-down preserves selected context;
- intervention preview may show projected before/after when Blueprint supports it.

Motion must explain causality, not entertain.

## 7. Accessibility

- critical state uses icon/label/context in addition to color;
- maintain readable contrast;
- keyboard/focus support for interactive visualization when feasible;
- reduced-motion preference respected.

## 8. Command Center signature

For Command Center candidates, prefer a coherent operational story over separate unrelated charts.

A strong first viewport may combine:
`Hospital Instrument Band → Operational Flow Spine → embedded bottleneck → forecast/time-to-threshold → Intelligence Intervention`

This is a visual grammar, not a fixed layout template.

## 9. Anti-template checks

FAIL if:
- charts exist only because dashboards usually contain charts;
- visualization could be replaced by a generic SaaS chart without losing meaning;
- all charts use the same card shell regardless of purpose;
- color is decorative;
- no operational question is answered;
- the visualization is visually impressive but slower to understand than a table/number.
