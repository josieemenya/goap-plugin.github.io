# Utility System 

## Description :

Solves decision-making. Gives an answer to "How does the AI decide what it wants?" by evaluating available goals and assigns scores based on current world state. The highest soring Goal is given to the Planner to build a plan.


## Concepts : 

### Goal Utility Scoring : 
    - For each available goal, we run GetUtility() and get the returned score/
    - If the score is higher than the current score we apply the goal to be the topmost considered Goal.
    - By the end of the loop the topmost considered Goal will be the Goal with the highest score and returned to the Planner

---

### GetUtility() : 

- A function that can be overridden in the Goal blueprint Editor.

- It takes in a Blackboard Component to allow for the UE5 Blackboard to be integrated. So Blackboard Keyvalues can be considered in scoring.

---

### Goal Priotisation : 

- The GetUtility() function can also be used as a prioritisation ssystem, instead of returning normalized scores you can just do something like :

```
e.g.In the case our blackboard key `HasWeapon` is true :

return 10000;

else :

return -1; 

```

---

### Utility Recalculation : 

- Utility is recalculated when a Planner exists and after every 5 seconds.

It is only passed to the Planner in these circumstances : 

- The Planner does not currently have a plan

- The Planner has a plan but the current plan does not refelect what the new calculated goal should be.

---