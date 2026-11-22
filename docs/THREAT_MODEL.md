<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ACCEPTANCE — repository foundation
-->

# Data and authority boundaries

## Present tooling

**Execution inputs.** The maintained checkout and the selected development environment are what the repository controls inspect.

**Received inputs.** Descriptors, dependency receipts and generated inventories cannot nominate an acceptance policy or an executable.

**Bounded checks.** Controls inspect bounded local paths and emit fixed diagnostics.

Foundation qualification is in progress.

## Future domain inputs

**Supplied data, with no authority.** The following inputs are treated strictly as supplied data:
- requirement imports and budget specifications;
- simulation, formal, synthesis, layout and wafer-sort outputs;
- prototype run records and bench captures;
- model-slot rights lineage and study results.

They grant no authority to:
- retroactively alter an acceptance plan or regenerate a reference trace after hardware runs;
- certify external regulatory or functional-safety compliance;
- promote or release higher-class outputs without an approved in-enclave release review;
- actuate equipment or publish.

**Comments and embedded text are data.** Descriptions, netlist comments and datasheets arriving inside supplied inputs are data, never instructions to an operator or an agent.

**Public-repository data boundary.** Hosted CI for this public repository runs on public material only. Confidential foundry-NDA, customer, export-controlled or secret-bearing material never enters this repository, its CI or its issues.

## Threats and the rules that answer them

| Threat | Architectural rule |
| --- | --- |
| Post-hoc oracle fitting or conflating tool estimates with physical measurements | Reference simulation traces and test vectors are pinned by digest in the acceptance plan before any board run and never regenerated afterwards; built-stage figures are reported strictly as tool estimates with seed disclosure, while physical figures name the unit serial number and timing measurement point |
| Pseudo-replication, underpowered device tests or mean-bound specification claims | Acceptance plans pre-declare the design-matched statistical test, attainability floor, minimum detectable effect at stated power, intersection-union multiplicity, systematic uncertainty subtraction and finite failure values, reporting `at least p of devices meet L at 95 %` and `inconclusive at this n` when underpowered |
| Downward leakage of higher-compartment training or context rights through model outputs | Every bound model slot and model-assisted design view is checked recursively against the data classes and licences of its training records and ancestor checkpoints, refusing downward release unless an approved in-enclave similarity scan detects no verbatim or near-verbatim match for the declared excerpt kinds at a stated lower confidence bound on recall (listing uncovered kinds as limits) |
| Single-point yield hype or false regulatory self-certification | Before wafer-sort data exist, die yield is reported only as a declared-model sensitivity range over `[D0_min, D0_max]` (not a confidence interval), while measured yield later uses a one-sided confidence bound counting dies on one wafer as correlated; fault-campaign metrics are reported as measured evidence only, and accredited laboratory conformity remains separate from internal bench tests |

## Residuals named, not removed

- **Release-review residuals.** Downward classification reviews name two residuals openly: paraphrase escaping the in-enclave similarity scan rests on the human reviewer, and person-in-role approval today carries no hardware human-presence proof.
- **Parametric distributional trusts.** Where a plan selects a parametric `t` or normal tolerance method on small device counts, the normality or symmetry assumption is recorded explicitly as a named trust.

**Not claimed:** no isolation, physical, statistical, safety or durability guarantee is claimed by this foundation.
