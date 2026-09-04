# Representative Test Cases — SCI-11 and SCI-12

> Sanitized public versions based on the original TestLink cases and execution records. The test intent, Expected behavior, execution result, and observed outcome are preserved; operational identifiers and raw product screenshots are omitted.

These two cases represent different parts of the HES test approach: SCI-11 focuses on negative input validation, while SCI-12 covers a multi-step device-creation flow and post-save operational-state visibility. They are examples from the 12-case suite, not a replacement for the full execution summary.

## SCI-11 — Create a meter with all input fields blank

### Test definition

**Objective:** Verify how the HES device-creation workflow handles a save attempt when all device input fields are left empty.

#### Preconditions

- The HES application is available.
- At least one data concentrator is available for device creation.
- The **New Device** window is accessible.
- The **General Properties** area is available.

#### Test data

All device input fields are left blank.

The original data-concentrator identifier is intentionally omitted from the public version.

#### Step and Expected Result

| Step | Action | Expected Result |
|---|---|---|
| 1 | Leave all device input fields blank and select **Save**. | The submission is rejected, the meter is not created, and validation feedback is displayed. |

### Execution

**Result:** Failed

**Actual Result:** An information message indicated **OK**, and the empty meter record was added successfully to the meter list.

### Interpretation

No approved requirements baseline or requirement ID was linked to this case. The Expected behavior relied on a reasonable input-validation and data-integrity expectation: an entirely empty device record should not be persisted as a valid meter.

The result is presented as a validation risk supported by the observed execution, not as a violation of a formally approved requirement.

### Evidence note

The original TestLink material records the case, the Failed execution result, and the successful addition of the empty record. Raw screenshots and the original operational identifier are kept out of the public portfolio for confidentiality.

---

## SCI-12 — Create a meter marked Out of Service

### Test definition

**Objective:** Verify how the HES device-creation workflow handles a meter created with complete information and the **Out of Service** state selected, including how that state is represented after saving.

#### Preconditions

- The HES application is available.
- At least one data concentrator is available for device creation.
- The **New Device** window is accessible.

#### Test data

Complete device information is entered, and **Out of Service** is selected before saving.

Specific device values and the original data-concentrator identifier are intentionally omitted from the public version.

#### Steps and Expected Results

| Step | Action | Expected Result |
|---|---|---|
| 1 | Enter a valid Device ID. | The Device ID field is available and accepts the value. |
| 2 | Enter a Designation. | The Designation field is available and accepts the value. |
| 3 | Enter a Description. | The Description field is available and accepts the value. |
| 4 | Enter the manufacturer serial number. | The manufacturer serial-number field is available and accepts the value. |
| 5 | Enter the distributor serial number. | The distributor serial-number field is available and accepts the value. |
| 6 | Enter a valid MAC address. | The MAC-address field is available and accepts the value. |
| 7 | Select **Out of Service**. | The option is available and can be selected. |
| 8 | Select **Save**. | The meter is added under the selected data concentrator with the entered information and is visibly represented as inactive / Out of Service. |

### Execution

**Result:** Failed

**Actual Result:** The meter was added successfully, but the meter list did not provide a visible distinction between the active and Out-of-Service states.

### Interpretation

No approved requirements baseline or requirement ID was linked to this case. The Expected behavior relied on a reasonable state-visibility expectation: when an explicit Out-of-Service state is selected during creation, that state should remain distinguishable after the record is saved.

The result is presented as an operational-state visibility risk supported by the observed execution, not as a violation of a formally approved requirement.

### Evidence note

The original TestLink material records the eight-step case, the Failed execution result, and the observed inability to distinguish the saved meter's operational state in the list. Raw screenshots and operational identifiers are kept out of the public portfolio for confidentiality.

## Related material

- [Repository overview](../README.md)
- [Test Approach](../docs/test-approach.md)
- [Execution Summary](../docs/execution-summary.md)
- [Evidence Policy](README.md)
