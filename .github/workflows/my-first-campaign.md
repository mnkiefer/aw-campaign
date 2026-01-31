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

## Instructions

This workflow demonstrates the `dispatch-workflow` safe output capability. You can trigger other workflows by outputting a `dispatch_workflow` request.

### Example: Dispatch a workflow

To dispatch the `add-name` workflow with input parameters, output a JSON entry like this:

```json
{
  "type": "dispatch_workflow",
  "workflow_name": "add-name",
  "inputs": {
    "campaign_id": "my-first-campaign",
    "payload": "{\"text\": \"your text\"}"
  }
}
```

The available workflows you can dispatch are: `add-name`, `add-emojis`.