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

# Dependencies

## Dependencies = relationship mapping

Dependencies always been the elephant in the room of software development. Regardless of methodology, teams consistently struggle with dependency management due to its complexity and high cognitive load.

Hydro offers the conceptual foundation to solve and automate this part. It aims to transform through AI-assisted analysis and systematic tracking.&#x20;

Dependencies define the prerequisite relationships between tasks and epics, creating the logical flow that drives wave organization and execution sequence.

### **Dependency types and patterns**

Hydro recognizes few fundamental dependency patterns that occur in enterprise development:

**Sequential Dependencies** - create critical path chains where tasks must complete in strict order:

`[Authentication API` → `[User Profile API]` → `[Profile UI]` → `[User Settings]`

**Parallel Dependencies** - allow independent work streams that share common prerequisites

```
[Core Data Models] → [User Service]
                   → [Payment Service]
                   → [Notification Service]
                   → [Audit Service]
```

**Convergent Dependencies** - bring multiple independent streams together at integration points

```
[User Management] ↘
[Payment System]   → [E-commerce Checkout Flow]
[Inventory API]   ↗
[Shipping Service] ↗
```

**Cross-System Dependencies** - handle enterprise integrations with external systems:

```
[Internal Auth] → [SSO Integration] → [External Directory] → [User Provisioning]
```

### **Dependency analysis process**

Hydro rececomments dependencies being analyzed through a systematic process that determines wave assignments. The methodology doesn't make this a requirement, but encourages the community to develop tools for supporting the process.

```python
def calculate_wave_assignment(task):
    # Wave follows dependency depth
    dependency_waves = [dep.wave for dep in task.dependencies]
    task.wave = max(dependency_waves, default=0) + 1
    
    # Calculate business impact
    dependent_tasks = find_tasks_depending_on(task)
    unlock_potential = len(dependent_tasks) * task.business_value
    
    return {
        'wave': task.wave,
        'unlock_potential': unlock_potential,
        'priority_score': (unlock_potential * risk_factor * business_urgency)
    }
```

**Dependency Anti-Patterns**

Here are few patterns that should be avoided:

* Circular Dependencies → Task A depends on Task B which depends on Task A
* Hidden Dependencies → undocumented assumptions that create surprise blockers
* Over-Dependencies → tasks that depend on too many prerequisites
* Under-Dependencies → missing dependencies that cause integration failures

**Dependencies-to-Wave Process:**

Hydro recommends dependencies being identified during the **Refinement** phase (when tasks are analyzed and prepared for development). This process can be partially automated (assisted by AI), or fully automated (with a check from human side).

Here is a proposal of how a systematic process of dependency analysis and wave assignment can be implemented programatically

1. **Step 1 - s**et dependencies using format "Depends on: #X, #Y" or "No dependencies"
2. **Step 2 -** AI analyzes dependencies and assigns appropriate wave based on dependency depth
3. **Validation**: Epic integrity maintained - all epic tasks remain in same wave
4. **Override**: manual wave assignment possible with dependency conflict validation

```python
def systematic_dependency_analysis(tasks, epics):
    # Step 1: Set dependencies
    for task in tasks:
        task.dependencies = parse_dependencies(task.dependency_string)
        # Format: "Depends on: #X, #Y" or "No dependencies"
    
    # Step 2: AI analyzes and assigns waves based on dependency depth
    def assign_waves_by_dependency_depth():
        for task in tasks:
            if task.dependencies == []:
                task.wave = 0  # Foundation wave
            else:
                max_dep_wave = max([dep.wave for dep in task.dependencies])
                task.wave = max_dep_wave + 1
    
    # Step 3: Validate epic integrity
    def validate_epic_integrity():
        for epic in epics:
            epic_tasks = get_tasks_in_epic(epic)
            epic_waves = [task.wave for task in epic_tasks]
            
            if len(set(epic_waves)) > 1:
                # All tasks in epic must be in same wave
                raise EpicIntegrityViolation(f"Epic {epic.id} spans multiple waves")
            
            epic.wave = epic_waves[0]  # Set epic wave to match tasks
    
    # Step 4: Manual override with conflict validation
    def manual_wave_override(task_id, target_wave):
        task = get_task(task_id)
        original_wave = task.wave
        
        # Check dependency conflicts
        for dependency in task.dependencies:
            if dependency.wave >= target_wave:
                raise DependencyConflict(
                    f"Cannot assign task {task_id} to wave {target_wave}: "
                    f"depends on {dependency.id} in wave {dependency.wave}"
                )
        
        # Check epic integrity
        epic = get_epic_for_task(task)
        if epic and any(t.wave != target_wave for t in epic.tasks if t != task):
            raise EpicIntegrityViolation(
                f"Moving task {task_id} would split epic {epic.id} across waves"
            )
        
        task.wave = target_wave
        return True
    
    # Execute process
    assign_waves_by_dependency_depth()
    validate_epic_integrity()
    
    return tasks, epics
```

This process enables automated cascade analysis when tasks complete, automatically identifying newly unblocked work and calculating priority scores for optimal task sequencing.

***

{% hint style="info" %}
Hydro Methodology © 2025 \
Licensed under Creative Commons Attribution 4.0 International (CC BY 4.0)
{% endhint %}
