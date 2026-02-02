---
name: Greet the Actor
description:  Greets the actor by name.
on:
  workflow_dispatch:
    inputs:
      text:
        required: true

features:
  action-tag: "bb15d929e3d597412c29a9349cf1fe24484d550c"

permissions:
  contents: read
  pull-requests: read
---

# Greet the actor

Reply with:
"{{text}}, ${{ github.actor }}!"
