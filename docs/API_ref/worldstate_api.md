# World State

#### Description:

## Members

### Member Variables :

<code><a href="https://dev.epicgames.com/documentation/unreal-engine/map-containers-in-unreal-engine?application_version=5.5&lang=en-US">TMap</a><<a href="https://dev.epicgames.com/documentation/unreal-engine/API/Runtime/Core/FString?application_version=5.7&lang=en-US">FString</a>, bool> StateValues;</code>
<dd>Reflects the World state as a map of string boolean key pairs.</dd>
<br>
### Member Function(s):

<code>bool SatisfiesAll(const<a href="worldstate_api.html">FWorldState</a>& Other) const;</code>
<dd>Checks if the other World State satisfies all of the State Values.</dd>
<br>
<code>bool SatisfiesAny(const<a href="worldstate_api.html">FWorldState</a>& Other) const; </code>
<dd>Checks if the other World State satisfies any of the State Values.</dd>
<br>