<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ACCEPTANCE — repository foundation
-->

# Decision: separate independent pre-declared acceptance and qualification from flow execution and domain tools

## Context

When the repository that runs a synthesis tool, prototype board or model benchmark also writes its own acceptance rule after seeing the numbers, tool estimates slip into measurement claims, underpowered runs are misread as passes or failures, and post-hoc trace adjustments hide mismatches.

## Decision

**What Circuit Acceptance owns:**
- qualification record;
- acceptance plan;
- acceptance report;

**What it imports:** Circuit Core, Circuit Technology and Circuit Flow.

**Owned elsewhere:**

| Responsibility | Owner |
|---|---|
| contracts, admission and approval kernel | Circuit Core |
| process, board and facility profiles | Circuit Technology |
| DAG execution and deterministic reference runs | Circuit Flow |
| study templates and grader bundle specs | Circuit Learning |
| sealed holdout custody | REMANENTIA |
| accredited external conformity testing | External accredited laboratories |

## Consequences

**What can be qualified now:** repository governance and validation tooling, before domain code exists.

**What it cannot qualify:** unimplemented schemas, solvers, hardware or sign-off verdicts.

**Architectural consequences:**
- Circuit Acceptance owns pre-evaluation acceptance plans, qualification records and sign-off reports across prototypes, tapeouts, recipes and model-slot rights;
- every physical, statistical, yield-interval and proof-mode distinction is enforced before downstream manufacturing or deployment consumes a verdict;
- external regulatory and functional-safety certification remains strictly with accredited external bodies.
