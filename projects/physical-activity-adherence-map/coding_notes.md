# Coding Notes — Micro Map v0.1

## Core rule
Code what the study actually describes. Do not infer a more specific mechanism than the available source supports.

## Field rules
- `study_id`: PA001–PA010 for v0.1.
- `citation`: authors, year, title, journal, volume/issue/pages when available.
- `population`: sample type, N, and key age/clinical characteristic if reported.
- `target_behavior`: the concrete behavior measured (e.g., MVPA, steps/day, exercise completion).
- `adherence_problem`: plain-language behavioral problem stated or clearly motivated by the paper. If interpretive, mark it `[study rationale]` or `[inferred]`.
- `intervention`: delivery channel + intervention components. Avoid vague labels such as “digital intervention” when components are reported.
- `BCT_or_mechanism`: use author-described mechanism/component terms first (e.g., self-monitoring, goal setting, feedback). Do **not** assign BCTTv1 numeric codes in v0.1 unless independently verified against the intervention description.
- `duration`: intervention exposure duration.
- `outcome`: actual behavioral outcome(s); secondary psychosocial/use outcomes may be added after the primary behavior outcome.
- `result_and_DOI`: short directional result, not a causal overclaim; include DOI URL.

## Result language
Prefer: “associated with higher…”, “group increased…”, “no clear difference…”
Avoid: “proved”, “works”, “best”, or cross-study rankings in v0.1.

## Missing information
Use `NR` (not reported in the accessible source) rather than guessing.

## Schema pressure tests from PA002–PA004
- If effects differ by time point, preserve the time point (`3 months`, `6 months`, follow-up) in `result_and_DOI`.
- If relative treatment effect and absolute behavioral direction differ, record both; do not convert a relative advantage into an absolute increase.
- Null-effect studies remain eligible. This map describes intervention structure, not a success-only evidence set.
- When a comparator is active, describe the comparator-relevant distinction in `intervention` rather than implying intervention-versus-no-treatment.

## Schema pressure tests from PA005–PA008
- Separate **behavior change** from **physiological capacity**. A trial can increase walking or leisure-time PA without improving peak VO2.
- A transient early response (e.g., week 1) must not be coded as a sustained intervention effect.
- When both groups receive a digital device or resource, code the true randomized contrast (e.g., `Fitbit + SMS` vs `Fitbit only`).
- A between-group advantage can reflect maintenance in the intervention group plus deterioration in control; record baseline direction before calling it an increase.
- `BCT_or_mechanism` can contain multiple author-described self-regulation elements, but v0.1 still does not translate them into BCTTv1 numeric codes.

## Schema pressure tests from PA009–PA010
- Distinguish `personal behavioral feedback` from `social comparison`. PA009 found both feedback forms superior to no feedback, but no significant incremental benefit from adding peer comparison.
- More digital exposure is not automatically better maintenance. In PA010, continuing the app for another 6 months did not outperform accelerometer-only maintenance after the initial 3-month intervention.
- Hybrid interventions must be labeled as hybrid. When digital delivery is combined with in-person counseling, v0.1 does not attribute the observed effect to the app alone.
- When an intervention has an acquisition phase and a maintenance phase, encode both phases rather than summarizing the study as simply positive or negative.
