Explain has parameter `mode` which can be one of those:
1. *queryPlanner* - Mongo runs [[query optimizer]] to choose the winning plan for the operation under evaluation.
2. *executionStats* - Mongo runs the [[query optimizer]] to choose the winning plan, executes the winning plan to completion, and returns statistics describing the execution of the winning plan. However, [[`executionStats`]] does not provide query execution information for the rejected plans.
3. *allPlansExecution* - MongoDB runs the [[query optimizer]] to choose the winning plan and executes the winning plan to completion. In `"allPlansExecution"` mode, MongoDB returns statistics describing the execution of the winning plan as well as statistics for the other candidate plans captured during [[plan selection]].
   If the query optimizer considered more than one plan, [[`executionStats`]] information also includes the _partial_ execution information captured during the [[plan selection phase]] for both the winning and rejected candidate plans.

## Output
Explain() operations can return information regarding:

- `explainVersion`, the output format version (for example, `"1"`).
- `command`, which details the command being explained.
- `queryShapeHash`, starting in MongoDB 8.0, which is a hexadecimal string with the hash of a [[query shape]].
- [[`queryPlanner`]], which details the plan selected by the [[query optimizer]] and lists the rejected plans.
- [[`executionStats`]], which details the execution of the winning plan and the rejected plans.
- [[serverInfo]], which provides information on the MongoDB instance.
- `serverParameters`, which details internal parameters.

## How to work with Explain()

[Youtube: Tips and Tricks for Query Performance: Let Us .explain() Them](https://www.youtube.com/watch?v=UMzt4PbHtm8)

General algorithm when query comes into play:
![[Queryland_alg.png]]

This algorithm we can split into 4 next parts:
![[Queryland_parts.png]] 

## Explain as Island

We can view at `explain()`'s output as roadmap and split it as 4 parts to read it easier. Not all output require attention - sometime we must focus only on few things: 

![[ExplainAsIsland.png]]

By "removing noise" we'll get kind of landmarks which will help to get desired:
![[RemovedNoise.png]]

Grabbing together that plan can be divided at 4 parts and how and what attention must be paid we'll get next general map:
![[GenealRoadmap.png]]

## Explain Output Structure

The `explain` results present the query plans as a tree of stages.
Each stage passes its resulting documents or index keys to the parent node. The leaf nodes access the collection or the indices. The internal nodes use the documents or the index keys that result from the child nodes. The root node indicates the stage that MongoDB ultimately derives the result set from.

Stages are descriptive of the operation. For example:
- `COLLSCAN` for a collection scan
- `IXSCAN` for scanning index keys
- `FETCH` for retrieving documents