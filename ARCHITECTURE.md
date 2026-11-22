<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ACCEPTANCE — repository foundation
-->

# Architecture

## Current executable surface

The checkout contains:
- repository validation tooling;
- dedicated tests;
- workflow definitions;
- native documentation.

No domain component of Circuit Acceptance is implemented yet. The metadata keeps domain capabilities, claims and qualified record formats empty.

## Intended data flow

1. **Acceptance planning** freezes requirement digests, chip budgets, fault/code/formal coverage floors, `[D0_min, D0_max]` yield-model bounds, pre-bound reference simulation traces and the complete pre-trial statistical specification before any look or trial.
2. **Prototype and tapeout sign-off** check hierarchical budget and assume-guarantee closure, separate built-stage tool estimates from serial-numbered hardware measurements, verify zero-mismatch vector traces alongside proof-mode-qualified formal equivalence, and enforce post-dummy-fill timing/DRC/ESD sign-off.
3. **Process, recipe and slot-rights qualification** qualify manufacturing recipes and verify that every bound or proposed model slot carries a current deterministic no-model run and satisfies the most restrictive data class and licence across its recursive training data and base checkpoints.

## Ownership

**This project owns** the planned Circuit Acceptance records and boundary rules.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| contracts, admission and approval kernel | Circuit Core |
| process, board and facility profiles | Circuit Technology |
| DAG execution and deterministic reference runs | Circuit Flow |
| study templates and grader bundle specs | Circuit Learning |
| sealed holdout custody | REMANENTIA |
| accredited external conformity testing | External accredited laboratories |

## Interpretation

- **Sample size.** An underpowered comparison establishes `inconclusive at this n`, neither equivalence nor failure.
- **Single unit.** Measurements on one serial-numbered board or die establish nothing about a device population.
- **Conformity.** Internal bench and fault-injection reports never constitute `CE`, `FCC`, `ISO 26262` or `IEC 61508` certification.

Read [the documentation architecture](docs/ARCHITECTURE.md) for the planned records, domain rules and schema identifiers.
