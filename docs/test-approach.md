# Test Approach

## Purpose

This document explains the approach used for the targeted HES device-creation test slice represented in this portfolio. It describes the work supported by the available evidence without presenting the activity as a complete or formally approved test campaign.

## Objective

The initial objective was to begin with exploratory testing and obvious functional/data risks in the HES administration application, formalize useful scenarios in TestLink, and expand into deeper testing as product access and knowledge increased.

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
- DC reassignment behavior.
- Selected UI-to-database persistence comparisons using SQL Server.

### Not represented as executed scope

- MDM testing.
- Every HES module.
- A complete end-to-end smart-metering campaign.
- Formal performance or endurance testing.
- Formal security or penetration testing.
- Compliance testing.
- Fix verification, retesting, or regression.
- Release-closure validation.

## Test oracle

There was no approved client requirements baseline, completed cahier des charges, or requirement-ID mapping attached to the exported TestLink cases.

Expected behavior was therefore derived from a combination of:

- limited explanations available from developers;
- smart-metering domain knowledge;
- reasonable input-validation expectations;
- observable consistency between entered data, displayed data, and stored data.

This matters when interpreting the results. The portfolio presents the observations as evidence-backed product risks or deviations from reasonable validation/data-consistency expectations, not as proven violations of formally approved requirements.

## Test workflow

The work followed a practical progression:

1. Explore the HES device-creation workflow and identify obvious functional and data risks.
2. Convert repeatable scenarios into TestLink cases.
3. Execute the cases manually against the available HES application.
4. Record Expected and Actual behavior in the execution evidence.
5. Use SQL Server for selected persistence comparisons after data entry through HES.
6. Group the observations by their visible behavior and user/data impact.
7. Communicate the identified issues internally.

The available records show **12 executed cases: 2 Passed, 8 Failed, and 2 Blocked**.

## Risk areas covered

### Device identity and duplicate control

The suite checked whether device identity could be created consistently and whether an already existing device could be created again.

### Required and empty input

Several cases exercised individual blank fields and one case submitted an entirely empty device record.

### Invalid input

The suite included invalid Device ID characters and malformed MAC data.

### Data visibility and consistency

The test work compared entered values with what could be observed after creation. SQL Server was also used for selected persistence checks.

### Operational state

A dedicated case checked whether an Out-of-Service device could be distinguished after creation.

### Save-path stability

Two scenarios were blocked by unhandled database exceptions during save operations.

## SQL Server checks

SQL Server served as a secondary verification point after values were entered through HES. The purpose was to determine whether information had been stored correctly, not stored, or stored differently from the UI input.

The reviewed evidence does not contain the original SQL queries, table names, database screenshots, or a repeatable query procedure. The portfolio therefore records the verification purpose without inventing technical details that are not supported by the available source material.

## Stopping point

The initial exploratory and functional test phase was paused before broader execution because continued application access was not available.

The identified issues had been shared internally, but the available evidence does not establish later fixes, retesting, regression, or release closure. Those activities are not claimed.

## Related material

- [Repository overview](../README.md)
- [Execution Summary](execution-summary.md)
- [Evidence Policy](../evidence/README.md)
- [Representative Test Case — SCI-11](../evidence/representative-test-case.md)
