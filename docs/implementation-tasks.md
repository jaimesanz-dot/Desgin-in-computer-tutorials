# Implementation Tasks

Generated from the approved `/office-hours` design and `/plan-eng-review` engineering review.

## P1

- [ ] **T1 — Architecture — Implement explicit "Check my work" validation**
  - Surfaced by: Architecture Review Issue 1
  - Files: `src/plugin-controller.ts`, `src/ui/`
  - Verify: manual Figma run shows validation only after clicking the button.

- [ ] **T4 — Tests — Build Vitest coverage and automated plugin/integration harness**
  - Surfaced by: Test Review Issue 4
  - Files: `tests/`, `vitest.config.*`, plugin integration harness files
  - Verify: test run covers validator branches, lesson state, and one full lesson flow.

## P2

- [ ] **T2 — Lesson model — Create typed lesson array and named validator map**
  - Surfaced by: Architecture Review Issue 2
  - Files: `src/lesson.ts`, `src/validators.ts`
  - Verify: unit test loads all steps and resolves every `validatorId`.

- [ ] **T3 — Validation — Use shared validator result contract**
  - Surfaced by: Code Quality Review Issue 3
  - Files: `src/validation-result.ts`, `src/validators.ts`, `src/ui/`
  - Verify: unit tests cover `pass`, `fail`, and `near-miss` rendering.

- [ ] **T5 — Performance — Implement selection-first validation with named fallback**
  - Surfaced by: Performance Review Issue 5
  - Files: `src/plugin-controller.ts`, `src/validators.ts`
  - Verify: tests prove selected subtree wins and whole-page scans are not used for normal checks.

## Build Order

1. Scaffold the Figma plugin and test runner.
2. Add the typed lesson schema and button lesson data.
3. Implement validator result types and validator functions.
4. Build the compact plugin panel.
5. Wire the explicit `Check my work` flow.
6. Add unit tests.
7. Add the automated integration-style lesson flow.
8. Run one manual Figma smoke test before demo.
