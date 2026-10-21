# nyc

Synthetic, invalid-by-design JavaScript project for **nyc**.

Domain: A payroll calculator whose single test only exercises the holiday-pay branch, leaving the standard-hours and overtime-hours branches entirely untested.

**Measured**: installed and actually invoked in the build environment; the result below is real, not asserted.

## What makes this folder invalid (majority wrong, measured)

nyc --check-coverage reports 45.45% statement/line coverage and 25% branch coverage -- 54.55% of statements and 75% of branches are genuinely uncovered.

## Command

```bash
nyc --check-coverage --lines 100 --branches 100 --functions 100 --statements 100 mocha 'test/**/*.test.js'
```

## Notes

A clear majority of both statements and branches are never executed under test.

## Per-Node-family results

Boundary-version methodology: 2 earliest + 1 middle + 2 latest supported Node majors. node12/node14 are **code-only** (valid, version-appropriate source with no live tool invocation -- same source as the Clean sibling's families, since these tools' modern releases do not run on pre-ES2020 Node baselines); node20/node24/node26 are **live-verified** -- actually installed and run under that family's own real Node binary, and confirmed to produce a genuine finding, not asserted.

| Family | Status |
| --- | --- |
| node14 | CODE-ONLY (valid source, no live tool run) |

This repo carries only the `node14` build.
