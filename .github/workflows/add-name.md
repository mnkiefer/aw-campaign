---
name: Greet the Actor
description:  Greets the actor by name.
on:
  workflow_dispatch:
    inputs:
      text:
        required: true

permissions:
  contents: read
  pull-requests: read
---

# Greet the actor

Reply with:
"{{text}}, ${{ github.actor }}!"
