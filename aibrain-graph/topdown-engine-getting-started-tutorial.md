---
description: >-
  In this tutorial you'll learn the basic steps of the AIBrain graph for TopDown
  Engine.
---

# TopDown Engine - Getting Started Tutorial

**Note**: To get you started using the AI Brain Graph, you should first follow the [Install instructions](../install-instructions.md) and check that everything is working.

### The Tutorial Scene

First of all, look for the _MinimalAI3D\_Tutorial_ scene \(and open it\), that will serve as a starting point for this tutorial. Basically, it is the TopDown _MinimalAI3D_ scene with all enemies removed \(with the exception of _PatrolAndMoveAI_\).

1. Open the _AIs_ group to check the content: you will find the _PatrolAndMoveAI_ prefab along with two other gameObjects \(stripped out of all AI components\): _PatrolAndMoveAI\_Generated_ and _PatrolAndMoveAI\_Pluggable._

### Creating the AI Brain Graph

To start working with the graph, you'll need to create an AI Brain Graph:

1. In the Project panel, right-click the mouse button and select _Create &gt; The Bit Cave &gt; AI Brain Graph_
2. Rename the newly created asset _PatrolAndMoveBrain_ \(or anything you deem appropriate\)
3. Double-click on the asset to open the Editor

![](../.gitbook/assets/topdown_tutorial_001.png)

### The PatrolAndMoveAI Brain Structure

Select the _PatrolAndMoveAI_ prefab in scene and look at the _AI Brain_, _AI Actions_ and _AI Decisions_ components: we want to replicate the same structure with the AI Brain Graph:

* The _AI Brain_ has two states: _Patrolling_ and _MoveTowardsTarget_
* While in _Patrolling_ the character will perform an _AIActionMovePatrol3D_ and an _AIActionAimWeaponAtMovement_ action
* While in _MoveTowardsTarget_ the character will perform an _AIActionMoveTowardsTarget3D_ and an _AIActionAIMWeaponATMovement_ action
* The chracters will exit the _Patrolling_ state if the target is within range \(_AIDecisionDetectTargetRadius3D_\)
* The character will not exit the M_oveTowardsTarget_ state after a while

To create the AI Brain Graph we will need these nodes:

* Two states
* Two transistions
* Three actions
* One decision

#### Creating the States



