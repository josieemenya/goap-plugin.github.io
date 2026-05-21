#Example Controller API

##### Description :

The C++ class for the Example Controller. Used for quick setup for those who just want to get something working quick.

## Members
### Member Variables

<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/AIModule/UBlackboardComponent?application_version=5.7&lang=en-US">UBlackboardComponent</a>\* BlackboardComponent;</code>
<dd>Attaches a BlackboardComponent by default, allows for Blackboard Integration</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/object-pointers-in-unreal-engine?application_version=5.6&lang=en-US">TObjectPtr</a><<a href="reasoner_api.html">UUtilityReasoner</a>> Reasoner;</code>
<dd>Utility Reasoner Component. Holds Goals and scores them before sending the desired goal to the Planner.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/object-pointers-in-unreal-engine?application_version=5.6&lang=en-US">TObjectPtr</a><<a href="planner_comp_api.html">UPlannerComponent</a>> Planner;</code>
<dd>Planner Component. Holds template actions and when a Goal is received holds a stack of actions that guide the AI to the desired state.</dd>
<br>
### Member Functions

<code>virtual void OnPossess(<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Engine/APawn?application_version=5.7&lang=en-US">APawn</a>\* InPawn) override;</code>
<dd>Called when the pawn is possessed by an AIController.</dd>
<br>
<code>virtual void OnUnPossess() override;</code>
<dd>Called when the pawn is unpossessed by an AIController.</dd>
