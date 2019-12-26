# Using Master/Slave AIBrains

The **Master/Slave** system implements a set of methods to control AIBrains \(set as _Slaves_\) from other AIBrains \(set as _Masters_\) or other parts of the application through the Corgi/TopDown [Event System](https://corgi-engine-docs.moremountains.com/events.html).

### Using the System

The two main actors involved in this system are:

* **Brain Master**: not necessarily connected with a brain, it is used to send State change command events through dedicated channels
* **Brain Slave**: this element listens for State change command events and forces the AIBrain  behavior

{% hint style="info" %}
A Master can also be a Slave and listen to events \(even those dispatched by itself\).
{% endhint %}

####  Brain Master Ability

The **BrainMasterAbility** component lets you send state change commands to slave brains through a dedicated channel: usually this is achieved through an _AIActionChangeAIBrainStateCommand_ but you can access the _SendCommand_ method:

```csharp
SendCommand(string channelName, string newStateName, Transform target)
```

* _channelName_ is used to filter who will receive and execute the command
* _stateName_ is the state the AIBrain should transition in
* _target_ is the AIBrain target \(if any\)

#### The Brain Slave Ability

The **BrainSlaveAbility** component is used to receive state change commands through a dedicated channel.

{% hint style="info" %}
The slave can listen to one or more channels.
{% endhint %}

Whenever an event is received, the slave will try to change the AIBrain to the new state.





