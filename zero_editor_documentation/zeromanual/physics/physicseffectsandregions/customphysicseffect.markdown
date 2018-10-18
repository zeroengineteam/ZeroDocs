The [CustomPhysicsEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/CustomPhysicsEffect.markdown) component allows users to define their own physics effects through callback events. Forces can be applied to any object independently of this component, but this component will determine what objects forces should be applied to using the defined application modes (level, region, etc...).

This effect sends out two events: `CustomPhysicsEffectPrecalculatePhase` and `ApplyCustomPhysicsEffect`, both of which use the [CustomPhysicsEffectEvent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/CustomPhysicsEffectEvent.markdown) class. `CustomPhysicsEffectPrecalculatePhase` should be used to cache any unchanging values for the frame, such as the world-space values for the effect. `ApplyCustomPhysicsEffect` is sent out for each object that should have a force applied to it.

 #  Application Modes
It is up to a user to define what application modes the CustomPhysicsEffect works with.

---
 #  Related Materials
 ##  Manual
- [physicseffectsandregions.markdown](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)

 ##  Reference
- [CustomPhysicsEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/CustomPhysicsEffect.markdown)
- [CustomPhysicsEffectEvent](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/CustomPhysicsEffectEvent.markdown)
- [PhysicsEffect](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/PhysicsEffect.markdown) 

 