# Node

#### Description:
The structure the planner uses for the search traversal.
Not Available in Editor.

## Members
### Member Variables :

<code><a href="worldstate_api.html">FWorldState</a> State;</code>
<dd>The World State refelected by the Node.</dd>
<br>
<code><a href="action_api.html">UAction</a>\* Action;</code>
<dd>The Action relected by the Node.</dd>
<br>
<code><a href="node_api.html">Node</a>\* Parent;</code>
<dd>The previous Node traversed in the search.</dd>
<br>
<code>float gCost;</code>
<dd>Disance between current node and starting Node</dd>
<br>
<code>float hCost;</code>
<dd>The theoretical distance from current node to the end.</dd>
<br>
<code>float fCost;</code>
<dd>Sum of gCost + hCost</dd>


