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
  pull-requests: read

features:
  action-tag: "bb15d929e3d597412c29a9349cf1fe24484d550c"

safe-outputs:
  dispatch-workflow:
    workflows: [add-emojis]
    max: 1
---

# Celebrate your first campaign

## Trigger Conditions

Only act if the label that was just added matches one of:

- `ai:my-first-campaign` - run ALL workflows
- `ai:add-emojis` - run add-emojis workflow only

## Instructions

You can run workflows either by calling the workflow MCP tool directly (preferred) or by emitting a `dispatch_workflow` request.

### Example Tool Call

The MCP tool is named after the workflow (underscores replace hyphens):

```javascript
add_emojis({
  inputs: {
    text: "<text>",
    number: <issue_number>
  }
})
```

### Or: Agent dispatch format

```json
{
  "type": "dispatch_workflow",
  "workflow_name": "add-emojis",
  "inputs": {
    "text": "<text>",
    "number": <issue_number>
  }
}
```
