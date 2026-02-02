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
    max: 2
---

# Add Emojis

Reply to the text input question received {{ inputs.text }} with an answer including emojis of joy and celebration on the issue received {{ inputs.number }}.
