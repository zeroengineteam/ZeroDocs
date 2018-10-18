This lesson covers some of the more advanced features of Zero Engine's Tile Editor tool. The [ previous lesson](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/editor/tile_editor.markdown) covers the basics.


 #  Learning Objectives


- Tile colliders
- Tile palettes


 #  Level Setup


- Reopen the TileEditor zero project project from the [ previous tutorial](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/editor/tile_editor.markdown)


 #  Tile Archetypes


When you place tiles with the TileEditor2D tool, they are not created as individual game objects. Instead, they are placed into a tilemap, which allows multiple tiles to be merged into a single cog, saving memory and processing time. As a result, tile archetypes are used a bit differently than conventional archetypes.

When the engine creates a merged tilemap object, it is always given a [ MultiSprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/multisprite.markdown) component, so you don't necessarily need to put one on your tile archetype. If you do, though, the resultant merged tilemap will use the settings specified by your archetype's MultiSprite. Similarly, a merged tilemap object optionally has a [ MeshCollider](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/colliders/meshcollider.markdown) component, so you only need to give a tile archetype that component if you want the merged tilemap to use the settings from the MeshCollider for your archetype.

Let's create a tile archetype with some custom game logic and add it to our level.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a ZilchScript resource using the Component template template and name it `ReloadLevelOnCollisionStarted`
- Update the `ReloadLevelOnCollisionStarted` script to the following:

```lang=csharp, name="ReloadLevelOnCollisionStarted"
class ReloadLevelOnCollisionStarted : ZilchComponent
{
  function Initialize(init : CogInitializer)
  {
    Zero.Connect(this.Owner, Events.CollisionStarted, this.OnCollisionStarted);
  }
  
  function OnCollisionStarted(event : CollisionEvent)
  {
    this.Space.ReloadLevel();
  }
}
```

This component will cause the level to be reloaded if the player character (or, really, anything at all) comes in contact with it. We can use it to create "deadly" tiles.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateTransform](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createtransform)
- In the `Properties Window`
 - Rename Transform object to `DeadlyTile`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : [ MeshCollider](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/colliders/meshcollider.markdown)
 - Under [ MeshCollider](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/physics/colliders/meshcollider.markdown)
  - Set Ghost checkBox to `true`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `ReloadLevelOnCollisionStarted`
 - Set Archetype  to `DeadlyTile`
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Delete](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#delete) the DeadlyTile object

This new archetype can now be used with the TileEditor2D tool with any sprite source in the project.

- Select the {nav icon=pencil, name=TileEditor2D} tool
- In the `Tools Window`
 - Set Archetype enum to `DeadlyTile`
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108811.png)
- In the `Level Window`
 - Using the {nav icon=pencil, name=TileEditor2D} tool, create a lava pit in the level with both the plain lava sprite source ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108750.png) and the animated LavaSurface texture sprite source ![Animated Lava Surface at 250 ms Delay](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108754.gif)
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108818.png)

While you're painting tiles into a level, it can sometimes be easy to lose track of which tiles have what archetypes. Fortunately, the TileEditor2D tool has a feature to help with that.

- In the `Tools Window`
 - Set ShowArchetype checkBox to `true`

With ShowArchetype checkBox enabled, the editor will show the name of the archetype that was used for each tile in the level.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108820.png)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)



![Playing with Lava](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108831.gif)


The lava seems to be working as intended. Now let's get a closer look at some of what's going on here. Pressing `F9` while the game is running begins **Edit In Game** mode, which makes the editor open the game session and all of its spaces for editing while it's still running. This is a very powerful and useful feature in any situation, but it is great for showing off some of the details of how the TileEditor2D tool merges groups of tiles.

- While the game is running, press key the `F9` key
- In the `Objects Window`
 - Under TileMap object
  - Observe the objects that are there

When the game starts, before the first frame, the engine prepares level by merging the tilemaps into their logical pieces. Note how each separate platform is its own object, and the lava is separate from the ground.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108925.png)


