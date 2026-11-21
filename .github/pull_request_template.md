## Ticket

Closes #

## What

One paragraph. One idea per PR.

## Why

The spec criterion or user-visible behavior this answers.

## Check

- [ ] The failing run is recorded (red) and the passing run after (green).
- [ ] `uv run pytest` passes locally.
- [ ] The changed paths match the issue's `Touches:` list (or the PR carries
      `scope:expanded`).
- [ ] Docs are updated where the behavior changed.

## Review

A fresh session that did not write this code must review it. The reviewer
checks the linked spec criterion, the red/green evidence, and one mutation:
break the code on purpose and confirm the check catches it. Approval is the
signoff; request changes otherwise.
