# Evidence Policy

## Purpose

This repository is built from surviving historical QA evidence. The goal is to show the testing method, execution result, and professional reasoning without publishing internal product material that is unnecessary for a public portfolio.

## Private evidence available

The reviewed source set includes:

- TestLink test cases and execution reports;
- the 12-case execution matrix and metrics;
- TestLink screenshots;
- a preliminary test plan;
- captured exception records;
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
- unreviewed internal emails or source documents.

The complete raw TestLink archive is also excluded because it contains internal data, duplicate material, screenshots, logs, and historical template content that does not add enough public value to justify the exposure.

## Public reconstruction rule

Public evidence is recreated or sanitized from the historical source while preserving the facts that matter:

- scenario and test intent;
- Expected behavior;
- observed Actual behavior;
- execution result;
- scope and limitations.

No new execution, requirement, root cause, fix, retest, regression, or business outcome is introduced during reconstruction.

## Representative case

The repository includes one sanitized case:

**SCI-11 — Create a meter with all input fields blank**

It was selected because it is understandable without deep smart-metering knowledge, demonstrates a negative validation scenario, has a clear Expected/Actual contrast, and can be shown without exposing raw product imagery or exception details.

See [Representative Test Case — SCI-11](representative-test-case.md).

## Evidence boundary

The public portfolio demonstrates a real, targeted HES testing activity. It does not claim that the complete HES product, MDM, or the full smart-metering solution was tested.

## Related material

- [Repository overview](../README.md)
- [Test Approach](../docs/test-approach.md)
- [Execution Summary](../docs/execution-summary.md)
