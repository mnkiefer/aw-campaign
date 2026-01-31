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
  action-tag: "67d415ed02e564aa99a9852f59ebed4ea8a64436"

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

To run workfklows, use safeoutputs_dispatch-workflow:

```json
{
  "type": "dispatch_workflow",
  "workflow_name": "<workflow-name>",
  "inputs": {
    "payload": "{ ... }"
  }
}
```

Comment on the issue with the results of the dispatched workflows.
