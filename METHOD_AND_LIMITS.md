# Method and limits

**Partial text-only methods note, `v0.1.0-methods-note`.** The local R7 experiment and this prose release are separate decisions. This document describes the reading contract of the note; it does not authorize any experimental execution or release of private evidence.

## 1. What this text makes available

The note contains original explanatory prose, a claim-to-evidence table, public primary-source references and release decisions. It contains no executable code, probe, EFI image, third-party binary, private log, correspondence or screenshot. It can therefore support review of the stated method and its limits. It is not a runnable reproduction package.

Evidence commitments in `CLAIMS_AND_EVIDENCE.md` identify selected retained private items by digest. A digest alone cannot authenticate a producer, prove that a program ran, establish the truth of a narrative or let a reader replay absent bytes. Where the raw evidence is private, the claim is explicitly attributed to the internal retained record. An outside reviewer is entitled to withhold experimental acceptance until adequate evidence is available through an authorized route. No future evidence sharing is promised by this package. [P02–P03]

## 2. Required distinctions

| Evidence category | Permitted interpretation | Inference not established |
|---|---|---|
| Byte comparison | Files match the declared digest or each other | Producer authenticity, execution or rights |
| Offline fake/model | A specified model or substituted API follows or violates its contract | Behaviour of real Windows handles or guest hardware |
| Native Linux component test | The identified component behaved as recorded in that Linux harness | Windows ABI, Ring 3 or complete guest execution |
| Windows observation | The identified probe returned an observed result on the reported reference | Correctness of a separate target |
| QEMU guest observation | The reported guest run produced linked observations under its configuration | Exhaustive instruction coverage, general Windows compatibility or independent reproduction |
| Documentary review | A claim is attached to the selected evidence and scope | Experimental validation or permission to publish |

No score is summed across these categories. A repeated checker invocation is not a fresh kernel run. A later editorial date is not a new experimental date. Changing the probe, target or assessor creates a version distinction that must be retained. [P03]

## 3. A useful negative-control contract

Before an experiment, define the mechanism required, the smallest defect that removes it, and the observation that should make the assessor reject. Retain the baseline and the defect on their exact versions. A negative may fail by design while the probe still prints `PASS` or returns zero. Conversely, a crash before launch does not establish detection of the intended semantic defect. The causal linkage must identify the same API invocation and the relevant thread or object. [P01–P02]

An offline mutation of a log tests the reader against that altered record; it does not prove that the altered execution ever occurred. A guard-deletion mutant tests reliance on that guard under the selected fixtures; it does not prove that all possible faults are covered. Initial failures, false admissions, invalid fixtures and corrected expectations should remain distinguishable. If an expected result was wrong, retain the first test and explain the corrected contract rather than overwriting the outcome. [P03]

## 4. Measurement and generalization

A wall-clock process duration, watchdog threshold or message-arrival interval is not automatically the duration of the API being studied. Calibration must relate the external observation to API entry and return with stated uncertainties. Likewise, a single observed interleaving cannot establish all permitted schedules. Held-out cases require a meaningful freeze and separation from development knowledge. [P04]

The current record does not supply the full R7 requirements for two guest waiters already blocked before a signal, independently calibrated API time, the later T09 guest interleaving, held-out cases or completion of the planned, bounded negative-control set. J5 and `BOUNDED_PASS` remain unacquired. The I19 technical lot stays `HOLD/STOP_AT_HOLD`; I20 adds no native run and no new model score. [P04]

## 5. Economic and legal interpretation

The proposed comparison of AI-assisted and other reimplementation work requires common task definitions, acceptance criteria and accounting for human review, computation, correction and maintenance. The present observations do not estimate causal productivity gains, market effects or research incentives. Such outcomes remain open questions. [P05]

Technical similarity and legal characterization must be assessed separately. Source provenance, protected expression, applicable exceptions, contracts and relevant jurisdiction may matter. The public primary sources are context, not case-specific clearance. Tool redistribution questions arise only if the corresponding components are selected for distribution; this text release includes none. CC BY 4.0 applies only to the original prose as specified in RIGHTS_AND_RELEASE_DECISIONS.md; it does not clear third-party material or the underlying experiments. [P06; S01–S05, S07]
