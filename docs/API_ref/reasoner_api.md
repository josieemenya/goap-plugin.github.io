# Utility Reasoner

###### Description 

Inherits from UActorComponent.

## Members

### Member Variables

<code><a href="worldstate_api.html">FWorldState</a> InternalAgentState;</code>
<dd>Reflected Agent State</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="https://dev.epicgames.com/documentation/unreal-engine/typed-object-pointer-properties-in-unreal-engine">TSubclassOf</a><<a href="goal_api.html">UGoal</a>>> GoalClasses;</code>
<dd>Holds the templated Goal Classes.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="goal_api.html">UGoal</a>\*> Goals;</code><dd>Holds instances of the templated Goals.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/object-pointers-in-unreal-engine?application_version=5.6&lang=en-US">TObjectPtr</a><<a href="goal_api.html">UGoal</a>> CurrentGoal</code>
<dd>The Current Goal evaluated by the planner</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/object-pointers-in-unreal-engine?application_version=5.6&lang=en-US">TObjectPtr</a><<a href="planner_comp_api.html">UPlannerComponent</a>> Planner</code>
<dd>Pointer Reference to the Planner.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/object-pointers-in-unreal-engine?application_version=5.6&lang=en-US">TObjectPtr</a><<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/AIModule/AAIController?application_version=5.7&lang=en-US">AAIController</a>> OwnerController</code>
<dd>Owning AI Controller.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Engine/FTimerHandle?application_version=5.7&lang=en-US"></a> ThinkTimer</code>
<dd></dd>
<br>

### Member Functions

<code> void Initialize(<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/AIModule/AAIController?application_version=5.7&lang=en-US">AAIController</a>\* InController, <a href="planner_comp_api.html.html">UPlannerComponent</a>\* InPlanner);</code>
<dd>Initalizes Planner & Blackboard</dd>
<br>
<code>void StartThinking();</code>
<dd>Sets The timer so that the Utility will continuosly evaluate.</dd>
<br>
<code>void HandlePlanFinished();</code>
<dd>Handles functionality for when the Planner has finished Planning and Execution.</dd>
<br>
<code>void HandlePlanInvalid();</code>
<dd>Handles functionality for when the Planner execution is invalidated.</dd>
<br>
<code>void Think();</code>
<dd>Handled when to Update the CurrentGoal being updated to the Planner</dd>
<br>
<code><a href="goal_api.html">UGoal</a>\* ChooseBestGoal();</code>
<dd>Runs utility Scoring.</dd>
<br>
<code>void RequestPlan(<a href="goal_api.html">UGoal</a>\* Goal); </code>
<dd>Sends Goal to the Planner to build plan.</dd>
<br>
<code>void SyncToWorldState(<a href="worldstate_api.html">FWorldState</a> CurrentWorldState)</code>
<dd>Snapshot of the Current World State, Uses the blackboard. ⚠️Warning, this feature is still under construction and won't work as expected. Use with precaution.</dd>
<br>