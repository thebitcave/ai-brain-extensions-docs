# Using Master/Slave AIBrains

The **Master/Slave** system implements a set of methods to control AIBrains \(set as _Slaves_\) from other AIBrains \(set as _Masters_\) or other parts of the application through the Corgi/TopDown [Event System](https://corgi-engine-docs.moremountains.com/events.html).

### Using the System

The two main actors involved in this system are:

* **Brain Master**: not necessarily connected with a brain, it is used to send State change command events through dedicated channels
* **Brain Slave**: this element listens for State change command events and forces the AIBrain  behavior

{% hint style="info" %}
A Master can also be a Slave and listen to events \(even those dispatched by itself\).
{% endhint %}

####  BrainMaster Ability

The **BrainMaster** ability component lets you send state change commands to slave brains through a dedicated channel: usually this is achieved through an _AIActionChangeAIBrainStateCommand_ but you can access the _SendCommand_ method:

```csharp
SendCommand(StateCommandChannel channel, string newStateName, Transform target = null)
```

* _channel_ is used to filter who will receive and execute the command
* _newStateName_ is the state the AIBrain should transition in
* _target_ is the AIBrain target \(if any\)

{% hint style="info" %}
This ability doesn't extend the regular Corgi/TopDown abilities, so it doesn't need a Character component: this means you can use anywhere you need \(i.e.: with a some trigger or any game logic\).
{% endhint %}

#### The Brain Slave Ability

The **BrainSlave** ability component is used to receive state change commands through a dedicated channel.

{% hint style="info" %}
The slave can listen to one or more channels.
{% endhint %}

Whenever an event is received, the slave will try to change the AIBrain to the new state.

As an alternative, the state change can be also forced through the TransitionToState\(\) method:

```csharp
TransitionToState(string newStateName, Transform target = null)
```

* _newStateName_ is the state the AIBrain should transition in
* _target_ is the AIBrain target \(if any\)

#### Channels

To use the Master/Slave communication system, you will have to create a **Channel**, that will be added to the slave channel list:

1. Select Create &gt; The Bit Cave &gt; MasterSlave &gt; State Command Channel
2. Rename the newly created asset
3. Add it to your slave _Channels_ list
4. Add the same channel to the master _AIActionChangeAIBrainStateCommand_ component





