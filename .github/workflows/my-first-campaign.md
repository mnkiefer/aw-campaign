---
name: My First Campaign
description:  Prints a greeting to you and adds some celebratory emojis.
on:
  issues:
    types: [labeled]
  workflow_dispatch:

permissions:
  contents: read
  issues: read

features:
  action-tag: "59b5eaa9e5323e3f2d8652bb5e2a75cbc07a3d89"

safe-outputs:
  dispatch-workflow:
    workflows: [add-name, add-emojis]
    max: 1
  add-comment:
    max: 1
---

# Celebrate your first campaign

## Trigger Conditions

Only act if the label that was just added matches one of:

- `ai:my-first-campaign` - run ALL workflows
- `ai:add-name` - run add-name workfklow only
- `ai:add-emojis` - run add-emojis workflow only

Running means using dispatch-workflow to trigger the specified workflows.

Comment on the issue with the results of the dispatched workflows.
