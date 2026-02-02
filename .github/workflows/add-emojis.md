---
name: Add Emojis
description: Replies to the issue with celebratory emojis.
on:
  workflow_dispatch:
    inputs:
      text:
        required: true
        type: string
      number:
        required: true
        type: number

permissions:
  contents: read
  pull-requests: read

features:
  action-tag: "bb15d929e3d597412c29a9349cf1fe24484d550c"

safe-outputs:
  add-comment:
    max: 1
---

# Add Emojis

Reply to the text input received {{ inputs.text }} and add emojis of joy and celebration on the issue or PR number received {{ inputs.number }}.
