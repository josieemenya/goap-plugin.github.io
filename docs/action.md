# Action

## Description

`Action` is a Blueprint implementation of the [`UAction`](API_ref/action_api.md) class.

Actions represent the behaviours an AI agent can perform while working toward a Goal.

Each Action defines:

- what must be true before it can be considered
- what changes after it completes
- how expensive it is relative to other Actions
- what behaviour should occur when the Action executes

---

## Preconditions

Preconditions define the world-state requirements that must be satisfied before the Planner can consider this Action.

Example:

- `HasWeapon = true`
- `TargetVisible = true`

If the required conditions are not met, the Action will not be included in a valid plan.

---

## Effects

Effects define the world-state changes produced by the Action.

These are used by the Planner when determining whether an Action helps satisfy a Goal.

Example:

- `HasFood = true`
- `EnemyDefeated = true`

---

## Cost

Cost determines how expensive an Action is compared to alternatives.

The Planner uses this value when evaluating possible plans.

---

## Execute

`Execute()` defines the actual runtime behaviour of the Action.

This function **must be overridden** in Blueprint or C++ for the Action to perform any meaningful behaviour.

Examples:

- moving to a target
- interacting with an object
- playing an animation
- modifying gameplay state

---

## Return Values

Actions return an [`ExitSequenceType`](API_ref/exit_sequence.md) value indicating the result of execution.

See [`ExitSequenceType`](API_ref/exit_sequence.md) for full details.