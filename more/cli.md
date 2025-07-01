---
description: Methodology Implementation Support
icon: square-terminal
---

# Tooling

As teams scale hydro, a gap becomes apparent: your AI assistant can write code but can't update Jira tickets. Traditional project management tools weren't designed for AI teammates who need to manipulate work items alongside humans.

Effective implementation requires tooling that handles:

* Dependency-driven planning and wave orchestration
* AI task classification and context management
* Workflow state management with human approval gates

### Reference Implementation: ido4

We're developing ido4 as a reference CLI that demonstrates these patterns:

```bash
# Core workflow patterns
ido4 set-dependencies 42 "Depends on: #15, #20"  # Link task dependencies
ido4 assign-wave 42                              # Add task to wave
ido4 classify-task 42 ai-ready                   # Set AI coding level
ido4 status --waves                              # Show wave progress
```

**Status:** active development\
**Early access:** [contact](https://mailchi.mp/3a42b980f407/hydro) us for pilot program

### Tool-Agnostic Approach

The methodology works with any tooling approach. Teams are building solutions using GitHub Projects, Jira, Azure DevOps, and custom implementations.

The key is enabling AI to participate in work management, not just code generation.

***

{% hint style="info" %}
Hydro Methodology © 2025 \
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
{% endhint %}
