# OpenClaw Skill Acceptance

Release-gate validation for OpenClaw skills.

`openclaw-skill-acceptance` is a release-gate skill for OpenClaw authors. Use it when a new or updated skill needs evidence-backed validation before internal rollout or ClawHub publishing. The default output is a strict enterprise Markdown acceptance report.

## Short Description

Use when a new or updated OpenClaw skill needs release validation before rollout or ClawHub publishing.

## Marketplace Intro

This skill helps authors decide whether an OpenClaw skill is actually ready to ship. It checks more than loadability: trigger quality, metadata hygiene, resource organization, evidence discipline, dynamic behavior, dependency risk, and report completeness. The result is a structured enterprise acceptance report with explicit pass, conditional pass, or fail conclusions and a release recommendation.

## What It Checks

- Spec compliance for `SKILL.md`, naming, description style, and metadata
- Best-practice release audit for trigger design, progressive disclosure, resource layout, and instruction boundaries
- Feature inventory extraction and coverage analysis
- Load verification with `openclaw gateway restart`, `openclaw skills list`, and `openclaw skills info`
- Dynamic prompt validation for positive, negative, incomplete-input, and safety cases
- Dependency and conflict checks for grouped skills
- Evidence-backed reporting with environment issues separated from skill defects
- Release recommendation for internal rollout or ClawHub publishing

## Default Output

The default output is an enterprise Markdown acceptance report, not just a chat summary.

Expected sections include:

- document info
- target skill and workspace
- spec findings
- best-practice audit results
- static and dynamic validation results
- environment issues
- final conclusion
- release recommendation
- next actions

## Best For

- validating a new skill before first release
- regression-checking a modified skill before republishing
- deciding whether a skill is ready for internal rollout
- deciding whether a skill is ready for ClawHub

## Not For

- generic prompt experiments unrelated to OpenClaw skills
- ad hoc one-off chat testing without evidence capture
- free-form code review that does not concern a skill package
- automatic repair of the target skill during validation

## Example Prompt

```text
Use $openclaw-skill-acceptance to validate this OpenClaw skill for release, run spec and best-practice checks, test positive/negative/incomplete/safety prompts, and generate an enterprise acceptance report.
```

## Listing Copy

### One-line Pitch

Release-gate audit for OpenClaw skills with evidence-backed dynamic validation and enterprise reporting.

### Short Listing

Validate an OpenClaw skill before release with spec checks, feature coverage, dynamic verification, and a structured enterprise report.

### Full Listing

`openclaw-skill-acceptance` is designed for authors who need a real release decision, not a casual opinion. It validates OpenClaw skills across specification, best-practice readiness, feature coverage, grouped-skill dependency risk, loadability, and runtime behavior. It requires actual evidence, keeps pending items visible, separates environment noise from skill defects, and produces a strict enterprise Markdown acceptance report with a release recommendation for internal rollout or ClawHub publishing.
