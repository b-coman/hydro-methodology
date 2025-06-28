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

# Activities and Processes

Hydro methodology organizes work through distinct activities that occur throughout the development lifecycle. These activities are specifically designed for the hybrid AI-human world - they support fully programatic automations and proposelly focus on prior-development activities.

{% hint style="info" %}
These activities integrate with the workflow states described in the [previous section](workflow.md), with refinement occurring during 'In Refinement' state, planning during wave organization, and execution spanning 'In Progress' through 'Done' states.
{% endhint %}

### Refinement = task analysis + preparation

Refinement is the key activity in Hydro's SDLC. Actually, Hydro by its nature shifts the general focus from code writing (in legacy Agile frameworks) to thoughtful definitions in the "pre-work" phases.&#x20;

Unlike traditional methodologies that separate product and engineering work, Hydro's refinement process brings product managers and engineers together through shared analysis of business requirements and technical complexity.&#x20;

**Why is important?** → Teams transform rough requirements into executable tasks with clear specifications and appropriate AI collaboration patterns.

Activities performed:

**Initial Analysis** - examines the business requirement and technical complexity

* Business value assessment and stakeholder impact analysis
* Technical complexity evaluation and architectural considerations
* Scope definition with clear boundaries and exclusions
* Risk assessment for implementation and integration challenges

**AI Classification** - determines the optimal collaboration pattern (According to the classes defined before)

* Complexity analysis using decision framework algorithms
* Pattern matching against established task types
* Confidence scoring for classification accuracy
* Human validation of AI-suggested classifications

**Dependency Mapping -** identifies prerequisite relationships and sequencing requirements

* Technical dependency analysis for implementation order
* Business dependency evaluation for value delivery sequence
* External dependency identification for third-party integrations (if any)
* Invalid or circular dependency detection

**Context Package -** it is created the package that prepares AI execution specifications:

* File reference compilation for relevant codebase context
* Pattern identification from existing implementations
* Constraint documentation for performance and compliance requirements
* Quality requirement specification including testing and validation criteria

**Acceptance Criteria Definition** - it establishes the completion standards (also defines the tests that should be performed)

* Functional requirement specification with measurable outcomes
* Non-functional requirement definition including performance and security
* Integration point validation for system compatibility
* Business validation criteria for stakeholder acceptance

### Planning = wave organization

Planning activities organize refined tasks into executable waves based on dependency analysis and business priorities. Building on the collaborative foundation established during refinement, planning maintains the integrated approach between product strategy and technical delivery through shared wave design and business priority alignment.

Wave planning ensures optimal task sequencing while maintaining epic integrity and business value delivery:

**Dependency analysis** - calculates wave assignments based on prerequisite relationships and unlock potential for business impact prioritization.

**Epic integrity -** ensures all epic tasks remain in single waves to maintain business capability coherence and complete value delivery.

**Wave composition optimization** - balances AI-ready, AI-assisted, and human-only tasks to prevent bottlenecks and optimize team capabilities.

**Business Priority -** aligns technical sequencing with stakeholder value delivery and market timing considerations.

### Execution = development + validation

Execution activities implement tasks according to their classification while maintaining quality standards and enabling natural workflow progression. The task components and descriptions (as defined in the previous section) will lead the process. Tasks becomes the main communication channel for software development (AI-only or AI-assisted)

**AI-Ready Task Execution** follows autonomous implementation patterns:

* Context package analysis for requirement understanding
* Automated test generation with comprehensive coverage
* Documentation creation following project standards
* Coding patterns followed according to documentation and context packages

**AI-Assisted Task Execution** combines AI generation with human guidance:

* Human architectural decision making for complex business logic
* AI scaffolding generation for boilerplate and repetitive code
* Collaborative refinement of generated implementations
* Joint testing strategy development and execution

**Hybrid Task Execution** manages shared ownership between humans and AI:

* Human leadership of strategic and architectural decisions
* Continuous collaboration throughout development process
* Human validation of all business-critical logic and integrations

**Human-Only Task Execution** preserves human expertise for critical decisions:

* Complete human ownership of design and implementation decisions
* AI support through research, analysis, and documentation assistance
* Quality assurance support through automated testing and validation

### Completion = integration + Wave closure

Completion activities validate finished work and enable progression to subsequent waves through systematic quality gates and dependency analysis.

**Task Completion Validation** ensures individual work units meet all requirements:

* Acceptance criteria verification through automated and manual testing
* Code quality assessment using established standards
* Integration testing with existing system components
* Performance validation against specified requirements
* Security scanning and vulnerability assessment for applicable components

**Wave Completion Validation** validates cohesive capability delivery:

* All wave tasks completed and validated according to individual criteria
* Integration testing across all wave components for system compatibility
* Documentation completeness - maintainability and knowledge transfer
* Next wave dependency satisfaction verification

{% hint style="info" %}
Teams should conduct a brief completion review to demonstrate delivered capabilities to stakeholders, capture lessons learned for process improvements, and assess readiness for subsequent wave activation. This ensures continuous improvement and smooth progression between waves.
{% endhint %}

**Cascade analysis and dependency unblocking** enables continuous flow by automatically identifying newly unblocked tasks and calculating priorities for optimal next wave preparation.

**Quality Gate Enforcement** maintains enterprise standards through comprehensive validation including code review, automated testing, performance benchmarks, security compliance, and documentation accuracy.

***

{% hint style="info" %}
Hydro Methodology © 2025 \
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
{% endhint %}
