# Frequently Asked Questions

## My AI didn't do anything when I hit Play

Consult the following checklist:

- Is the plugin enabled?
- Is your Character using the correct AI Controller?
- Have you added at least one Goal to the Reasoner?
- Have you added at least one Action to the Planner?
- Do your Actions have valid Preconditions and Effects?
- Can your Goal actually be reached using the available Actions?
- Are State Value names spelled exactly the same across Goals and Actions?

Reminder : A Planner cannot create a plan if no valid sequence of Actions can satisfy the Goal.

---

## My AI has Goals but still doesn't do anything.

- Does your Reasoner have more than one Goal?
- If yes, then it might be the case that you haven't overriden the GetUtility() function, override it, make sure it has a meaningful score and ensure that if you are using values from a Blackboard, that the blackboard itself is valid.
- If no, then the Planner might not be able to find a pathway to the Goal, please check the Actions Preconditions and Effects and double check the spelling across each.

---

## Action never executes :

- Is the Action available in the Planner's Available Actions?
- Action Preconditions may also never be satisfied, double check the spelling if that's the case
- Execute function in Actions was not overriden, please override if that was the case!
- Execute Action is either returning a TYPE of FAILURE, INTERRUPTED or INVALID
- Planner cannot find a valid path to the Goal.

---

## Action appears in the Planner but is never chosen:

- Actions Preconditions are never met
- Action cost is too high compared to an alternative
- Actions Effects do not help satisfy the Goal

---

## Differences between the Planner and Reasoner : 

- The Reasoner chooses what the AI wants to do.
- The Planner chooses how to achieve it
- A simpler way to put it would be
- Reasoner : Chooses the Goal
- Planner : Chooses the Actions to get to the Goal

---

## Do I have to use Example Controller?

- No. The Example Controller was made as a reference for those who want the Planner working right out of the box. If you have a better system for the controller then by all means use your own, Just make sure you have the Planner and Reasoner attached to it.

---

## Can I put the Planner/Reasoner on a Character instead of a Controller?

- Yes! Actions recieve Owner as an Actor specifically to support alternative setups, if your components live on a Character cast Owner appropriatelty.

---

## What's the difference between Precondtions and Effects?

- Preconditions: conditions that must be true

- Effects : the world state changes cause after action execution.

---

## Can Actions fail.

- Yes. An action can fail during execution in cases such as:

    - The target moving away or no longer being valid

    - objects destroyed

    - Navigation failing.

Please reflect these bu returning the appropriate execution type.

---

## Why is my planner failing to find a plan?

- Most likely:
- No Actions are registered
- The desired state of the Goal is impossible to reach.
- Effects don't match the Goal State
- Precomdition bloack every possible path
- Circular dependencies between actions.
- To debug effectively, work backwards: 

Goal -> DesiredState -> Which Action should produce that result?

---

## Do I need to use Utility AI to use Goals?

- Not if you don't want to!
- If your system has a more effective way to select goals then you can use it

---

## Blackboard is null in GetUtility 
Possible causes:

- The blackboard has not been initialised in the Example Controller

- If not using the Example Controller, there is no Blackboard Component attached to Controller.

---

## Can multilple goals be active?

- Not with the current implemented setup, the Reasoner only selects one goal at a time, if you need multiple goals you might need to implement custom Logic.

---

## My Planner keeps replanning every frame: 
- Likely causes : 
- Goals are being evaluated and changed constantly 
- World state updates are too aggressive
- Planner invalidation logic happens too frequently 

---

## How to Debug and Plan effectively :

1) Start With one Goal
2) Start with one action
3) Define State Values
4) No Preconditions

Once that works, add preconditions debug and keep adding complexity.

---