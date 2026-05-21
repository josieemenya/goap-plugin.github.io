# UPlannerComponent

###### Description 

Inherits from UActorComponent.

Core planner component attached to an AIController. When a goal is assigned, it uses A* search to generate a sequence of actions for the AI to execute.

---

## Members
### Member Variables
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/AIModule/UBlackboardComponent">UBlackboardComponent</a>\* BB_Planner;</code><dd>Allows for Blackboard Integration inside the planner.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="action_api.html">UAction</a>\*> ToDoStack;</code><dd>Where the planner stores the list of actions, ready to execute by the AI</dd>
<br>
<code><a href="action_api.html">UAction</a>\* CurrentAction;</code><dd>Current action being executed by the planner. Runtime-only, not exposed to editor or Blueprint.</dd>
<br>
<code><a href="action_api.html">UAction</a>\* LastAction;</code><dd>Debug-only reference to the last executed action. Not Editable or Visible.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="https://dev.epicgames.com/documentation/unreal-engine/typed-object-pointer-properties-in-unreal-engine">TSubclassOf</a><<a href="action_api.html">UAction</a>>> AvailableActions;</code><dd>Stores a list of Action Templates, allows for customization in Editor. Visible and Editable in Editor</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="action_api.html">UAction</a>\*> ActionList;</code><dd>A list of instaned Template actions from Available Actions.</dd>
<br>
<code><a href="worldstate_api.html">FWorldState</a> AgentStateValue</code><dd>Agent State Values, updated during action execution.</dd>
<br>

### Member Functions

<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="action_api.html">UAction</a>\*> FilterSatisfyingActions(<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="action_api.html">UAction</a>\*> Actions, const <a href="worldstate_api.html">FWorldState</a> DesiredState); 
</code>
<dd>Returns the subset of actions whose effects satisfy at least part of the desired world state. Not Callable in Editor.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="action_api.html">UAction</a>\*> PlanGoal(<a href="worldstate_api.html">FWorldState</a> CurrentState, <a href="worldstate_api.html">FWorldState</a> DesiredState); 
</code><dd>Returns a subset of actions that when executed achieves the desired World State.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="action_api.html">UAction</a>\*> BuildPlan(<a href="node_api.html">Node</a>\* Last);
</code><dd>Builds an Array of Actions to form a plan by using Node traversal.</dd>
<br>
<code>void UpdateStack(<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Engine/AActor?application_version=5.7&lang=en-US">AActor</a>\* OwningActor)</code>
<dd>Updates The ToDoStack by executing the top most element from the stack.</dd>
<br>
<code>FORCEINLINE bool HasPlan() const { return ToDoStack.Num() > 0; } </code><dd>Checks if ToDoStack has elements. If it's greater than 0, then we currently have a plan.</dd>
<br>
<code>FORCEINLINE void AbortPlan() { ToDoStack.Empty(); }</code><dd>Wipes out the elements in the ToDoStack, effectively aborting the plan. e.g. when the Current Action execution is invalid.</dd>
<br>
### Delegates
<code>
    FOnPlanInvalid OnPlanInvalid
</code>
<dd>
    Dynamic Multicast Delegate, should be called in code when the plan is invalidated, e.g, a null pointer or an action execution returning <a href="exit_sequence.html">EExitSequence::INVALID</a>. Bound function is usually defined in the AIController.
</dd>

<code>
    FOnPlanFinished OnPlanFinished
</code>
<dd>
    Dynamic Multicast Delegate, should be called in code when the plan is finished, e.g, when the ToDoStack is empty. Bound function is usually defined in the AIController.
</dd>