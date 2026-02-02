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
  action-tag: "a7c1a95fbe623e7f4b0983621153a3a38892c4da"

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
- `ai:add-name` - run add-name workflow only
- `ai:add-emojis` - run add-emojis workflow only

## Instructions

You can run workflows either by calling the workflow MCP tool directly (preferred) or by emitting a `dispatch_workflow` request.

### Example Tool Call (preferred)

The MCP tool is named after the workflow (underscores replace hyphens):

```javascript
add_name({
  text: "<text to add your name to>"
})
```

### Or: Agent dispatch format

```json
{
  "type": "dispatch_workflow",
  "workflow_name": "add-name",
  "inputs": {
    "text": "<text to add your name to>"
  }
}
```

The available workflows you can dispatch are: `add-name`, `add-emojis`.