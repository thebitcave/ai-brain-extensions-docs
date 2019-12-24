# Node Reference

The _AI Brain Graph_ comes packed with four types of nodes:

* _AI Brain State Node_
* _AI Transition Node_
* _AI Action Node_
* _AI Decision Node_

Additionally, when you work with a Subgraph, you have access to:

* _AI Brain Subgraph Nodes_
* _AI State In Nodes_
* _AI Transition Out Nodes_

### AI Brain State Nodes

This node represents a single state in the MMTools _AIBrain_.

Each state should be given a unique name by right-clicking the header and choosing _Rename_.

The _Set as starting state_ button will set the state as the first one in the MMTools _AIBrain_ states list.

#### Inputs

* **States In** \(_State_ connection\): a list of entry points from other states transitions
* **Actions** \(_Action_ connection\): a list of actions that should be performed when entering the state itself

#### Outputs

* **Transitions** \(_Transition_ connection\): a list of transitions that will let the system exit from this state 

![The State node](../.gitbook/assets/node_reference_001.png)

### AI Transition Nodes

This node represents a single transition from a state in the MMTools _AI Brain_: a state can have more than one transition.

If you wish, you can rename the node by right-clicking the header and choosing _Rename_ but this won't affect the AI generation.

{% hint style="info" %}
A Transition node should always have an _AIDecision_ attached
{% endhint %}

#### Inputs

* **Decision** \(_Decision_ connection\): a single _AI Decision Node_ that will let the AI Brain exit from the actual state
* **Input** \(_Transition_ connection\): a single connection from the _AI Brain State_

#### Outputs

* **True State** \(_State_ connection\): a connection to the state that should be activated when the decision is true
* **False State** \(_State_ connection\): a connection to the state that should be activated when the decision is false

![The Transition node](../.gitbook/assets/node_reference_002.png)

### AI Action Nodes

Action nodes are a graph representation of _AI Action_ components.

They comes with a single output element that should be connected to the state. This will tell the state itself that this action should be executed.

A node may have some parameters, corresponding with the MMTools _AIAction_ component.

The _Label_ field corresponds to the _AIAction Label_ attribute.

* _Decision_: a single _AI Decision Node_ that will let the AI Brain exit from the actual state

If you wish, you can rename the node by right-clicking the header and choosing _Rename_ but this won't affect the AI generation.

![The Action node for the AIActionDoNothing](../.gitbook/assets/node_reference_003.png)

### AI Decision Nodes

Decision nodes are a graph representation of _AI Decision_ components.

They comes with a single output element that should be connected to a state transition. This will define the condition to exit the state.

A node may have some parameters, corresponding with the MMTools _AIDecision_ component.

The _Label_ field corresponds to the _AIDecision Label_ attribute.

If you wish, you can rename the node by right-clicking the header and choosing _Rename_ but this won't affect the AI generation.

![The Decision node for the AIDecisionHealth](../.gitbook/assets/node_reference_004.png)

### AI Brain Subgraph Nodes

A subgraph node is a special state node, that lets you create a subgraph with all decision/action logic. You can create a subgraph asset and assign it to the _Subgraph_ field.

It can be set as a starting node \(in this case its inner starting node will be used\).

![An empty Subgraph node](../.gitbook/assets/node_reference_005.png)

To connect the subgraph node to the main brain graph you can use:

* _AI State In Nodes_: that will create dynamic entry point to the subgraph node
* _AI Transition Out Nodes_: that will create dynamic output from the subgraph node

![A Subgraph node with a brain graph assigned](../.gitbook/assets/node_reference_005_a.png)

### AI State In Nodes

This node exposes an _AI Brain State_ node inside a subgraph to the parent brain graph.

![The State In node](../.gitbook/assets/node_reference_006.png)

### AI Transition Out Nodes

This node exposes an _AI Transition_ node connection inside a subgraph to the parent brain graph.

![The Transition Out node](../.gitbook/assets/node_reference_007.png)





