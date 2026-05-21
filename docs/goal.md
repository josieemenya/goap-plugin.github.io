# Goals

## Description

`Goal` is a Blueprint implementation of the [`UGoal`](API_ref/goal_api.md) class.

Goals represent the desired world states an AI agent attempts to achieve.

The Utility Reasoner evaluates available Goals, selects the highest-priority option, and requests a plan from the Planner to satisfy it.

---

## Desired State

The **Desired State** defines the world-state conditions that must be satisfied for this Goal to be considered complete.

Examples:

- `HasFood = true`
- `EnemyDefeated = true`
- `ReachedSafeLocation = true`

The Planner uses this state as the target when constructing a valid Action sequence.

---

## Utility Scoring

The `GetUtility()` function determines how desirable this Goal is compared to other available Goals.

The Utility Reasoner evaluates all Goals and selects the one with the highest utility score.

Higher scores indicate higher priority.

Example considerations:

- hunger level
- current health
- nearby threats
- available resources
- Blackboard values

Overriding `GetUtility()` is strongly recommended for dynamic decision-making.

If `GetUtility()` is not customised, Goal selection may behave unpredictably or fail to reflect changing gameplay conditions.

If you're unfamiliar with Utility AI scoring, [this overview is a useful starting point](https://youtu.be/p3Jbp2cZg3Q?si=TkeErSvJ3KPBzVOc).