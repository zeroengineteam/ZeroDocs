An Archetype [ Resource ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/resources.markdown) is the serialized definition of a Cog (Game Object Composition) which can be used as a template from which to create new cogs from. The core benefit of Archetypes is that any changes made to the Archetype affect each object created from the Archetype. These objects are called **instances** of the Archetype.


 #  Advantages of Archetypes
Often in games we find reasons to have several copies of the same object in the game at once. The game could take place in a forest with thousands of trees and rocks with subtle differences. It could be an arcade shooter with hundreds of identical enemies swarming towards the player. In any case where there is duplicate object creation Archetypes can save us both development time, and performance at runtime.

If a level has hundreds of instances of the same character Archetype, all those characters can be modified at the same time by modifying the Archetype. Where as if each chracter was not Archetyped, they would have to be individually modified which is slow. One could also group select and modify which may not be practical depending on the placement of objects in the level. While making full use of the Archetype system takes forethought, it increases development efficiency over the course of a project.

Take the example of a game with an army of identical characters which are made out of instances of just 1 or 2 Archetypes the engine can load it much faster than if each character was its own unique Cog with no shared Archetype. This is because after the Archetype is loaded by the engine, it can be used by the engine to create/render the instances of it in the army. As opposed to the engine having to load a copy of the object data for each non-Archetyped tree object.

 #  Creating Archetypes
Creating an Archetype is fairly simple.



![2017_07_07_11_34_28_Zero_Editor_ArchetypeDocumentation](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46803.png)


Simply provide an name for the new Archetype in the Archetype field and press Enter or the ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46805.png) button. This will create the new Archetype resource from the selected object causing to to appear under the Archetype tag in the Resource Window.

 #  Creating Objects from Archetypes
Creating a new instance of an existing Archetype is simple and can be done through multiple approaches.

 ##  Instance from the Resource Library
By clicking and dragging an Archetype resource from the resource library into the Level Window we can create a new instance of that Archetype.



![ArchetypeInstantiationFromLibrary](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46827.gif)


 ##  Copying an Instance
Objects which are an instance of an Archetype can be duplicated via copy & paste to create a new instance of the same Archetype.

- `ctrl + c`
- `ctrl + v`



![ArchetypeCopyPaste](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46829.gif)


*Here `ctrl + +c` and `ctrl + v` are used then `ctrl + click + drag`*

 ##  Instances at Runtime
Archetypes are essential for creating objects at runtime. Here is a short example of how one might create instances of an Archetype at runtime.

```
class ObjectSpawner : ZilchComponent
{
  [Property]
  var ObjectArchetype : Archetype = Archetype.MyArchetype;
  
  [Property]
  var SpawnRate : Real = 1.0;
  
  var Timer : Real = 0.0;
  
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Space, Events.LogicUpdate, this.OnLogicUpdate);
  }

  function OnLogicUpdate(event : LogicUpdate)
  {
    this.Timer += event.Dt;
    if(this.Timer > this.SpawnRate)
    {
      this.Timer = 0.0;
      this.Space.Create(this.ObjectArchetype);
    }
  }
}
```



![ArchetypeInstantiationRuntime](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46831.gif)


*Here you can see the above `ObjectSpawner` script running.*


As you can see the function `Space.Create()` is how you instantiate Archetypes at runtime from script. There is also `Space.CreateAtPosition()` which allows you to specify a position for the object to spawn at as opposed to the Space origin.

 #  Basic Archetype Modifications
When an Archetype instance is modified it turns orange.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46846.png)



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46848.png)

Below the behaviors various types of modifications are described.

 ##  Property Modifications
When a property field of an  an Archetype instance is edited it is turned orange to mark it as modified. This is a common theme as other items will turn orange when modified.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46838.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46836.png)



 ### Local Modification Override
It should be noted that based on the above modifications to `Transform` the Archetype instance will not be marked as modified.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46844.png)

This is because the properties such as `Transform.Translation`, `Transform.Rotation`, `Transform.Scale`, and `Area.Size` have the `LocalModificationOverride` attribute which prevents that property from normally interacting with archetype updates and reversion. A property with the `LocalModificationOverride` attribute will not be uploaded with other modifications when a modified instance is uploaded to the archetype. Overrridden properties will also not be modified when an instance is reverted to archetype. The `LocalModificationOverride` attribute can be applied to properties in custom Zilch components as well.

 ##  Component Modifications
