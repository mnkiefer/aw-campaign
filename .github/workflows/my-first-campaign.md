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

You can run workflows by sending a `dispatch_workflow` tool request.

For example, to dispatch the `add-name` workflow with input parameters, the tool request would look like:

```js
dispatch_workflow({
  "type": "dispatch_workflow",
  "workflow_name": "add-name",
  "inputs": {
    "text": "<text to add your name to>",
  }
})
```

The available workflows you can dispatch are: `add-name`, `add-emojis`.