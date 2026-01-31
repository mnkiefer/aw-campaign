---
on:
  workflow_dispatch:
    inputs:
      text:
        required: true
---

# Greet the actor

Reply with:
"{{text}}, ${{ github.actor }}!"
