# Design-in-computer tutorials

A demo concept for **practice mode inside software**: a guidance layer that teaches while the user works, starting with a Figma plugin that coaches someone through building a reusable button component.

## Core idea

Most tutorials live outside the moment of action. This project explores the opposite: the computer acts like a patient coach inside the tool you are already using.

The first demo target is Figma:

1. The learner opens the plugin panel.
2. The panel shows the current lesson step.
3. The learner creates or edits objects on the canvas.
4. The learner clicks **Check my work**.
5. The plugin validates the selected node or a named fallback object.
6. The panel shows pass, fail, or near-miss feedback.
7. The learner finishes with a real reusable button component.

## Current plan

- [Design doc](docs/practice-mode-for-figma-design.md)
- [QA test plan](docs/practice-mode-for-figma-test-plan.md)

## Engineering decisions already reviewed

- Use a Figma plugin first, not a browser overlay or desktop agent.
- Validate explicitly when the learner clicks **Check my work**.
- Define the lesson as a typed step array.
- Map `validatorId` values to named validator functions.
- Return a shared validator result shape: `{ status, message, details, nextAction }`.
- Use selection-first validation, with a small `Button / Primary` fallback search.
- Include Vitest unit tests and an automated plugin/integration harness in the first build.

## Not in scope for v1

- Multi-app support.
- Ghost cursor recording.
- Background/automatic validation.
- Whole-page scans on every check.
- Full lesson authoring format.
- Figma Community publishing.

## Next build steps

1. Scaffold the Figma plugin.
2. Add the typed button-component lesson.
3. Implement the validator result contract.
4. Build validators for frame, size, text, fill, radius, layer name, and component status.
5. Add the compact plugin panel UI.
6. Add Vitest coverage and an automated integration-style lesson flow.
