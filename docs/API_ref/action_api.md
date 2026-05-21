# Actions

##### Description :

C++ class for the Action BP. Used for Planner selection.


## Members :
### Member Variables :

<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Engine/AActor?application_version=5.7&lang=en-US">AActor</a>\* OwningActor;</code>
<dd>The Actor that owns the Actions. Not Exposed or edited in Editor.</dd>
<br>
<code><a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/FName?application_version=5.7&lang=en-US">FName</a> Name;</code>
<dd>Name of the Action. Editable and used for logging and comparison between other actions. Please give it a name.</dd>
<br>
<code><a href="worldstate_api.html">FWorldState</a> Preconditions;</code>
<dd>The conditions that need to be met to consider this action.</dd>
<br>
<code><a href="worldstate_api.html">FWorldState</a> Effects;</code>
<dd>How the action affects the world state.</dd>
<br>
<code>float Cost;</code>
<dd>Cost of the Action.</dd>
<br>
### Member Function(s):

<code><a href="exit_sequence.html">EExitSequenceType</a> Execute(<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Engine/AActor?application_version=5.7&lang=en-US">AActor</a>\* Owner);</code>
<dd>Where the functionality for the action lives. Always make sure you're overidding or it will return with the Hidden Enum Type.</dd>
<br>