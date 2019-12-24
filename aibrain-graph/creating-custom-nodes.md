# Creating Custom Nodes

If you are working on a game made with Corgi Engine, chances are you are going to create new _AI Decisions_ and _AI Actions_: the AI Brain Graph is completely extensible, so you can create your own nodes.

Basically, each node acts as a component generator for the corresponding action or decision, so you'll just have to pass the correct attributes.

### Creating AI Action Nodes

To create your own action nodes, you will have to extend the _AIActionNode_ class and override a single method, called _AddActionComponent_: this component returns an instance of the Corgi _AIAction_ you want to add with this node.

As an example, please take a look at the _AIActionJumpNode_ that corresponds to the _AIActionJump_ for the Corgi Engine:

```csharp
using MoreMountains.CorgiEngine;
using MoreMountains.Tools;
using UnityEngine;

namespace TheBitCave.CorgiExensions.AI
{
    /// <summary>
    /// A node representing a Corgi <see cref="MoreMountains.CorgiEngine.AIActionJump"/> action.
    /// </summary>
    [CreateNodeMenu("AI/Action/Jump")]
    public class AIActionJumpNode : AIActionNode
    {
        public int numberOfJumps = 1;

        public override AIAction AddActionComponent(GameObject go)
        {
            var action = go.AddComponent<AIActionJump>();
            action.Label = label;
            action.NumberOfJumps = numberOfJumps;
            return action;
        }
    }
}
```

Please note the `[CreateNodeMenu("AI/Action/Jump")]` that adds this node to the graph contextual menu.

### Creating AI Decision Nodes

To create your own decision nodes, you will have to extend the _AIDecisionNode_ class and override a single method, called _AddDecisionComponent_: this component returns an instance of the Corgi \(or TopDown Engine\) _AIDecision_ you want to add with this node.

As an example, please take a look at the _AIDecisionHitNode_ that corresponds to the _AIDecisionHit_ :

```csharp
using UnityEngine;
using MoreMountains.CorgiEngine;
using MoreMountains.Tools;

namespace TheBitCave.CorgiExensions.AI
{
    /// <summary>
    /// A node representing a Corgi <see cref="MoreMountains.CorgiEngine.AIDecisionHit"/> decision.
    /// </summary>
    [CreateNodeMenu("AI/Decision/Hit")]
    public class AIDecisionHitNode : AIDecisionNode
    {
        public int numberOfHits = 1;

        public override AIDecision AddDecisionComponent(GameObject go)
        {
            var decision = go.AddComponent<AIDecisionHit>();
            decision.Label = label;
            decision.NumberOfHits = numberOfHits;
            return decision;
        }
    }
}
```

Please note the `[CreateNodeMenu("AI/Decision/Hit")]` that adds this node to the graph contextual menu.

