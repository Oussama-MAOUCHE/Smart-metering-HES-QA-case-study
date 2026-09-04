# Industrial Smart-Metering HES QA

Manual QA case study from an industrial smart-metering project at **SAIEG — Sonelgaz Group**. I tested a focused area of the Head End System (HES) administration application: creating and validating meter/device records under a data concentrator.

## At a glance

| Area | Project scope |
|---|---|
| System tested | HES administration application |
| Test focus | Device/meter creation under a data concentrator |
| Test management | TestLink |
| Testing | Manual functional and exploratory testing |
| Platform | Windows Server 2016 |
| Executed cases | 12 |
| Results | 2 Passed · 8 Failed · 2 Blocked |

These results apply to this focused suite, not the entire HES product.

## System context

The wider smart-metering solution included meters, data concentrators, HES, and Meter Data Management (MDM). HES and MDM were separate but complementary systems: HES collected and extracted information from data concentrators, while MDM was intended to process information received through HES for downstream metering functions.

This case study covers only the **HES device-management area** that I tested. MDM is included only to explain the wider system context.

## My contribution

- Developed and refined a preliminary test plan for the HES testing scope.
- Authored and executed 12 manual test cases in TestLink.
- Began with exploratory testing, then formalized repeatable positive, negative, validation, data-consistency, and state-oriented scenarios.
- Recorded Expected and Actual behavior through TestLink execution notes, screenshots, reports, and metrics.
- Reported test execution results and identified issues to the project team through internal email.
- Prepared and delivered an introductory presentation on software testing and TestLink to a multidisciplinary internal audience.

## Test focus

The test scope concentrated on risks around device identity, validation, post-save visibility, and state representation:

- access to the device-creation workflow;
- creation with complete information;
- duplicate-device handling;
- blank-field validation;
- invalid Device ID and MAC input;
- empty-record submission;
- Out-of-Service state representation;
- DC-number change during device creation.

The detailed approach and scope boundaries are documented in [Test Approach](docs/test-approach.md).

## Execution result

| Result | Cases |
|---|---:|
| Passed | 2 |
| Failed | 8 |
| Blocked | 2 |
| **Total** | **12** |

The complete sanitized case matrix is available in [Execution Summary](docs/execution-summary.md).

## Selected findings

### Validation gaps

Several negative cases showed that incomplete device records could be accepted, including submissions with individual blank fields and a submission with all input fields left blank.

### Duplicate handling

A duplicate meter record was accepted and followed by a generic success response instead of a clear duplicate-control response.

### Post-save data visibility

A meter created with complete, apparently valid information was added, but the displayed list did not expose enough of the submitted values to verify them reliably.

### Operational-state visibility

A meter marked **Out of Service** could be added, but its state could not be distinguished from active devices in the displayed list.

### Unhandled save errors

Malformed MAC data and a DC-number change triggered unhandled database exceptions during save operations. These observations support an error-handling and save-path stability concern; they are **not** presented as proof of SQL injection or another specific security vulnerability.

### Protective input behavior

One negative case passed because invalid characters could not be entered in the Device ID field.

## Outcome and limitations

The executed cases identified issues and risks in validation, duplicate control, post-save data visibility, operational-state visibility, and save-path stability.

The test phase was paused before broader execution because continued application access was not available. The findings had already been communicated internally. The records reviewed for this portfolio do not document a later fix/retest cycle, so this case study stops at the observed execution results.

Out of scope for this case study: MDM testing, product-wide testing, database-side testing or validation, formal performance testing, formal security testing, compliance testing, regression, fix verification, retesting, and release closure.

## Evidence and confidentiality

Private supporting material includes TestLink cases and execution reports, screenshots, metrics, a preliminary test plan, exception records, system-context documentation, internal execution-report emails, and an internal testing presentation.

For confidentiality, raw application screenshots, raw internal emails, operational identifiers, usernames, stack traces, internal paths, and database implementation details are not published. Public material is sanitized or summarized while preserving the facts needed to understand the testing work.

See the [Evidence Policy](evidence/README.md) and the sanitized [Representative Test Cases — SCI-11 and SCI-12](evidence/representative-test-case.md).
