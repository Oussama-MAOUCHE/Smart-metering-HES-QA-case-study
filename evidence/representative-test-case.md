# Representative Test Case — SCI-11

> Sanitized public reconstruction based on the original 2022 TestLink case and execution record. The scenario, Expected behavior, execution result, and observed outcome are preserved; operational identifiers and raw product screenshots are omitted.

## Test definition

**Title:** Create a meter with all input fields blank

**Objective:** Verify how the HES device-creation workflow handles a save attempt when all device input fields are left empty.

### Preconditions

- The HES application is available.
- At least one data concentrator is available for device creation.
- The **New Device** window is accessible.
- The **General Properties** area is available.

### Test data

All device input fields are left blank.

The historical DC identifier is intentionally omitted from the public reconstruction.

### Step and Expected Result

| Step | Action | Expected Result |
|---|---|---|
| 1 | Leave all device input fields blank and select **Save**. | The submission is rejected, the meter is not created, and validation feedback is displayed. |

## Execution

**Result:** Failed

**Actual Result:** An information message indicated **OK**, and the empty meter record was added successfully to the meter list.

## Interpretation

No approved requirements baseline or requirement ID was linked to this case. The Expected behavior relied on a reasonable input-validation and data-integrity expectation: an entirely empty device record should not be persisted as a valid meter.

The result is presented as a validation risk supported by the observed execution, not as a violation of a formally approved requirement.

## Evidence note

The original TestLink material records the case, the Failed execution result, and the successful addition of the empty record. Raw screenshots and the original operational identifier are kept out of the public portfolio for confidentiality.

## Related material

- [Repository overview](../README.md)
- [Test Approach](../docs/test-approach.md)
- [Execution Summary](../docs/execution-summary.md)
- [Evidence Policy](README.md)