Adding, removing, or reordering a component to an Archetype instance modifies it from Archetype.

*Unmodified*


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46867.png)


*Component added*



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46850.png)


*Component removed*



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46852.png)


*Components reordered*



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46871.png)




 ## Child Modifications
Adding, removing, reordering a child object from an Archetype instance will also mark the Archetype as modified.

*Unmodified*


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46873.png)


*Child added*



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46881.png)


*Child removed*



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46877.png)


*Children reordered*



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46879.png)


It is important to note that neither component nor child modifications have functionality equivalent to LocalModificationOverride available. Property modifications usually adjust some factor of a piece of functionality. However, component and child object operations have the potential change the fundamental functionality of the Archetype. In the case where a certain component or child object modification becomes common place it should be add to the original archetype (and have the originally unmodified instances use LocalModificationOverride) or create a new archetype with the modifications.

 # Upload To Archetype
Above we discussed the various modification types you can make to an Archetype. It is very common for a developer to create many instances of an Archetype then modify some paticular instance. However, sometimes we want to go the opposite direction and apply modifications we have made to an individual instance to the Archetype. Thinking about the army of characters we used as an example earlier. Imagine we had been changing hat colors for awhile and we decide we like a paticular color for the default. By clicking ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46805.png) we can turn a[pply this change to all unmodified instances of the Archetype. This is called uploading to Archetype. Whereas if we give it a new Archetype name and click ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46805.png)  we will create a new Archetype.



![UploadToArchetype](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46892.gif)

Here we modify right two of the three Archetype instances. The middle instance, which is modified, is then uploaded to the Archetype causing the modification to be applied to the unmodified instance on the left. Notice that the other modified instance on the right does not turn Red. This is due to the right instance being already modified from the orginal Archetype (meaning it is modified from the newly uploaded version as well).

 # Revert To Archetype
 ## Reverting Cogs
Often developers make accidental or undesireable changes to an Archetype instance and have legitamate reasons to not want to undo everything to revert the instances back to their original state. This is one of the many reasons Archetype instances can be reverted to the current state of the Archetype resource using the ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46894.png) button next the Archetype field in the property window.

*Here you can see the middle sprite reverted to match the orginal Archetype.*


![RevertToArchetype](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46896.gif)


 ## Reverting Properties
Often it is necessary to revert individual properties on an Archetype instance. This is a simple operation:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46898.png)


By using `RightClick` on the property grid one can open the context menu allowing the property to be reverted without affecting the rest of the instance. This is important and simply setting the modified field to the same value will not make the field appear un-modified to the engine.

 ## Reverting Locally Removed Child
By using `RightClick` on the greyed out representation of objects which have been removed from the child hierarchy of an Archetype one can `Restore` an object back into the heirarchy.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46900.png)

 ## Reverting Child Order
If children in an Archetype hierarchy are reordered, their order can be reverted to match the current Archetype by using `RightClick` on the Archetype instance root object and selecting `Restore Child Order`.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46902.png)


Reverting child modifications are important as for reasons of reverting 

 # Marking as Modified
There are time where an Archetype is about to be upload, but it is realized there is a single unmodified instance of the Archetype which should not be updated to the new Archetype. In this case it is possible to manually mark a property as modified even if its value matches that of the original Archetype. This allows the Archetype to be updated without having the changes affecting the instance which has a locally overridden property.



![LocalModificationOverride](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46906.gif)


Once again let's think back to the army of characters all created from the same Archetype, specifically the example where we have been experiementing and have just settled in on the hat color we would like to be the default for the whole army. Now imagine we want the leader to keep the original hat color. By marking the leader's hat color as modified, when we upload the new color to the Archetype the leader will not be affected.

(NOTE)**Nested Archetypes**: Nested archetypes are supported and are currently int the #zero_editor_documentation pipeline: T391

 # Related Materials
 ## Manual
- [ Resource ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/architecture/resources.markdown) 
  
  
  
  
  
  
  

 