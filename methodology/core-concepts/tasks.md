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

# Tasks

### Task = Individual Work Units

Tasks represent discrete, implementable units of work with clear completion criteria and specific collaboration patterns. Each task includes comprehensive specifications for both human understanding and AI execution.

{% hint style="info" %}
Note: Task activities and progression through workflow stages (Backlog → In Refinement → Ready for Dev → In Progress → In Review → Done) are detailed in the [Workflow States](tasks.md#workflow-states-and-transitions) and [Activities](tasks.md#activities-and-processes) sections.
{% endhint %}

#### **Task naming convention**

Tasks follow a structured naming pattern that indicates their relationship to epics and execution sequence.

Format: \[Task X.Y] Descriptive name&#x20;

* X = Epic identifier (1, 2A, 11, etc.)
* Y = Sequential task number within epic (1, 2, 3...)

Examples:&#x20;

* \[Task 1.1] Define user authentication interface&#x20;
* \[Task 2A.3] Implement payment validation logic&#x20;
* \[Task 11.2] Configure CI/CD pipeline

#### **Task classification**

Every task receives a classification that determines the collaboration pattern between humans and AI.

**AI-Ready Tasks**&#x20;

AI-Ready Tasks can be completed independently by AI with minimal human oversight. They are usually single file output, clear specifications, established patterns. They usually show a success rate of 90%+ first-pass approval.

* Human Role: Define requirements, review output
* AI Role: Full implementation, testing, documentation

Examples:&#x20;

API endpoint implementations with OpenAPI specifications, database entities following established patterns, React components matching design system specifications, test suite generation for defined business rules, configuration and deployment scripts

**AI-Assisted Tasks**

This type of tasks require collaborative development between humans and AI during the coding activities. They are very likely multi-component changes, business logic or/and system integrations and they shows regularly 70%+ success rate with minor modifications.

* Human Role: Guide approach, validate business logic
* AI Role: Generate scaffolding, handle boilerplate, create tests

Examples

Service layer implementations with complex business rules, data migration scripts with validation logic, third-party API integrations with error handling, complex form workflows with validation logic

**Hybrid Tasks**&#x20;

Hybrid Tasks are defined as shared ownership with continuous collaboration beween an AI coding assistant and human programmer. Their main characteristic is about strategic implementations and they require business domain expertise to handle the edge cases.&#x20;

* Human Role: Architectural decisions, critical logic
* AI Role: Support implementation, generate utilities

Examples

Authentication and authorization systems, payment processing with compliance requirements, workflow orchestration engines, data privacy and GDPR compliance features

**Human-Only Tasks**&#x20;

Human-only Tasks require human expertise for critical decisions on complex architectures, compliance, esecurity, etc. Being named Human-Only doesn't mean AI coding assistant isn't involed, but its role will be less driving comparing with the other types.

* Human Role: Full design and implementation leadership
* AI Role: Research, boilerplate, documentation support

Examples

System architecture and technology choices, security threat modeling and compliance strategy, business process design and optimization, technical debt remediation planning

#### **Task components**

Every task must include the following important components. The presence, and good quality of these elements will determine the success of AI in fulfilling its job, and ultimately the qulity of work.

**Epic reference**

* Part of `Epic [X]: [Epic Name]`

**Dependencies**

"Depends on: #X, #Y" or "No dependencies"

* Used for wave assignment calculation
* Drives cascade analysis when task completes

**Wave assignment**

Wave: `wave-001`

* Required field for all tasks
* Follows dependency analysis algorithm
* Supports Epic Integrity Principle

**Testing requirements**

* Test File: `[path to test file]`
* Coverage Target: `[X]%` (varies by AI classification)
* Test Type: `[Unit/Integration/E2E/Type/Manual]`
* Test Scenarios:
  * Happy path: `[main success scenario]`
  * Error case: `[primary failure scenario]`
  * Edge case: `[boundary condition]`

**AI context package**

* [ ] Read: `[path to relevant files]`
* [ ] Pattern: `[Architecture pattern to follow]`
* [ ] Constraints: `[Technical and business constraints]`
* [ ] Example: `[path to example]` (if available)

#### **Task Documentation**

Here is a general template for the specs compliance for tasks:

```yaml
Task Definition:
  id: "[Task X.Y] Task Name"
  classification: "ai-ready | ai-assisted | hybrid | human-only"
  confidence_score: 1-10
  wave: "wave-001"
  epic_reference: "Part of Epic [X]: [Epic Name]"
  dependencies: "Depends on: #X, #Y" or "No dependencies"

Acceptance Criteria:
  - "Specific, measurable deliverable"
  - "Test requirements and coverage targets"
  - "Integration points and validation steps"

Testing Requirements:
  test_file: "[path to test file]"
  coverage_target: "[X]%"
  test_scenarios: 
    - "Happy path"
    - "Error case" 
    - "Edge case"

AI Context Package:
  files_to_analyze: 
    - "src/interfaces/auth.ts"
    - "docs/patterns.md"
  patterns_to_follow: 
    - "Repository pattern"
    - "Error handling"
  constraints: 
    - "Performance <200ms"
    - "Security requirements"
  quality_requirements: 
    - "Test coverage ≥90%"
    - "Integration tests"
```

#### **Task sizing**

Here are some general guidelines and empirical observations, not required rules. In Hydro, and AI-human hybrid work generally, execution time is less important than the quality of task definitions and and dependency identification pre-work.

* **AI-Ready Tasks**: 1-2 hours (single component scope)
* **AI-Assisted Tasks**: 3-5 hours (bounded complexity)
* **Hybrid Tasks**: 1-2 days (strategic implementations)
* **Human-Only Tasks**: 1-2 days maximum (split if larger)

**When to split tasks?**

* Touches more than 3 files (except human-only integration tasks)
* Has more than 5 acceptance criteria
* Requires totally different skill sets, security or architecture scope

{% hint style="info" %}
Well-defined tasks with clear acceptance criteria and appropriate AI context enable efficient execution regardless of estimated duration. Focus on specification quality over time estimation.
{% endhint %}

#### **Definition of Done** (standard for all tasks)

The DoD establishes the standard completion criteria that every task must satisfy before transitioning to "Done" status. This checklist serves as the final validation gate in the workflow.

* [ ] All acceptance criteria met
* [ ] Tests written and passing (coverage target met)
* [ ] Code follows project conventions
* [ ] Documentation updated
* [ ] PR approved by reviewer
* [ ] No breaking changes to existing interfaces

***

{% hint style="info" %}
Hydro Methodology © 2025 \
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
{% endhint %}
