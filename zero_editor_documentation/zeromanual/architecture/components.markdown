Components are bits of functionality that can be added to a game object. 
You can see the three components on our Player in the Properties window: Transform, Sprite, and RigidBody. 

 - Transform gives our game object a position, rotation, and scale. 
 - Sprite, which requires a Transform, allows us to visualize our game object.
 - RigidBody allows our Transform's Translation (position) and Rotation to be altered by the Physics engine. 

By using components to create our game objects we can easily reuse our code to make new and different items. This set-up can aid you in rapid prototyping when making your own games. 

Lets imagine we are making Bats, Wolves, and Birds. You could create 3 components:

 - BatLogic
 - WolfLogic 
 - BirdLogic



![badcomponentsexample](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/786.png)


While making them you find they have some things in common. Rather than copying and pasting (which becomes messy fast), we can use the component-based engine to our advantage and rearrange our logic. By making smaller components of functionality, we can factor out the code into common components making it easier to share between them, for instance:



![venn](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/789.png)


*The ones in gray are built-in to the Zero Engine*




![componentexample](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/787.png)


*Noticing shared functionality allows us to restructure our code*


By having these things separated you can more easily prototype and create new game objects.

For instance, in our example you later decide to create a flying healthpack. By utilizing the components you already 
ade, Flying and ChangeOtherHealth, most of the work is done.



![flyingpowerup](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/788.png)


*Something we// **can't** //make with BatLogic, WolfLogic or BirdLogic components*


Components are meant to be generic (when plausible), in order to allow for reuse. In many ways, components can be 
ade more generic by adding Properties to components.

In our example, we could make our DropLoot component more generic by having a Property represent which loot is dropped. With this new property our component could allow our Bat to drop health, while the Wolf drops a power-up, etc.

 #  Component Based Design
When building in the Zero Engine your Workflow can be optimized by building things in a component based manner. What this means is that instead of attaching a single script component to a single archetype and using it to drive all the functionality of that object, your workflow can be sped up by building specific smaller actions to specific components.

When choosing how to construct a set of script components for a project it's helpful to play several games in the chosen genre and look at what commonalities they have. Using what you find you can generate a set of components you will need. 
For instance, the shooter could have used an "input component" for mouse and keyboard input, a "shoot component" to handle how shooting is done in the world, a "movement component" to handle movement through the world, a "sound component" to handle the various sounds the player will create and other varied game logic components to handle things such as health (e.g. "health component"), power ups, collisions, etc. Enemies in a shooter would probably also need a "damage on collision component" and a "special shooting component" and a "behavior component".

As with all design the correct way depends on the project. No single set of script components that will give you all your required functionality for all projects.
 
  
  
  
  
  
  
  

 