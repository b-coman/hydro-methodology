---
description: Methodology Implementation Support
icon: square-terminal
---

# Tooling

The Hydro methodology requires tooling that can handle dependency analysis, wave orchestration, and AI-human collaboration workflows. Traditional project management tools weren't designed for these patterns.

### Implementation Requirements

Any tool implementing Hydro needs to support:

* **Dependency-driven planning** rather than time-based sprints
* **Wave assignment and tracking** based on dependency analysis
* **AI task classification** and context management
* **Human approval gates** at appropriate workflow points
* **Progress tracking** focused on possibilities unlocked

### Reference Implementation

`ido4` serves as the reference implementation of these patterns:

```bash
# Core workflow patterns
ido4 set-dependencies 42 "Depends on: #15, #20"
ido4 assign-wave 42
ido4 classify-task 42 ai-reviewed
ido4 status --waves
```

**Platform support:** GitHub Projects, Jira (in development)\
**AI assistant support:** Claude Code, Gemini CLI, OpenAI Codex (planned)\
**Status:** Active development, early access available

### Integration Considerations

Effective Hydro implementation requires:

* **Project management integration** - visualization and hybrid team collaboration
* **Workflow state management** - this goes beyond standard project tools
* **AI assistant integration** - context and execution management
* **Team analytics** - workflow optimization

### Alternative Implementations

Hydro methodology is tool-agnostic. Teams could build implementations using:

* Other project management platforms (Jira, Linear, Azure DevOps)
* Different AI coding assistants (GitHub Copilot, custom solutions)
* Alternative CLI approaches
* Integration with existing dev tools

***

{% hint style="info" %}
Hydro Methodology © 2025 \
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
{% endhint %}
