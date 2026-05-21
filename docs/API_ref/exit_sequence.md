# EExitSequenceType

##### Description :
Defines the possible termination states of a behaviour sequence during execution.

This enum is used to communicate the final or current execution state of a sequence when transitioning out of a node, task, or control flow operation.

## Values
|Name	|Description|
|-------|-----------|
|SUCCESS| The sequence completed successfully and met all required conditions.|
|FAILURE	|The sequence terminated because one or more required conditions failed.|
|INTERRUPTED	|The sequence was externally interrupted before completion.|
|INVALID	|The sequence entered an invalid state or produced an undefined result.|
|RUNNING	|The sequence is still executing and has not yet reached a terminal state.|
|DEFAULT	|Internal fallback value used when no explicit state has been assigned. Hidden from Blueprint exposure.|