# Goals

#### Description:

The C++ Class for the Goal BP. Used for utility scoring and Planner Selection.


## Members

### Member Variables :

<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/FString?application_version=5.7&lang=en-US">FString</a> Name;</code>
<dd>Name of The Goal.</dd>
<code><a href="worldstate_api.html">FWorldState</a> DesiredState;</code>
<dd>The Reflected World State that must be reached to satisfy this goal</dd>
<br>
### Member Function(s):

<code>float GetUtility(const <a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/AIModule/UBlackboardComponent">UBlackboardComponent</a>\* Blackboard);</code>
<dd>The scoring function for utility AI. Must be overriden in the Editor for optimal use.</dd>
<br>
	
