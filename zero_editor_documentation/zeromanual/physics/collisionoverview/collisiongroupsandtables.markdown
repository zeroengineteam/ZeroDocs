[ CollisionGroups](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionGroup.markdown) and [ CollisionTables](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionTable.markdown) are intertwined resources in the physics system. A CollisionGroup defines a label for a [Colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/Colliders.markdown) to be used within a CollisionTable. A CollisionTable defines filters for pairs of CollisionGroups. These filters allow extra control over what collisions can take place. Additionally, filters can be configured to send extra events.

 #  CollisionGroup
A CollisionGroup defines a group (or label) for a Collider to take part in. This only serves to group certain Colliders together but doesn't change any behavior unless the active CollisionTable is configured to do so.

 #  CollisionTable
A CollisionTable is a resource property set on [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/PhysicsSpace.markdown) that defines pair-wise CollisionGroup relationships known as CollisionFilters. These filters control if a collision happens and if extra events are sent between group pairings.

 ##  CollisionFilters
A [CollisionFilter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionFilter.markdown) can be used to control if collisions happen between pairs of CollisionGroups. There are three primary states of a CollisionFilter:
 - **Resolve:** The default state for a filter. Says that collision resolution should happen as normal.
 - **SkipResolution:** Collision detection should be run as normal but resolution should not happen. This allows configuring pairs to be ghost collisions while still getting events.
 - **SkipDetection:** Collision detection should be skipped. Skipping collision detection also implies skipping collision resolution. This option is typically only set for performance reasons. This can also be used to prevent collision events from being sent to make gameplay logic easier.
 
Additional information can be configured on a [CollisionFilter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionFilter.markdown) to send out events through the use of CollisionFilterBlocks.

 ###  CollisionFilterBlocks
A [CollisionFilterBlock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionFilterBlock.markdown) is a sub-component on CollisionFilter used to control what kinds of events are sent out between groups. The current supported block types are:
 - **CollisionStartBlock:** Sends out the GroupCollisionStarted event when this grouping has a CollisionStarted.
 - **CollisionPersistedBlock:** Sends out the GroupCollisionPersisted event when this grouping has a CollisionPersisted.
 - **CollisionEndBlock:** Sends out the GroupCollisionEnded event when this grouping has a CollisionEnded.
 - **PreSolveBlock:** Sent out before collision is resolved. Allows altering information before a collision has happened.
 
All blocks can configure which groups in the filter to send to. The `SendEventsTo` properties control which objects in the pairing should get the event. The `A` and `B` referred to are in the same order as the GroupA  and GroupB  properties of the filter. If a filter has GroupA and GroupB as the same value, then this order is not defined.

Additionally, filter blocks contain the EventOverride  property that lets the user send out a custom event name instead of the default names. Note that these names do not currently show up in the `Events` namespace and must be connected to with a string literal.

The PreSolveBlock is a special block that should be used sparingly. As [PreSolveEvent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PreSolveEvent.markdown) before collisions are resolved. This event does not expect any drastic changes to the scene, such as removing components. Any complex behavior other than changing property values may crash the engine.

 #  Troubleshooting
One of the most common issues when using CollisionGroups and CollisionTables is forgetting to set the correct CollisionTable resource on the [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/PhysicsSpace.markdown). Additionally, see [WhyAreTheyNotColliding](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/physicstroubleshooting/whyaretheynotcolliding.markdown) for other common collision issues.

---
 #  Related Materials
 ##  Manual
- [CollisionEvents.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/CollisionEvents.markdown)
- [PhysicsSpace.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/PhysicsSpace.markdown)
- [Colliders.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/Colliders.markdown)
- [WhyAreTheyNotColliding.markdown](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/collisionoverview/PhysicsTroubleshooting/WhyAreTheyNotColliding.markdown)

 ##  Reference
- [CollisionGroup](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionGroup.markdown)
- [CollisionTable](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionTable.markdown)
- [CollisionFilter](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionFilter.markdown)
- [CollisionEvent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionEvent.markdown)
- [CollisionGroupEvent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionGroupEvent.markdown)
- [PreSolveEvent](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PreSolveEvent.markdown)
- [CollisionFilterBlock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionFilterBlock.markdown)
- [CollisionStartBlock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionStartBlock.markdown)
- [CollisionPersistedBlock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionPersistedBlock.markdown)
- [CollisionEndBlock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/CollisionEndBlock.markdown)
- [PreSolveBlock](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/PreSolveBlock.markdown) 

 