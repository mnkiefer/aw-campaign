---
name: Add Emojis
description:  Adds celebratory emojis to the provided text.
on:
  workflow_dispatch:
    inputs:
      text:
        required: true

permissions:
  contents: read
  pull-requests: read

safe-outputs:
  add-comment:
    max: 1
---

# Add Emojis

Add emojis of joy and celebration to the end of the input text and reply to the issue.
