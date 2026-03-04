---
order: 50
---

# Events

The Events module is a great way to easily implement a good design pattern for your games.

In fact, different features of your game may need to interact with other features.  
Doing communication directly between them will create dependencies and tight coupling between your game features, making them hard to change and maintain over time.

Here comes my plugin!  
By making a single point of communication, the different event subsystems will act as very accessible mediators between your game features.

## Example Use Case

Let say you have multiple game features, like a player with an inventory and a camera, an HUD displaying some information on screen, an achievement system recording various stats from the game, puzzles in your world to unlock some hidden places, etc.

![](/static/images/StatesAndEvents/events_diagram.svg)

As you can see in the diagrams above, having each feature directly communicating with the others will lead to a messy intricating of dependencies (arrows are direction of information).
Maintaining, debugging and modifying this tight-coupled code will quickly become a nightmare.

When using a mediator, like my events subsystems in my plugin, you are currently decoupling your different features, making it easy to modify, delete or even replace your feature with another. You can easily add new features without changing the whole codebase.

:::note
As you can see on my diagram above, not all dependencies disappear with a mediator. There are still some other ways of communication not going through the mediator.  
There are other great design patterns for those cases (e.g. interfaces) but not covered by this plugin.
:::

For example, the `HUD` or `Achievements` features (in the diagram with the `Events` mediator) are easily replaceable or removable without touching anything else in the code. Also you can easily debug and test your game features by adding some dev features to send some mockup events (e.g. a debug key to simulate an item received, will just send an event to the mediator and the HUD will display the notification like if it was a real item received by the player).

## Getting Started

There are 3 scope levels for the event, each one is a subsystem:

- The `Game Instance` scope: the event manager is alive from the game start and until the game is closed.
- The `World` scope: each time you load a new world (e.g. map transition) a new event manager is created.
- The `Local Player` scope: each local player will have an event manager.

Choose the corresponding subsystem depending on your use case, but each one works the same.

### Create your Event Classes

First things first, you need events to send and receive between your game features.

So, let's create some event classes by deriving from the `CX Event` class of the plugin.

![](/static/images/StatesAndEvents/event_create.jpg)

You can add any variables to them, for example, for an `Inventory Changed` event, you may want a reference to the `Inventory Item` and the quantity added/removed (if negative).

:::note
Make sure to mark your variables as `Expose on Spawn`, it will be handy later!
:::

![](/static/images/StatesAndEvents/event_vars.jpg)

### Sending an Event

To send an event, construct a new object of the event you want to send, and then you simply have to retrieve the subsystem you want and call `Send Event` on it.

![](/static/images/StatesAndEvents/event_get_subsystem.jpg)

![](/static/images/StatesAndEvents/event_send.jpg)

### Receiving an Event

To receive an event, it's really easy too.
Just get the subsystem you want and bind an event to the delegate of the subsystem.

You then cast the `Event` input to the event class you want.

:::note
If you want to receive multiple types of event, you just have to chain the cast nodes using the `Cast Falied` output.
:::

![](/static/images/StatesAndEvents/event_receive.jpg)
