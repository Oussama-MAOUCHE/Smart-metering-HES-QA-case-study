# Evidence Policy

## Purpose

This repository presents selected QA evidence from the HES testing work. The goal is to show the testing method, execution result, and professional reasoning without publishing internal product material that is unnecessary for a public portfolio.

## Private evidence available

The reviewed source set includes:

- TestLink test cases and execution reports;
- the 12-case execution matrix and metrics;
- TestLink screenshots;
- a preliminary test plan;
- captured exception records;
- internal execution-report emails;
- smart-metering system-context documentation;
- an internal presentation on software testing and TestLink.

These sources are used to confirm public claims, not copied wholesale into the repository.

## What is intentionally not published

The repository excludes raw material that could expose internal or operational information, including:

- HES product-interface screenshots;
- device and data-concentrator identifiers;
- operational test data;
- usernames;
- exception stack traces;
- internal file paths;
- service or connection identifiers;
- database implementation details;
- raw internal emails and source documents containing internal operational, access, product, or implementation information.

The complete raw TestLink material is also excluded because it contains internal data, duplicate material, screenshots, logs, and template content that does not add enough public value to justify the exposure.

## Public evidence rule

Public material is sanitized and summarized from the source records while preserving the facts that matter:

- scenario and test intent;
- Expected behavior;
- observed Actual behavior;
- execution result;
- scope and limitations.

No new execution, requirement, root cause, fix, retest, regression, or business outcome is introduced in the public version.

## Representative cases

The repository includes two sanitized examples from the 12-case suite:

- **SCI-11 — Create a meter with all input fields blank**: negative input validation and empty-record handling.
- **SCI-12 — Create a meter marked Out of Service**: multi-step device creation and post-save operational-state visibility.

The two cases were selected because they show different parts of the test approach without exposing raw product material. They are representative examples, not a substitute for the complete sanitized execution matrix.

See [Representative Test Cases — SCI-11 and SCI-12](representative-test-case.md).

## Evidence boundary

The public portfolio demonstrates a real, targeted HES testing activity. It does not claim that the complete HES product, MDM, or the full smart-metering solution was tested.

## Related material

- [Repository overview](../README.md)
- [Test Approach](../docs/test-approach.md)
- [Execution Summary](../docs/execution-summary.md)
