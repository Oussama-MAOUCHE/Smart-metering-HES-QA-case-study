# Industrial Smart-Metering HES QA

Historical manual QA case study based on work performed at **SAIEG — Sonelgaz Group** on an industrial smart-metering project. The portfolio focuses on a targeted test slice of the Head End System (HES) administration application: creating and validating meter/device records under a data concentrator.

> Historical QA case study based on work performed in 2022. Portfolio documentation reconstructed from surviving evidence in 2026.

## At a glance

| Area | Evidence-backed scope |
|---|---|
| System tested | HES administration application |
| Tested workflow | Device/meter creation under a data concentrator |
| Test management | TestLink |
| Execution | Manual |
| Platform | Windows Server 2016 |
| Database | SQL Server |
| Executed cases | 12 |
| Results | 2 Passed · 8 Failed · 2 Blocked |

These results describe only the targeted 12-case suite. They are not a product-wide quality score.

## System context

The wider SCI smart-metering solution included meters, data concentrators, HES, and Meter Data Management (MDM). HES and MDM were separate but complementary systems: HES collected and extracted information from data concentrators, while MDM was intended to process information received through HES for downstream metering functions.

The surviving execution evidence supports testing of the **HES device-management area only**. MDM is included here for architectural context and is not presented as executed test scope.

## My contribution

- Developed and iteratively refined a preliminary HES test plan.
- Authored and executed 12 manual cases in TestLink.
- Began with exploratory testing and then formalized repeatable positive, negative, validation, data-consistency, and state-oriented scenarios.
- Used SQL Server as a secondary verification point to compare HES input with persistence outcomes.
- Recorded expected and actual behavior through TestLink execution notes, screenshots, reports, and metrics.
- Communicated identified issues internally through the company email channel.
- Prepared and delivered an introductory presentation on software testing and TestLink to a multidisciplinary internal audience.

## Test focus

The initial slice concentrated on risks around device identity, validation, persistence, and state visibility:

- access to the device-creation workflow;
- creation with complete information;
- duplicate-device handling;
- blank-field validation;
- invalid Device ID and MAC input;
- empty-record submission;
- Out-of-Service state representation;
- DC reassignment;
- comparison of HES input with database persistence outcomes.

The detailed rationale and scope boundaries are documented in [Test Approach](docs/test-approach.md).

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

## Database validation

SQL Server was used as a secondary verification point after entering data through HES to check whether values were stored correctly, missing, or persisted differently from the UI input.

The surviving evidence confirms the database technology and contains database-related application exceptions, but it does not preserve the original SQL queries, table names, database screenshots, or a repeatable query procedure. Those details are therefore not reconstructed in this portfolio.

## Outcome and limitations

The targeted test slice surfaced risks in validation, duplicate control, post-save data visibility, operational-state visibility, and save-path stability.

The initial exploratory and functional test phase was paused before broader execution because continued application access was not available. Findings had already been communicated internally, but the surviving evidence does not show a controlled fix, retest, regression, or release-closure cycle. No issue-resolution claim is made here.

The represented scope does not include MDM execution, product-wide testing, formal performance testing, formal security testing, compliance testing, or a completed test campaign.

## Evidence and confidentiality

The private evidence set includes TestLink cases and execution reports, screenshots, metrics, a preliminary test plan, exception records, system-context documentation, and an internal testing presentation.

Raw application screenshots, operational identifiers, usernames, stack traces, internal paths, and database implementation details are not published. Public supporting material is recreated or sanitized to preserve the QA evidence without exposing internal product information.

See the [Evidence Policy](evidence/README.md) and the sanitized [Representative Test Case — SCI-11](evidence/representative-test-case.md).
