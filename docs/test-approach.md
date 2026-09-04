# Test Approach

## Purpose

This document describes how I approached the focused HES device-creation scope represented in this portfolio and how the results were interpreted.

## Objective

The objective was to begin with exploratory testing around clear functional and data risks, formalize repeatable scenarios in TestLink, and expand coverage as product access and knowledge increased.

The executed scope focused on creating meter/device records under an existing data concentrator.

## Scope boundary

### In scope

- HES administration application.
- Device/meter creation under a data concentrator.
- Positive and negative creation scenarios.
- Duplicate handling.
- Blank-field and invalid-input validation.
- Post-save data visibility.
- Out-of-Service state visibility.
- DC-number change during device creation.

### Out of scope for this case study

- MDM testing.
- Every HES module.
- A complete end-to-end smart-metering campaign.
- Database-side testing or validation.
- Formal performance or endurance testing.
- Formal security or penetration testing.
- Compliance testing.
- Fix verification, retesting, or regression.
- Release-closure validation.

## Test oracle

There was no approved client requirements baseline, completed cahier des charges, or requirement-ID mapping attached to the TestLink cases.

Expected behavior was therefore based on:

- limited explanations available from developers;
- smart-metering domain knowledge;
- reasonable input-validation expectations;
- observable consistency between entered data and displayed data.

The findings are presented as observed product risks or deviations from reasonable validation and data-consistency expectations, not as violations of formally approved requirements.

## Test workflow

The work followed this progression:

1. Explore the HES device-creation workflow and identify functional and data risks.
2. Convert repeatable scenarios into TestLink test cases.
3. Execute the cases manually against the HES application.
4. Record Expected and Actual behavior in the execution evidence.
5. Review the recorded observations and execution results.
6. Report test execution results and identified issues to the project team through internal email.

The 12 executed cases resulted in **2 Passed, 8 Failed, and 2 Blocked**.

## Risk areas covered

### Device identity and duplicate control

The suite checked whether device records could be created consistently and whether an existing device could be created again.

### Required and empty input

Several cases exercised individual blank fields, and one case submitted an entirely empty device record.

### Invalid input

The suite included invalid Device ID characters and malformed MAC data.

### Data visibility and consistency

The work checked whether entered values could be verified after creation.

### Operational state

A dedicated case checked whether an Out-of-Service device could be distinguished after creation.

### Save-path stability

Two scenarios were blocked by unhandled database exceptions during save operations.

## Stopping point

The test phase was paused before broader execution because continued application access was not available.

The identified issues had already been shared internally. The records reviewed for this portfolio do not document later fixes, retesting, regression, or release closure, so those activities are not claimed.

## Related material

- [Repository overview](../README.md)
- [Execution Summary](execution-summary.md)
- [Evidence Policy](../evidence/README.md)
- [Representative Test Cases — SCI-11 and SCI-12](../evidence/representative-test-case.md)
