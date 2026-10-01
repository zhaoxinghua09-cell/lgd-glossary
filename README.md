# LGD Glossary — Candidate Definitions for Harmonization

Candidate definitions offered to the FG-TIDA terminology work ([FG-TIDA/themes#32](https://github.com/FG-TIDA/themes/issues/32)) and to any other effort harmonizing trust/identity/governance vocabulary.

**Standing of this document** — contribution, not priority: each entry is a candidate definition with runnable or checkable evidence attached. Harmonize away; improvements welcome via pull request. Terms are specified, not claimed as original coinage where prior use exists.

**License**: glossary text © 2026 Zhao Xinghua / Steven Zhao·China, licensed **CC BY 4.0** (see [LICENSE](LICENSE)). Pointed artifacts (catalog, demos, theory) retain their own licenses.

**Evidence rule**: a construction is specified as runnable or not described at all. Entries marked *runnable* link to executable evidence; entries marked *specified* are properties defined in [lgd-theory](https://github.com/zhaoxinghua09-cell/lgd-theory) and demonstrated in [lgd-medai-demo](https://github.com/zhaoxinghua09-cell/lgd-medai-demo).

---

## Part I — Silent-failure vocabulary (runnable evidence: [silent-failure-catalog](https://github.com/zhaoxinghua09-cell/silent-failure-catalog), entries as of 2026-09-19)

**Silent failure** — a failure of validation in which a check reports success while the property it was meant to check is not being verified. Definition domain: *validation that passes while nothing is being checked*. What makes the class dangerous is that it is invisible in any single run and readable only across a population.

**Silent-failure mode (named mode)** — a named, recurring pattern that produces silent failures. Each catalog entry carries a runnable reproduction, a fixing recipe, and a negative control, with status and an as-of date (SF-001 … SF-014, all `stable`, as of 2026-09-19).

**Family A · Vacuous verification** — validation that operates on nothing: zero items collected, exit 0 (SF-001); early return as an implicit skip (SF-002); swallowed exception (SF-003); sentinel value on failure (SF-004).

**Family B · Uncounted absence** — absences that never appear in any count: neutral marker not counted (SF-005); undeclared means unchecked (SF-006); empty value is silent (SF-007).

**Family C · Wrong evidence** — evidence taken from the wrong referent: loading an artifact as evidence of use (SF-008); exposure counted as usage (SF-009); local green is not remote green (SF-010).

**Family D · Drifting oracle** — the reference itself drifts: the always-green oracle (SF-011); misattributed failure (SF-012).

**Family E · Process & environment** — the checking machinery misreports its own state: stale copy contaminates the check (SF-013); zombie process looks alive (SF-014).

**Negative control** — proof that a check can detect a real break. Every catalog fixing recipe requires one; a fix without a negative control is itself a silent-failure suspect.

**Runnable reproduction** — a minimal executable demonstration of a mode, usually under ten lines.

**Self-testing linter** — a linter that scans a project's own gates for silent-failure patterns and verifies its own detection ability on a seeded corpus (`gate-lint.py --selftest`).

## Part II — Provenance & authority vocabulary (specified in [lgd-theory](https://github.com/zhaoxinghua09-cell/lgd-theory), 2026-09-06; first specified at FG-TIDA in [themes#27](https://github.com/FG-TIDA/themes/issues/27), 2026-09-25)

**Custody without judgment** — the property that separates whoever holds a record set from judgment over its content: the holder carries and protects the records, but holds neither authorship over the reference nor judgment over the taxonomy. Custody is an obligation, not a vote.

**Authorship record** — the field recording who fixed an expected outcome, under what standing, against what reference. Recording authorship is provenance, not a vote: authorship must not confer judgment authority over the population reading the result. (Adopted as a demonstration field in [themes#21](https://github.com/FG-TIDA/themes/issues/21), 2026-10-01: carry the record, or state that it cannot.)

**Authored-or-derived split** — the per-case statement of whether an expected verdict was fixed by an author or derived by construction from a frozen reference. A known-answer set can separate a judge that was wrong from one that was different only if this split is stated per case.

**Definition provenance** — the principle that definitions and taxonomies are themselves authored references requiring version, definitions, and change history, with the standing of the author recorded (symmetric with known-answer authorship; confirmed in [themes#21](https://github.com/FG-TIDA/themes/issues/21), 2026-10-01).

## Part III — Lifecycle governance vocabulary (specified in [lgd-theory](https://github.com/zhaoxinghua09-cell/lgd-theory), 2026-09-06; demonstrated in [lgd-medai-demo](https://github.com/zhaoxinghua09-cell/lgd-medai-demo), 2026-09-26)

**Lifecycle thread (registry / evidence / gates)** — the composition — not a claim of priority — of three mechanisms that each have long precedent (registration, evidence, gated transitions) into one lifecycle-wide governance thread, specified at a minimal, checkable level.

**Evidence-gated lifecycle governance** — governance in which each lifecycle transition is permitted by evidence checked at a gate; demonstrated by the run chain `DENIED → GATE_PASSED → PAUSE → ROLLBACK → REVERIFY → RESUMED` (lgd-medai-demo, one command, zero dependencies).

**Non-monotonic eligibility re-evaluation** — eligibility as a first-class variable that can be downgraded and reinstated under governed transitions when evidence changes after deployment — a complaint, drift, or recall is an input to a governed state change, not an ad hoc override.

**Pluggable evaluator slots** — evaluators as pluggable components under a stable lifecycle frame; a planted judge is exactly a slot swap under frozen conditions, making evaluator diversity a property of the frame rather than a workaround.

---

*© 2026 Zhao Xinghua / Steven Zhao·China. Glossary text CC BY 4.0. Brands SynomosAI / MedXpert are unregistered names only (no entity or trademark filed). Pointed artifacts keep their own licenses (code MIT / Apache-2.0; catalog content all rights reserved; lgd-theory text all rights reserved, citation with attribution permitted).*
