# Using Master/Slave AIBrains

The **Master/Slave** system implements a set of methods to control AIBrains \(set as _Slaves_\) from other AIBrains \(set as _Masters_\) or other parts of the application through the Corgi/TopDown [Event System](https://corgi-engine-docs.moremountains.com/events.html).

### Using the System

The two main actors involved in this system are:

* **Brain Master**: not necessarily connected with a brain, it is used to send State change command events through dedicated channels
* **Brain Slave**: this element listens for State change command events and forces the AIBrain  behavior

{% hint style="info" %}
A Master can also be a Slave and listen to events \(even those dispatched by itself\).
{% endhint %}

####  The Brain Master

\[TBD\]

#### The Brain Slave

\[TBD\]





