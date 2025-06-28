---
description: Workflow States and Transitions
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

# Workflow

The Hydro methodology operates with a single authoritative workflow state field that serves as the source of truth for all workflow logic. This ensures consistency and eliminates parallel tracking systems that can create confusion.

### **Standard Workflow States**

The methodology defines seven primary states that tasks flow through during their lifecycle

| STATE             | PURPOSE                                                    | CHARACTERISTICS                                                          | REQUIREMENTS TO MEET                                            | OBSERVATIONS                                                               |
| ----------------- | ---------------------------------------------------------- | ------------------------------------------------------------------------ | --------------------------------------------------------------- | -------------------------------------------------------------------------- |
| **Backlog**       | Initial capture of requirements and ideas                  | Basic description exists, dependencies undefined                         | Business priority for analysis                                  | Duration: indefinite until prioritized for refinement                      |
| **In Refinement** | Define all needed info for development                     | AI classification, context package, acceptance criteria                  | Human validates classification, AI suggests based on complexity | Complete when all specs done, dependencies mapped                          |
| **Ready for Dev** | All prerequisites satisfied, ready for implementation      | Clear acceptance criteria, AI context prepared, no blocking dependencies | All dependency tasks completed, specifications validated        | Can start when developer/AI capacity available, ranked by unlock potential |
| **Blocked**       | Temporary state for tasks that cannot proceed              | External blockers identified and documented                              | Regular review to ensure blockers being addressed               | Return to appropriate state when blockers resolved                         |
| **In Progress**   | Active development work occurring                          | Only tasks within currently active wave, typically one task at once      | Wave becomes active when first task transitions                 | AI-ready execute autonomously, others require human collaboration          |
| **In Review**     | Completed implementation awaiting human validation         | Code quality, business logic accuracy, integration compatibility review  | Automated tests, security scans, performance validation         | Review depth varies by AI classification, human sign-off required          |
| **Done**          | Completed, tested, and validated work ready for production | All acceptance criteria met, quality gates passed                        | Successfully integrated, documentation updated                  | Triggers analysis of dependent tasks for potential unblocking              |

### **State Transition Rules**

Each state change requires specific conditions to be met, preventing premature advancement and ensuring quality standards. The methodology enforces these validation gates to maintain workflow integrity and prevent coordination failures.

**Backlog → In Refinement:**

* Task selected for analysis based on business priority
* Basic requirements and context available
* Team capacity available for refinement work
* No blocking dependencies at refinement level

**In Refinement → Ready for Dev:**

* AI classification assigned and validated by human reviewer
* Dependencies clearly mapped and documented in proper format
* Acceptance criteria complete and testable
* AI context package prepared (for AI-classified tasks)
* Epic assignment confirmed and validated
* Wave assignment calculated or manually set

**Ready for Dev → In Progress:**

* All dependency tasks must be in "Done" status (strict enforcement)
* Team member or AI capacity available for task execution
* Task must be within currently active wave (Active Wave Singularity enforcement)
* No higher priority tasks available in ready state within the same wave
* Human approval for task initiation (where required by classification)

**In Progress → In Review:**

* Implementation complete according to all acceptance criteria
* Automated tests passing with required coverage thresholds
* Code committed to version control and available for review
* No blocking issues or unresolved technical debt introduced
* AI tasks may auto-transition with automated validation

**In Review → Done:**

* Human validation complete for quality and business logic accuracy
* Integration tests passing at both task and wave level
* Documentation updated and accurate
* Performance and security requirements met and validated
* All Definition of Done criteria satisfied
* No breaking changes to existing interfaces (or properly managed if necessary)

**In Review → In Progress (rework scenario):**

* Validation identifies specific issues requiring correction
* Detailed feedback provided for rework with clear requirements
* Human reviewer approval for returning to development
* Rework scope defined and estimated

**Ready for Dev/In Progress → Blocked:**

* External dependencies or blockers clearly identified and documented
* Blocking issues have defined resolution approach and ownership
* Impact assessment completed for timeline and dependent tasks
* Regular review schedule established for blocker resolution

**Blocked → Ready for Dev/In Progress:**

* All blocking issues resolved and validated
* Dependencies satisfied or acceptable workarounds implemented
* Human approval for unblocking and continuation
* Task returns to appropriate state based on completion status when blocked

**Quality Gates by State:**

* **In Refinement**: Classification accuracy, dependency completeness, wave assignment validation
* **Ready for Dev**: Prerequisite validation, wave boundary compliance
* **In Progress**: Active wave enforcement, resource allocation validation
* **In Review**: Code quality, business logic accuracy, integration compatibility
* **Done**: Complete validation against Definition of Done criteria

_Note: Advanced implementations may include automated cascade analysis for dependency unblocking and priority calculation for optimal task sequencing, empowering the methodology through specialized tooling._

***

{% hint style="info" %}
Hydro Methodology © 2025 \
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
{% endhint %}
