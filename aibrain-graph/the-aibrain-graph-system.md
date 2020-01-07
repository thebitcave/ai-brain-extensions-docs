# The AIBrain Graph System

The **AI Brain Graph** editor is a tool used to create Corgi/TopDown Engines AI logic through a visual node editor.

{% hint style="info" %}
The tool is built on top of [xNode](https://github.com/Siccity/xNode) by Thor Brigsted.
{% endhint %}

## Working with the Graph

### Creating a Graph

A graph is an asset stored in your project _Assets_ folder. To create one:

1. Right click anywhere in the Assets folder
2. Select Create &gt; The Bit Cave &gt; AI Brain Graph
3. Rename the brain asset
4. Double click on it to show the editor window

### Creating a SubGraph

Like the graph, a subgraph is an asset stored in your project _Assets_ folder. To create one:

1. Right click anywhere in the Assets folder
2. Select Create &gt; The Bit Cave &gt; AI Brain Graph
3. Rename the brain asset
4. Double click on it to show the editor window

### Adding Nodes

To add nodes to the graph \(or subgraph\) simply right click on any free space and select the desired node.

{% hint style="info" %}
Please check the [Node Reference](node-reference.md) page for a list of available nodes.
{% endhint %}

## Using a Graph on a Character

When you add a graph to a Corgi/TopDown character, the system will parse your nodes and will translate them to _AIBrain_/_AIAction_/_AIDecision_ components.

To achieve this, all you have to do is to add one of these components:

* AI Brain Generator: this component will generate all needed elements to the character 
* AI Brain Pluggable: similar to the previous component, but the generation will be at runtime

{% hint style="info" %}
Please check the [Corgi](corgi-engine-getting-started-tutorial.md) and [TopDown](topdown-engine-getting-started-tutorial.md) getting stated tutorials for an example on how to use these components.
{% endhint %}



