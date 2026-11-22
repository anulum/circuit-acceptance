<!--
SPDX-License-Identifier: AGPL-3.0-or-later
Commercial license available
© Concepts 1996–2026 Miroslav Šotek. All rights reserved.
© Code 2020–2026 Miroslav Šotek. All rights reserved.
ORCID: 0009-0009-3560-0851
Contact: www.anulum.li | protoscience@anulum.li
CIRCUIT-ACCEPTANCE — repository foundation
-->

# Circuit Acceptance

Circuit Acceptance is being built as the independent sign-off and qualification authority of the circuit platform. It binds requirements, budgets, coverage floors, blinded holdout rules and pre-trial statistical methods before evaluation begins, and issues qualification records and acceptance reports that keep tool estimates, single-board measurements, multi-device tolerance bounds and external regulatory certificates strictly apart. This checkout contains repository validation tooling and documentation only. Full foundation qualification is in progress. There is no installed acceptance-plan validator, sign-off evaluator, qualification-record issuer or qualified record schema.

Circuit Acceptance is part of the **SC Neuromorphic Computing Systems** group (SC-NEUROMORPHIC-COMPUTING-SYSTEMS). The [group and project map](https://github.com/anulum/sc-neurocore/blob/main/docs/ecosystem.md) shows the whole programme and where this repository sits in it.

**What does not exist yet:**
- an acceptance-plan, acceptance-report or qualification-record evaluator;
- a registered runtime record schema;
- a signed qualification certificate or completed physical acceptance campaign.

## Boundary

**What this project owns:**

| Record | Scope |
|---|---|
| Qualification record | Scoped qualification state of a recipe, equipment driver, prototype or tapeout package with explicit validity bounds and expiry conditions |
| Acceptance plan | Pre-evaluation contract fixing ReqIF/`StrictDoc` requirement digests, chip budgets, ATPG and formal/code coverage floors, hardware security gates, `[D0_min, D0_max]` defect-density yield intervals, pre-bound reference simulation trace digests and complete pre-trial statistical design |
| Acceptance report | Per-requirement `pass`, `fail`, `unmeasured` or `unsupported` verdicts, deterministic no-model completeness verification, blinded holdout promotion comparisons, recursive slot-rights checks, built-stage tool estimates and serial-numbered physical verdicts |

**Static imports:** Circuit Core, Circuit Technology and Circuit Flow.

**Records read without importing domain code:**

| Source | Records consumed |
|---|---|
| Circuit Core, Circuit Technology and Circuit Flow | design views, budgets, compartments, approvals, target profiles, run plans, observations and learning records |
| Circuit Digital, Circuit Analog, Circuit Mixed-Signal and Circuit Physical | formal/synthesis results, vector traces, firmware bindings, analogue corners, coupled results and post-fill layouts |
| Circuit Assembly, Circuit Devices, Circuit Fields and Circuit Photonics | assembly packages, chiplet specs, compact models, electromagnetic/thermal models and optical results |
| Circuit Prototyping, Circuit Lab, Circuit Manufacturing and Circuit Automation | prototype runs, calibrated captures, timebases, wafer-sort/genealogy/RMA records and cell observations |
| Circuit Learning and Evidence Instruments | model inventories, study templates, shared evidence manifests and timing witnesses |

**Capability registration and handoffs:** Registers as the custody-look sign-off evaluator with Circuit Core, connects to Bitstream Evidence CI, Sim-Real Witness, Deploy Pack, Neuro Safety Case and SC-NC Verify, and exports reports to Experiment Ledger.

**Explicit non-claims and operating boundaries:**
- It never self-certifies external regulatory or functional-safety conformity (`CE`, `FCC`, `ISO 26262` or `IEC 61508`): internal time-zero bench measurements, `JESD47` reliability stress and accredited external laboratory certificates remain distinct.
- It never accepts a pre-layout switching-activity power estimate for tapeout sign-off, nor an FPGA figure as ASIC timing or energy.
- It never calls a built-stage synthesis or place-and-route figure `measured`, and never makes a population or yield claim from a single board or single device.
- It never regenerates a reference simulation trace after seeing board outputs: any re-simulation is a new digest and a new run.

## Current tooling

Repository controls inspect:
- metadata and source attribution;
- workflows and dependency alignment;
- native documentation and repository inventory;
- preflight orchestration.

Metadata declares architecture-only maturity with empty implemented domain capability and claim inventories.

- Use the exact environment in [Contributing](CONTRIBUTING.md).
- Full CI and preflight belong in CI or in an explicitly admitted pre-push environment.
- See [Validation](VALIDATION.md) for the maintained validation scope.

## Intended evidence

Every future domain artefact will carry the platform's common provenance envelope, its source and environment digests, its confidentiality compartment and its explicit verification boundary. None of the planned record schemas is registered or qualified by this foundation.

## Documentation and support

Read [Architecture](ARCHITECTURE.md), [support](SUPPORT.md), [security reporting](SECURITY.md) and [citation metadata](CITATION.cff).

**Not claimed:**
- a hosted service, released package or DOI;
- a public CI status;
- a performed simulation, hardware measurement or sign-off verdict.

## Licence

Source is licensed under [AGPL-3.0-or-later](LICENSE). A commercial licence is available through the contact in [NOTICE](NOTICE.md).

![ANULUM](docs/assets/anulum_logo_company.jpg)

![Fortis Studio](docs/assets/fortis_studio_logo.jpg)

## Text and data mining reservation
The rightsholder, Miroslav Šotek (ANULUM), expressly reserves the use of the
works in this repository for text and data mining, including the collection of
this content for, and its use in, training, fine-tuning or evaluating machine
learning and artificial intelligence models, in accordance with Article 4(3) of
Directive (EU) 2019/790 and the national provisions transposing it.

No permission for such use has been granted beyond what the licence in
`LICENSE` grants. This reservation does not change that licence: uses the
licence permits remain permitted on its terms, including its attribution and
share-alike conditions.

Reservation made on 2026-11-22. Requests for permission: contact the
rightsholder through the contact listed in this repository.
