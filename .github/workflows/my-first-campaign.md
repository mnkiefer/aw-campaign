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


---

# Celebrate your first campaign

## Trigger Conditions

Only act if the label that was just added matches one of:

- `ai:my-first-campaign` - dispatch ALL workflows
- `ai:add-name` - dispatch add-name workfklow only
- `ai:add-emojis` - dispatch add-emojis workflow only

Comment on the issue with the results of the dispatched workflows.
