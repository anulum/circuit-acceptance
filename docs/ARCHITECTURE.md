<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ACCEPTANCE — repository foundation
-->

# Repository architecture

## Current executable tooling

**What it contains:** the repository's metadata, source-provenance, workflow, dependency-alignment, documentation, inventory and preflight controls.

**What each control does:** it inspects its fixed, declared local scope.

**What received metadata cannot do:** select another acceptance policy or grant domain authority.

Foundation qualification is in progress.

## Intended domain boundaries

| Record | Responsibility | Required evidence |
| --- | --- | --- |
| Qualification record | Scoped qualification state of a recipe, equipment driver, prototype or tapeout package with explicit validity bounds and expiry conditions | Complete upstream evidence digests and enrolled person-in-role sign-off where required |
| Acceptance plan | Pre-evaluation contract fixing ReqIF/`StrictDoc` requirement digests, chip budgets, ATPG and formal/code coverage floors, hardware security gates, `[D0_min, D0_max]` defect-density yield intervals, pre-bound reference simulation trace digests and complete pre-trial statistical design | Frozen before the first evaluation look or hardware trial; plans missing any statistical or uncertainty field are refused |
| Acceptance report | Per-requirement `pass`, `fail`, `unmeasured` or `unsupported` verdicts, deterministic no-model completeness verification, blinded holdout promotion comparisons, recursive slot-rights checks, built-stage tool estimates and serial-numbered physical verdicts | Zero dropped requirements, exact zero-mismatch vector checks separated from netlist formal proof modes, and explicit `inconclusive at this n` reporting when underpowered |

## Pre-trial physical and multi-device statistical rules

- **Method matched to experimental design.** Before any trial, the acceptance plan fixes the statistical test by design: Welch `t` (under a stated normality trust) or exact label permutation for independent arms; paired `t` or exact sign-flip for paired arms; one-sample `t` (stated normality trust), exact median sign test (smallest `p = 2^-n`) or sign-flip (stated symmetry trust) for a one-arm margin claim.
- **Attainability floor and minimum detectable effect.** When the unit of replication is the device (`n >= 2`), device count must reach `alpha` at the method's attainability floor — for exact sign-flip at `alpha = 0.05`, at least `5` devices since `2^-5 = 0.03125`; for exact label permutation, `1 / C(n1 + n2, n1) <= alpha`, such as `3 + 3` — and declare the minimum detectable effect at stated power (a two-device `t` bound has only one degree of freedom). When `n = 1`, replication measures run-to-run variation on that single serial-numbered unit only, with zero population or yield claim.
- **Multiplicity, tolerance bounds, uncertainty and failures.** Joint requirements across corners or metrics use an intersection-union test with no Holm correction, reserving Holm or Bonferroni for separate per-metric claims. Specification-limit claims state proportion `p`, confidence level and non-parametric `alpha^(1/n)` or stated-trust normal tolerance factor (never a mean bound), reading strictly `at least p of devices meet L at 95 %` (never `meets L`). Any missed bound whose declared minimum detectable effect exceeds the margin reads `inconclusive at this n` (never `fail`). Systematic instrument uncertainty `U` (or `U_diff` with reason on same-bench comparisons) and a finite failure value per metric (or rank method) are fixed beforehand, counting every abort or failure.

## Model-promotion comparisons, yield intervals and prototype reporting

- **Promotion comparisons.** AI-assisted claims require a current per-release deterministic no-model run and blinded holdout evaluation, reporting a frozen Berger intersection-union verdict against the declared deterministic reference (a deterministic tool, a generator or high-level synthesis flow, or a recorded human procedure with two-way bootstrap or crossed random-effects superiority lower confidence bound across at least `8` consenting participants, `30` items, `2` sessions by distinct participants per item and `3` items per participant), Kaplan-Meier right-censored median completion time, Clopper-Pearson in-budget success rate across at least the seed count, and separate counts of budget-exhaustion and service-outage fallbacks.
- **Yield intervals, built estimates and physical verdicts.** Before wafer-sort data exist, die yield is reported strictly as a declared-model sensitivity range (Murphy or negative-binomial) over `[D0_min, D0_max]`, not a confidence interval, and never a single point or commercial quote; once measured, yield is reported with a one-sided confidence bound that counts dies on one wafer as correlated. Built-stage FPGA figures are labelled tool estimates naming tool, version, part, corner and place-and-route seed (disclosing single-seed runs or pre-declared seed sets). Physical runs declare beforehand their conditions, trials, acceptance rule, unit of replication, and whether the claim covers one serial-numbered unit or a population of devices. Physical figures read `measured on unit S/N <serial_number>`, and every latency figure names where it was measured: on an on-fabric counter, or as seen by the host, which includes the bus, driver and operating system (never reporting host-seen wall time as core latency). A board's functional verdict counts mismatches against a reference simulation trace and vector set fixed by digest before the run, over every declared vector (zero mismatches required, never sampled or toleranced); it covers those declared vectors and the board stack, not every possible input, whereas netlist formal equivalence covers every input in its stated proof mode. Fault and mutation adequacy scores carry a one-sided lower confidence bound measured on a separate seeded set after the bundle is frozen, covering the declared fault or mutation mix only.

## Planned record schemas

- `circuit_acceptance.qualification_record.v1`
- `circuit_acceptance.acceptance_plan.v1`
- `circuit_acceptance.acceptance_report.v1`

These are planned identifiers. None of them is registered or qualified here.

Read [validation tooling](validation-tooling.md) for the executable repository interfaces.
