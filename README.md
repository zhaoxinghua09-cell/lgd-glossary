# LGD Glossary — Candidate Definitions for Harmonization
[![Trust Score](https://img.shields.io/badge/Trust%20Score-80%2F100%20A-2ea44f.svg)](https://github.com/zhaoxinghua09-cell/skillgate)

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

## Part IV — Re-evaluation vocabulary (specified in themes#33, 2026-10-01; demonstrated in lgd-medai-demo; *note: themes#33 was closed as wontfix on 2026-10-02 — the specifications below remain the authored definitions, cited as facts with their dates, not as live thread states*)

**Restore condition** — the structured commitment registered at the moment a downgrade takes effect, recording what will permit reinstatement: the evidence list that must arrive, the role entitled to verify it, and the validity window within which that verification holds. A downgrade without a restore condition is a one-way gate; with one, restoration is a governed transition rather than an ad hoc pardon. Where recovery semantics are absent from a statute, its drafters can only write the one-way version (see eIDAS Art. 28(4): a revoked certificate’s status "shall not in any circumstances be reverted"). Evidence: *runnable* — lgd-medai-demo reaches `REVERIFY → RESUMED` on a re-verification gate; opened in [themes#33](https://github.com/FG-TIDA/themes/issues/33) on 2026-10-01; closed as wontfix on 2026-10-02 — the thread remains the record of the maintainer's stated reasons, and sector practice was reviewed in the same thread.

**Re-evaluation-ready record** — a decision record that carries the inputs the original decision was based on, not only its outcome, so that a later re-evaluation evaluates against the authored reference rather than from memory. A record of outcome without inputs supports reconstruction ([themes#1](https://github.com/FG-TIDA/themes/issues/1)) but not re-decision. Evidence: *specified* — defined in [themes#33](https://github.com/FG-TIDA/themes/issues/33) (decision provenance for re-evaluation, 2026-10-01); demonstrated in lgd-medai-demo (gate decisions logged with their evidence references and digests).

**Stale decision** — a governed decision marked as no longer current without thereby being reversed. Staleness is a status distinct from revocation: the decision's validity window has closed, while its record remains authoritative about what was decided and on what inputs. Evidence: *specified* — themes#33 (currency and decay, 2026-10-01); the question of whether a previous finding remains applicable under changed conditions is raised in [themes#21](https://github.com/FG-TIDA/themes/issues/21) (change-and-reuse review).

**Eligibility state machine** — the formal object in which eligibility is a first-class variable: a state set (active / restricted / suspended / retired), transitions triggered by evidence events, a gate predicate on each transition, and a restore condition attached to every downgrade, reinstatement being the governed transition back to active. Evidence: *runnable* — the transition chain and per-transition gate predicates are demonstrated in lgd-medai-demo (`DENIED → GATE_PASSED → PAUSE → ROLLBACK → REVERIFY → RESUMED`, one command, zero dependencies); the state set and the mandatory restore-condition registration are specified in the LGD theory work (2026-10-01).

## Part V — LGD core vocabulary (specified in lgd-theory, 2026-09-06; themes#33, 2026-10-01)

The first three terms below are the three laws of lgd-theory, composing the Part III lifecycle thread (registry / evidence / gates).

**Registry (LGD-I · 有籍)** — the law that every governed entity is registered at birth: before an agent, model, tool, or dataset may act within a governed domain, its identity and configuration are entered into a registry whose records persist across the whole lifecycle. Registration is an obligation, not an honor. Evidence: *specified* — [lgd-theory](https://github.com/zhaoxinghua09-cell/lgd-theory) ("Every entity is registered at birth"), demonstrated in lgd-medai-demo (Act I).

**Evidence (LGD-II · 有证)** — the law that every key act leaves evidence: each consequential transition in a governed lifecycle must produce a checkable record at the time it happens, so that later parties can evaluate against what was recorded rather than what is remembered. Evidence: *specified* — lgd-theory ("Every key act leaves evidence"), demonstrated in lgd-medai-demo (Act II: insufficient evidence → DENIED → completed evidence → GATE_PASSED).

**Gate (LGD-III · 有门禁)** — the law that every evolution passes a gate: transitions between lifecycle states are permitted only by predicates evaluated over evidence at the moment of transition, never by the momentum of the prior state. Evidence: *specified* — lgd-theory ("Every evolution passes a gate"), demonstrated in lgd-medai-demo (change gate on model change; REVERIFY gate before RESUMED).

**Evidence event** — an occurrence that is eligible to trigger a state transition in an eligibility state machine because it arrives as a checkable record: a complaint, a drift signal, an audit finding, a monitoring alarm. An event that cannot be recorded is not an evidence event, whatever its urgency. Evidence: *specified* — themes#33 (standing of evidence, 2026-10-01); demonstrated in lgd-medai-demo (complaint triggers PAUSE; a worsening drift signal triggers ROLLBACK).

**One-way gate** — a transition design in which exit from a state is defined but re-entry is not: revocation without a registered restore condition. Statutes that lack recovery semantics tend to write one-way gates (see eIDAS Art. 28(4): its status "shall not in any circumstances be reverted"; quoted in full under restore condition, Part IV). The pairing defect: one-way gates push discretionary pardon outside the record. Evidence: *specified* — themes#33 (Summary: restoration is as consequential as revocation, 2026-10-01).

**Decision provenance** — the record of what a governed decision was based on: the inputs evaluated, the reference (policy, specification, prior decision) it was evaluated against, and the standing of whoever made it. Decision provenance is what makes a past decision re-evaluable rather than merely reconstructable. Evidence: *specified* — themes#33 (decision provenance for re-evaluation, 2026-10-01); sibling term: definition provenance (Part II).

**Validity window** — the period during which a verification, a decision, or a registered restore condition may be relied on without re-execution. A validity window is what lets a decision mark itself stale without being reversed. Evidence: *specified* — themes#33 (currency and decay, 2026-10-01); component of restore condition (Part IV); cf. stale decision (Part IV).

CC BY 4.0; contribution not priority.

## Ecosystem / 生态闭环

- [awesome-trusted-agents](https://github.com/zhaoxinghua09-cell/awesome-trusted-agents) — 四角度评分精选清单（生态榜单入口）
- [skill-scorecard](https://github.com/zhaoxinghua09-cell/skill-scorecard) — 四角度评分引擎
- [lgd-hub](https://github.com/zhaoxinghua09-cell/lgd-hub) — LGD 理论资产统一入口
- [lgd-skill-marketplace](https://github.com/zhaoxinghua09-cell/lgd-skill-marketplace) — LGD 技能超市总目录
- [governanceos](https://github.com/zhaoxinghua09-cell/governanceos) — 治理编排枢纽（SPEC→PLAN→GATE→AUDIT→EVO）
- [skillgate](https://github.com/zhaoxinghua09-cell/skillgate) — 技能信任评分引擎

---

*© 2026 Zhao Xinghua / Steven Zhao·China. Glossary text CC BY 4.0. Brands SynomosAI / MedXpert are unregistered names only (no entity or trademark filed). Pointed artifacts keep their own licenses (code MIT / Apache-2.0; catalog content all rights reserved; lgd-theory text all rights reserved, citation with attribution permitted).*
