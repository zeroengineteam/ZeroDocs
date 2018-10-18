CollisionGroups allow users to categorize colliders into different groups. CollisionTables define the relationships between those groups and the behavior of those colliders when they collide with one another.


 #  Learning Objectives


- CollisionGroups
- CollisionTables
- CollisionGroup relationships


 #  Level Setup


Before jumping into how CollisionGroups are used, we need to set up a simulation to use them in.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Rename Sprite object to `Platform`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Scale  to `[10,1,1]`
 - [Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [BoxCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [CreateSphere](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsphere)
- In the `Properties Window`
 - Rename Sphere object to `DefaultSphere`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[-3,5,0]`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Duplicate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#dupliate)
- In the `Properties Window`
 - Rename the duplicate DefaultSphere object to `SkipResolutionSphere`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0,5,0]`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [Duplicate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#dupliate)
- In the `Properties Window`
 - Rename the duplicate SkipResolutionSphere object to `SkipDetectionSphere`
 - Under [Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[3,5,0]`


 #  Collision Groups


A [CollisionGroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiongroup.markdown) is a resource assigned to one or more colliders, usually before the game is run.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94461.png)


*CollisionGroup enum property on the [SphereCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spherecollider.markdown) component*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a CollisionGroup resource using the Default template template and name it `SkipResolution`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a CollisionGroup resource using the Default template template and name it `SkipDetection`
- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : SkipResolutionSphere object
- In the `Properties Window`
 - Under [ SphereCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spherecollider.markdown)
  - Set CollisionGroup enum to `SkipResolution`
- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : SkipDetectionSphere object
- In the `Properties Window`
 - Under [ SphereCollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spherecollider.markdown)
  - Set CollisionGroup enum to `SkipDetection`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![notable](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94463.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

You will notice that the behavior of the balls has not changed as of yet. This is because in order for CollisionGroups to be used, they must be included in the space's [CollisionTable](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiontable.markdown).


 #  CollisionTables


A [CollisionTable](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiontable.markdown) defines the relationship between CollisionGroup pairs.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
  - Create a CollisionTable resource using the Default template template and name it `GameTable`

When a [CollisionTable](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiontable.markdown) is created, the `CollisionTableEditor Window` opens.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94465.png)


*The `CollisionTableEditor Window`*


This is the default configuration for a CollisionTable. It takes all the existing CollisionGroups and generates a permutation table of all the pairs.

- In the `CollisionTableEditor Window`
 - Set `DefaultGroup` / `SkipResolution` to `SkipResolution`
 - Set `DefaultGroup` / `SkipDetection` to `SkipDetection`



![setting_Tables](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94835.gif)


- Close the `CollisionTableEditor Window`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![notable](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94463.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

You are probably wondering why the groups still aren't working. There is still one more step to perform for the groups to take effect: we have to tell the Space to use the CollisionTable we have created instead of the default CollisionTable.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ SelectSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#selectspace)
- In the `Properties Window`
 - Under [PhysicsSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsspace.markdown)
  - Set CollisionTable enum to `GameTable`



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94469.png)


*Setting the CollisionTable enum property for the Space*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![noprint](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94471.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

Now we can see the two spheres, which are set up to skip resolution and detection respectively, fall through the platform as expected. We still need to prove to ourselves, however, that the SkipResolutionSphere object is still at least detecting the collision.


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `PrintCollision`
- Update the `PrintCollision` script to the following:

```lang=csharp, name="PrintCollision"
class PrintCollision : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Owner, Events.CollisionStarted, this.OnCollisionStarted);
  }

  function OnCollisionStarted(event : CollisionEvent)
  {
    Console.WriteLine("CollisionStarted: `this.Owner`, Other: `event.OtherObject`");
  }
}
```


- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : SkipResolutionSphere object
- In the `Properties Window`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `PrintCollision`
- [ Select](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown) : SkipDetectionSphere object
- In the `Properties Window`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `PrintCollision`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Console](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#console)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![printcollision](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/94783.gif)


*CollisionGroups properly configured, and printing collision detection*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

As can be seen by the printed message in the above image, the SkipResolutionSphere object is indeed detecting collision, whereas the SkipDetectionSphere object is not.

Collision groups and tables allow for a lot of flexibility in the usage of collision for game logic. They can also allow for significant performance improvement in games that heavily use physics.


 #  Related Materials
 ##  Manual
- [LauncherNewProject](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/launchernewproject.markdown)
- [commands](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [resourceadding](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- [addremovecomponent](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown)
- [selectobject](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/selectobject.markdown)

 ##  Reference
 ###  Commands
- [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- [ CreateSphere](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsphere)
- [ Duplicate](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#duplicate)
- [ SelectSpace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#selectspace)

 ###  Classes
- [spherecollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spherecollider.markdown)
- [transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
- [physicsspace](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsspace.markdown)
- [collisiongroup](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiongroup.markdown)
- [collisiontable](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/collisiontable.markdown)

 ###  Events
- [ CollisionStarted](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/event_reference.markdown#collisionstarted)

 ###  Enums
- [ CollisionFilterCollisionFlags](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#collisionfiltercollision)

 ##  Development Task 
- {T1176} 

 