Observe how the colliders on each object use meshes that are dynamically generated to perfectly fit the pieces they're placed on.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108927.png)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)

Let's move on.


 #  Tile Collision


So far, every tile we've placed has used a simple box-shaped collider. The TileEditor2D tool isn't limited to just boxes, though. It can use any [ PhysicsMesh](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicsmesh.markdown) as its collision shape. Zero Engine comes with a set of common ramps and boxes to be used with tilemaps.

- Download the following tile sheet:
  ![SimpleTriangleTiles](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108937.png)
- `Drag and drop` the file into the `Level Window`
- In the `Group Import Options Window`
 - Set ImportImages enum to `Sprites`
 - Press the `Import All` button
- In the `Library Window`
 - Under the SpriteSource  tag
  - Double-click  `SimpleTriangleTiles`
- In the `Sprite Source Editor Window`
 - Press the `Convert To Animation` button

This sheet's tiles are 64-pixel squares.

- In the `Sprite Importer Window`
 - Set FrameWidth  to `64`
 - Press the `Add Frames as Sprites` button
 - Press the Close button button

Now let's add some sloped surfaces to the level. Each of the new triangular tile sprites will pair perfectly with one of the sloped collider options:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108941.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108943.png)



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108945.png) ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108947.png)


(NOTE) **No Collision:** To remove the collider from a tile, click the little {icon times} button on the Collision enum property: ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108961.png) Similarly, you can remove the sprite from a tile by clicking the corresponding button on the Sprite enum property.

- Select the {nav icon=pencil, name=TileEditor2D} tool
- In the `Tools Window`
 - Set Archetype enum to `DefaultTile`
 - Set Sprite enum to `SimpleTriangleTiles000`
 - Set Collision enum to `SlopeLeft`
- In the `Level Window`
 - Use the Draw sub-tool to paint a slope
   ![Painting a Slope](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108933.gif)

It's wise to fill in the underside of the slope to alleviate potential collider-catching problems.

- In the `Tools Window`
 - Set Sprite enum to `SquareBordered`
 - Set Collision enum to `Box`
- In the `Level Window`
 - Use the Draw sub-tool to fill in the underside of the slope
   ![Filling in the Slope](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108935.gif)
 - Using the new sloped sprite sources and the sloped colliders, paint additional slopes as desired
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108949.png)

By this point, you might be getting tired of having to set the Archetype enum, Sprite enum, and Collision enum properties every time you want to change tiles. That's where tile palettes come in!


 #  Tile Palettes


A **tile palette** is like a shelf that stores tile definitions, making it easy to switch between tiles with a single click. It occupies the bottom portion of the TileEditor2D tool's property grid, and expands as necessary. Creating a tile palette is simple.

- Select the {nav icon=pencil, name=TileEditor2D} tool
- In the `Tools Window`
 - Press the Add button button to the right of the TilePalette enum property
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108951.png)
- In the `Add TilePaletteSource Resource Window`
 - Set Name  to `Grass`
 - Press the Create button button
- Select the {nav icon=pencil, name=TileEditor2D} tool
- In the `Tools Window`
 - Set TilePalette enum to `Grass`



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108953.png)


The new palette is mostly empty, but it's easy to add to it. Just set up a tile the way you want it, and then click in any empty space in the palette view to place it there.

- In the `Tools Window`
 - Set Archetype enum to `DeadlyTile`
 - Set Sprite enum to `LavaSurface`
 - Set Collision enum to `HalfBoxBottom`

Notice how the palette already reflects the changes you have made to its **selected tile**, which is outlined in blue:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108957.png)


To add a new tile to the palette, **first click in an empty spot** in the palette view and then set its properties. To modify an existing tile in the palette, **select the tile you want to modify**, and then set its properties. To remove a tile from the palette, **right-click the tile** you want to remove. In this manner, you can make things very convenient for yourself while you're editing a level.



