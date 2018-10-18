The [FlowEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/FlowEffect.markdown) component applies forces to make an object move at a target speed in a given direction. This is often used to make an object move in the flow of another, such as a river or a tractor beam.



![FlowEffect](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46701.png)


Unlike a [ForceEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/ForceEffect.markdown) which applies a constant force in a direction, FlowEffect applies a variable force to make an object move at a constant speed in the flow direction. MaxFlowForce  allows the user to control how much force can be applied to reach this target speed. This can also be thought of as controlling the acceleration of objects within the field. Note: the flow portion of the effect only affects movement in the flow direction, not in the inward force direction.

Additionally, FlowEffect has the AttractToFlowCenter checkBox property to pull objects towards the flow center. This attractional force is similarly defined by a target speed and a max force. Note: this force only affects movement in the inward direction, not in the flow direction.

 #  Application Modes
FlowEffect is only expected to be used as a [Region](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Region.markdown) effect. Other application modes are undefined.

---
 #  Related Materials
 ##  Manual
- [physicseffectsandregions.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions.markdown)
- [ForceEffect.markdown](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/physics/physicseffectsandregions/ForceEffect.markdown)

 ##  Reference
- [FlowEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/FlowEffect.markdown)
- [ForceEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/ForceEffect.markdown)
- [PhysicsEffect](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/PhysicsEffect.markdown)
- [Region](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/code_reference/class_reference/Region.markdown)
 
  
  
  
  
  
  
  

 