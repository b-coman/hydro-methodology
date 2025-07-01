---
layout:
  title:
    visible: true
  description:
    visible: false
  tableOfContents:
    visible: true
  outline:
    visible: true
  pagination:
    visible: true
---

# Waves

### Waves = execution units

A wave represents a self-contained and self-sufficient group of work that delivers tested and accepted functionality.

Waves are how the [flow principle](../flow-principles.md) manifests in practice --> the visible execution units where dependency-driven work actually happens. They can be seen as the marriage of sprints (delivery focus) and epics (business focus), optimized for AI-assisted development.

The wave concept replaces time-boxed sprints, since artificial time boundaries don't make sense when code can be implemented in hours.

**Waves characteristics:**

* A wave contains all dependencies needed for execution --> self sufficiency&#x20;
* All tasks within an epic must be in the same wave
* Length of the wave is less important. 2 hours or 2 days, that's the same.
* Waves complete as cohesive units with delivered capabilities - atomicity

**Waves Types**

Hydro categorizes work into four natural wave types that follow the logical progression of software development. Each wave type has distinct characteristics in duration, dependencies, and AI-human collaboration patterns.

1. **Foundation Waves** - Establish the architectural groundwork that enables all subsequent development. Could include any platform or data related work.&#x20;
   1. core architecture
   2. shared components
   3. development environment
2. **Feature Waves** - Build user-facing capabilities and business logic on top of the foundation
   1. user-facing capabilities
   2. business rules
   3. data processing
3. **Integration Waves** - Connect individual features into cohesive system experiences
   1. system cohesion
   2. end-to-end workflows
   3. cross-feature integration
4. **Polish Waves** - Optimize and enhance the quality of completed functionality. Includes bug fixing.
   1. performance tuning
   2. documentation
   3. user experience enhancement

<table><thead><tr><th width="116">Wave Type</th><th width="113">Duration</th><th>Dependencies</th><th>Composition</th><th>Completion</th></tr></thead><tbody><tr><td><strong>Foundation</strong></td><td>1-2 days (emergent)</td><td>None or minimal external requirements</td><td>70% AI-ready tasks (interfaces, schemas, configurations)</td><td>Enables all subsequent feature development</td></tr><tr><td><strong>Feature</strong></td><td>2-3 days (emergent)</td><td>Foundation waves plus previous feature waves</td><td>40% AI-ready, 40% AI-assisted, 20% human-only</td><td>Delivers measurable business value to users</td></tr><tr><td><strong>Integration</strong></td><td>3-5 days (emergent)</td><td>Multiple feature waves</td><td>20% AI-ready, 40% AI-assisted, 40% human-only</td><td>Production-ready system capabilities</td></tr><tr><td><strong>Polish</strong></td><td>1-2 days (emergent)</td><td>Core functionality complete</td><td>50% AI-ready (refactoring, documentation), 50% human-only (UX, optimization)</td><td>Enterprise-grade quality and maintainability</td></tr></tbody></table>

**Wave completion checkmarks**

A wave is considered complete when all validation gates pass:

✔︎ All tasks within wave closed and validated \
✔︎ Human operator validation complete \
✔︎ All code committed to version control \
✔︎ Integration tests passing at wave boundary \
✔︎ Next wave dependencies satisfied and unblocked \
✔︎ Performance benchmarks met \
✔︎ Security scans completed (if applicable) \
✔︎ Documentation updated and accurate \
✔︎ Business acceptance criteria validated

**Post-Completion activities:**

* Automatic dependency analysis identifies newly unblocked tasks
* Next wave activation when team ready and dependencies satisfied
* Cascade analysis triggers to determine priority of ready tasks within active wave
* Metrics collection for methodology improvement and business reporting

This creates comprehensive quality gates that prevent technical debt cascade while enabling natural flow progression to subsequent waves.

***

{% hint style="info" %}
Hydro Methodology © 2025 \
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
{% endhint %}
