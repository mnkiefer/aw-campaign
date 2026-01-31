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

safe-outputs:
  dispatch-workflow:
    workflows: [add-name, add-emojis]
    max: 2
  add-comment:
    max: 1
---

# Celebrate your first campaign

## Trigger Conditions

Only act if the label that was just added matches one of:

- `ai:my-first-campaign` - run ALL workflows
- `ai:add-name` - run add-name workfklow only
- `ai:add-emojis` - run add-emojis workflow only

Comment on the issue with the results of the dispatched workflows.