![Adding Tiles to a Palette](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109087.gif)


*The left mouse button adds tiles, and the right mouse button removes them*


- In the `Tools Window`
 - Create a full tile palette with archetypes, sprites, and colliders
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108963.png)

(NOTE) **Zooming the Palette View:** To make more room for yourself, you can hold key the `Ctrl` key and scroll  the **mouse wheel** to zoom the palette view in and out.

You can make multiple tile palettes to make it easy to facilitate making levels that are set in different locations, or use different art styles, and so on.

- In the `Tools Window`
 - Press the Add button button to the right of the TilePalette enum property
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109089.png)
- In the `Add TilePaletteSource Resource Window`
 - Set Name  to `Slopes`
 - Press the Create button button
- Select the {nav icon=pencil, name=TileEditor2D} tool
- In the `Tools Window`
 - Set TilePalette enum to `Slopes`
 - Fill in the tile palette with the triangular sprite sources and the SquareBordered texture sprite source, with appropriate collisions set for each tile
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108967.png)

Let's use both palettes to create a new level.

(NOTE) **TiledDrawing:** Watch what happens when you `left-click and drag` in the tile palette view to select multiple tiles, and then paint with them. Then, set the TileEditor2D tool's TiledDrawing checkBox property to `true` and then paint again. See the difference? TiledDrawing checkBox is great for preserving a specific configuration of tiles that you have laid out in the palette, but it also works with a brush committed with the Selection sub-tool! ![TiledDrawing Demonstration](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108992.gif)

- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ Add Resource](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
 - Create a Level resource using the {nav icon=clone, name=2D Level} template and name it `OtherLevel`
- Select the {nav icon=pencil, name=TileEditor2D} tool
- In the `Level Window`
 - Click  the **No TileMap Object** message
- In the `Tools Window`
 - Set TilePalette enum to `Grass`
- Using the `Grass` palette, create the main pieces of a level
  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108996.png)
- In the `Tools Window`
 - Set TilePalette enum to `Slopes`
- Using the `Slopes` palette, add slopes to the level
  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109006.png)
- In the `Library Window`
 - Under Archetype 
  - `Left-click and drag` `SweptPlayer2D` into the `Level Window`
- In the `Properties Window`
 - Configure the `SweptController` component's properties as desired
- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)



![Final Tiled Game](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109010.gif)


- [ Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)


 #  On Your Own


Background tilemaps can really make a level feel alive. To create one, just press the CreateTileMap button button in the {nav icon=pencil, name=TileEditor2D} tool's property grid.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109022.png)


It is often useful to organize your tilemaps by giving them descriptive names:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109026.png)


To make a tilemap into a proper background tilemap, just push it back a bit along the Z axis. You may also wish to alter some of the properties of the MultiSprite component to give it a moodier look:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109018.png)


Experiment with placing multiple layered tilemaps to help add visual flair to your levels.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109024.png)



 #  Related Materials


 ##  Tutorials


- [sprite_animations](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/graphics/sprite_animations.markdown)
- [the_market](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/external_zero_engine_tools/the_market.markdown)
- [swept_character](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/gameplay/swept_character.markdown)
- [tile_editor_ii](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/tutorials/editor/tile_editor_ii.markdown)


 ##  Manual


- [commands](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [spriteimporter](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/sprites/spriteimporter.markdown)
- [spritesourceeditor](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/sprites/spritesourceeditor.markdown)
- [resourceadding](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown)
- [archetype_basics](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/archetypes/archetype_basics.markdown)


 ##  Reference


 ###  Commands


- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#stopgame)
- [ CreateTransform](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#createtransform)
- [ Delete](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#delete)


 ###  Classes


- [multisprite](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/multisprite.markdown)
- [physicsmesh](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/physicsmesh.markdown)


 ###  Events


- [ CollisionStarted](https://github.com/zeroengineteam/ZeroDocs/code_reference/event_reference.markdown#collisionstarted)


 ##  Development Task


- T2174
 

 