---
name: My First Campaign
description:  Prints a greeting to you and adds some celebratory emojis.
on:
  workflow_dispatch:

safe-outputs:
  dispatch-workflow:
    workflows: [add-name, add-emojis]
    max: 2
---

# Celebrate your first campaign

Run add-name and add-emojis.
Then print the combined output.
