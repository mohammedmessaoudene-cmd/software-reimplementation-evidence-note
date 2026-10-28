# Evaluating software reimplementation: evidence and limits of a partial note

**Messaoudene NT Interop — partial methods note, `v0.1.0-methods-note`, 28 October 2026.** Direction and attribution: Professeur Messaoudene; prose prepared with AI assistance. CC BY 4.0 applies only to the original prose in this selection, with exclusions in [RIGHTS_AND_RELEASE_DECISIONS](RIGHTS_AND_RELEASE_DECISIONS.md).

## Purpose of this note

A reimplementation can produce the expected response while using a different mechanism from the one required. A `PASS` line or a favourable exit code is therefore insufficient to evaluate a synchronization operation. The required behaviour must be defined, the tested revision identified, and the observation linked to a specific invocation. A relevant negative control must then show that the harness rejects the defect it claims to detect. This note develops that method and one narrow historical example. [P01–P02]

The project examines an experimental subset of synchronization events and per-thread error state. This selection cannot evaluate a complete operating system. The present edition contains an original explanation and evidence references; it includes no code, binaries or private logs. Readers can examine the reasoning and public references. They cannot reproduce the historical experiment from this edition alone. [P03, P06]

## A checkable chain of evidence

The experimental contract should specify the permitted operations, selected errors, concurrency limits and conditions for success. In a binary comparison, the probe used on both sides must have the stated identity. A hash supports a comparison of bytes; it does not establish their origin, execution or correctness. [P01]

| Element | Question to resolve |
|---|---|
| Contract | What property is actually required? |
| Identity | Which probe, target and configuration were used? |
| Causal mechanism | Did the relevant wait cause the claimed blocking and resumption? |
| Discriminating negative | Does the harness reject a variant that removes precisely that property? |
| Assessor | Do its rules check relevant evidence rather than the displayed text alone? |

For a blocking wait, the expected causal account links API entry, thread state, removal from runnable contexts, the cause of wake-up, selection of that thread's context and return from the same invocation. These observations have different strengths: an internal line declaring a block is not independent inspection of the processor. Producer and validator revisions must remain attached to the traces. [P01, P03]

## Historical example: an immediate timeout that still printed PASS

A retained internal record from the I5 lineage reports a variant that immediately returned the timeout result of a finite wait. In that scenario, the probe printed `T07_timeout_result PASS`, reported zero internal elapsed time and exited with code 0. The QEMU receipt recorded 97, the code for this project's expected exit route, without a universal meaning for QEMU. The validator nevertheless rejected the case, including the finding `FINITE_TIMEOUT_WITHOUT_BLOCK`. [P02]

The recorded chain linked wait entry and return to the same invocation, without an intervening block. According to that record, the validator rejected this defect despite the positive output. It does not establish an independently measured physical duration: an internal clock and message-arrival timestamps remain different measurements. Nor does it establish that the assessor detects every false timeout. [P02, P04]

Hashes of the reference items appear in [CLAIMS_AND_EVIDENCE](CLAIMS_AND_EVIDENCE.md). The raw items remain private. The example is attributed to a historical local dossier; this note claims neither independent reproduction nor a new execution. A hash without an accessible file is an identity commitment useful for a later comparison, not a publicly replayable dataset. [P02–P03]

## Separate evidence categories and revisions

The internal dossier includes historical Windows probe observations, QEMU guest observations from the I5 lineage, C-component tests on Linux, and models or fake APIs. These categories answer different questions. A Linux frame-structure test does not establish a hardware context switch; a handle model does not establish Windows object identity; a QEMU log alone is not a complete instruction observation. [P03]

The later T09 revision has one received historical Windows oracle and a built normal EFI image. Its guest execution has not been established; its global-error-state mutant remains unbuilt and unrun. I5 results are not transferred to that successor. The I19 technical lot is closed under `HOLD/STOP_AT_HOLD`; I20 is a text-selection activity. [P04]

## What remains open

The project's local experimental protocol, R7, retains unmet requirements: two guest waiters already blocked before a signal, independently calibrated API duration, a discriminating guest interleaving of per-thread error state, held-out cases after freezing the target, and completion of the planned, bounded set of negative controls. J3/J4 are historical and partial; J5 has not been acquired and `BOUNDED_PASS=false`. [P04]

A partial method note remains distinct from a complete R7 demonstration. Future evidence must be tied to its revision, environment, oracle and falsifying conditions. [P01, P04]

## Proposed comparative study and public scope

The effect of AI assistance on reimplementation effort remains a question to measure here. A useful study would compare the same tasks and acceptance criteria, with and without declared assistance, recording human time, computation, validation, corrections and maintenance. Initial cost, quality and maintainability should be treated separately. The retained observations do not support attributing a causal gain to AI or economic harm to the sector. [P05]

A policy discussion can also examine possible benefits for interoperability, research and competition, alongside provenance and maintenance costs. Proportionate requirements for attribution, transparency about methods and explicit evidence are options for discussion. They are not newly adopted institutional rules. Functional similarity alone does not determine copying of protected expression or the unlawfulness of a reimplementation. [P05–P06; S01, S07]

The selected original prose is released under CC BY 4.0 to the extent of rights held by Professeur Messaoudene. The grant excludes private evidence archives, experimental code and linked third-party works. Licences of tools used but not included do not become the note's licence. This partial release neither acquires J5 nor claims R7 completion. [P06; S02–S05, S08]
