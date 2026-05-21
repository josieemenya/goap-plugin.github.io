# Utility Reasoner

###### Description 

Inherits from UActorComponent.

## Members

### Member Variables

<code><a href="worldstate_api.html">FWorldState</a> InternalAgentState;</code>
<dd></dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="https://dev.epicgames.com/documentation/unreal-engine/typed-object-pointer-properties-in-unreal-engine">TSubclassOf</a><<a href="goal_api.html">UGoal</a>>> GoalClasses;</code>
<dd></dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/TArray?application_version=5.7&lang=en-US">TArray</a><<a href="goal_api.html">UGoal</a>\*> Goals;</code><dd></dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/object-pointers-in-unreal-engine?application_version=5.6&lang=en-US">TObjectPtr</a><<a href="goal_api.html">UGoal</a>> CurrentGoal</code>
<dd></dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/object-pointers-in-unreal-engine?application_version=5.6&lang=en-US">TObjectPtr</a><<a href="planner_comp_api.html">UPlannerComponent</a>> Planner</code>
<dd></dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/object-pointers-in-unreal-engine?application_version=5.6&lang=en-US">TObjectPtr</a><<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/AIModule/AAIController?application_version=5.7&lang=en-US">AAIController</a>> OwnerController</code>
<dd></dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Engine/FTimerHandle?application_version=5.7&lang=en-US"></a> ThinkTimer</code>
<dd></dd>
<br>

### Member Functions

<code> void Initialize(<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/AIModule/AAIController?application_version=5.7&lang=en-US">AAIController</a>\* InController, <a href="planner_comp_api.html.html">UPlannerComponent</a>\* InPlanner);</code>
<dd></dd>
<br>
<code>void StartThinking();</code>
<dd></dd>
<br>
<code>void HandlePlanFinished();</code>
<dd></dd>
<br>
<code>void HandlePlanInvalid();</code>
<dd></dd>
<br>
<code>void Think();</code>
<dd></dd>
<br>
<code><a href="goal_api.html">UGoal</a>\* ChooseBestGoal();</code>
<dd></dd>
<br>
<code>void RequestPlan(<a href="goal_api.html">UGoal</a>\* Goal); </code>
<dd></dd>
<br>
<code>void SyncToWorldState(<a href="worldstate_api.html">FWorldState</a> CurrentWorldState)</code>
<dd></dd>
<br>