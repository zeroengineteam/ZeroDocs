This lesson focuses on covering the basics of how object hierarchies work in Zero Engine.


 #  Learning Objectives


- Object hierarchy creation
- Transforming hierarchies
- World-space values and local-space values 
- Recognizing non-uniform scale problems  


 #  Level Setup


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `ParentSquare`
 - Under [ Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
  - Set VertexColor  to `[R:255, G:0, B:0, A:1.00]`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `ChildSquare`
 - Under [ Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[1, -1, 0]`
 - Under [ Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
  - Set VertexColor  to `[R:0, G:0, B:255, A:1.00]`
- In the `Objects Window`
 - `Drag and drop` ChildSquare object on top of ParentSquare object
   ![Parenting](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46756.gif)


 #  Parenting


As you have probably noticed, by dragging and dropping an object onto another, we've **attached** the former to the latter in a process called **parenting**. We then refer to this group of objects as a **hierarchy**, and it adopts new behaviors, most notably with respect to transformations. Let's take a look:

- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : ParentSquare object
- Experiment with Translation , Rotation and Scale 



![Translation2](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46733.gif) ![Rotation](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46735.gif) ![Scale](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46737.gif)


*Transforming the ParentSquare object*


Notice that, when we apply a transformation to the **parent object**, it is propagated to the **child object**. However, if we apply transformations to the child, it won't affect the parent.



![ChildTranslation](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46744.gif) ![ChildRotation](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46746.gif) ![ChildScale](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46748.gif)


*Transforming the ChildSquare object*


If we look at the [ Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) component (in the `Properties Window`) of both objects while applying transformations to the ParentSquare object, we notice that while its transform values are modified, the ChildSquare object's values remain the same. In Zero Engine, the [ Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) values displayed on a **root object** (top parent of a hierarchy) correspond to their **world values**; that is, the transform values relative to the space's origin at `[0, 0, 0]`. Meanwhile, transform values for **child objects** are displayed as **local values**; that is, the offset modifications relative to the **parent object**'s values.



![ParentTransform](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46752.gif) ![ChildTransform](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46754.gif)


*The `Properties Window` showing the ParentSquare object and ChildSquare object objects, respectively*


Notice the parent's **world value** is being modified, while the child's **local value** remains the same.


 #  Non-Uniform Scale


When dealing with object Hierarchies, one can accidentally stumble on the problem of non-uniform scale. This can be seen when, for example, a **parent object** is scaled non-uniformly (that is, its X, Y, and Z scale values aren't all the same) and its **child object** of it is rotated.


![NonUniformScale](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46821.gif)

This produces an often undesired **shear** effect, and is usually best avoided by making sure the **parent object** is always uniformly scaled. It should be noted that shearing does not affect the shape of [ colliders](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown).


 #  Related Materials
 ##  Manual
- [gameobjectsconcept](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/cogs/gameobjectsconcept.markdown)
- [commands](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [selectobject](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown)
- [colliders](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/physics/colliders.markdown)

 ##  Code Reference
 ###  Commands
- [ NewProject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
- [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)

 ###  Classes
- [cog](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/cog.markdown)
- [sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
- [transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown) 

 