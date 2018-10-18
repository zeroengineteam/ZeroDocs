This lesson covers the basics of Zero Engine's Tile Editor tool. The [ next lesson](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/editor/tile_editor_ii.markdown) covers some of its more advanced features.


 #  Learning Objectives


- Tile sheet importing
- The Tile Editor's features


 #  Level Setup


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=Empty 2D Project} template

The Tile Editor tool allows a designer to quickly make a 2D level by painting a tilemap with tiles that consist of graphics, colliders, custom logic, and more.


 #  Importing Tile Sprites


The Tile Editor tool is typically (though not exclusively) used with sprites prepared with the [ Sprite Importer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/spriteimporter.markdown).

- Download the following tile sheet:
  ![PlatformerTiles](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/107599.png)
- `Drag and drop` the file into the `Level Window`
- In the `Group Import Options Window`
 - Set ImportImages enum to `Sprites`
 - Press the `Import All` button

Like in the [ tutorial on sprite animations](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/graphics/sprite_animations.markdown), we will use the Sprite Importer to take this large tile sheet and extract smaller SpriteSource resource resources from it.

- In the `Library Window`
 - Under the SpriteSource  tag
  - Double-click  `PlatformerTiles`
    ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/107617.png)
- In the `Sprite Source Editor Window`
 - Press the `Convert To Animation` button

The tile sheet consists of 32-pixel square tiles.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/107673.png)


*Each tile is 32 pixels wide and high*


To divide the tiles properly, we should set the FrameWidth  and FrameHeight  each to `32`. This will split the sheet into equally sized tiles, each of which is 32 pixels wide and high.

- In the `Sprite Importer Window`
 - Set Name  to `Tiles`
 - Set FrameWidth  to `32`
 - Set FrameHeight  to `32`
 - Set PixelsPerUnit  to `32`

Our goal here is to select every square region of the sheet that we want to use as a tile for the Tile Editor. By default, the ImportFrames enum property is set to [ AllFrames](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#importframes), so if we just clicked the `Add Frames as Sprites` button, it would add every 32-pixel tile in the sheet as a separate SpriteSource, and we'd be done. However, the sheet has some "holes" in it and a lot of empty space at the bottom, which would result in many tiles that are totally blank. These virtually useless SpriteSources would clutter up our library and act as a general nuisance. Instead, we can use the mouse to manually select all and only the tiles we want.

- In the `Sprite Importer Window`
 - Set ImportFrames enum to `SelectedFrames`
 - Left-click  every tile that you want to add
 - If you accidentally select a tile you don't want, right-click  it to deselect it



![Adding Grass Tile Frames](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109080.gif)


*The left mouse button selects tiles, and the right mouse button deselects them*


When you've got all the tiles you want, it's time to import them. Since we want each of these tiles to be a separate individual SpriteSource in the project, the `Add Frames as Sprites` button is the way to go.

- In the `Sprite Importer Window`
 - Press the `Add Frames as Sprites` button

The four lava surface tiles are designed as an animation strip, so we can import them together as a single animated SpriteSource.

- In the `Sprite Importer Window`
 - Press the `Clear Frames` button
 - Feel free to set FrameRate  to any desired value
 - Select the four lava surface tiles in order from left to right
 - Press the `Add and Close` button

(NOTE) **FrameRate:** The FrameRate  property defines the number of animation frames per second for an animated sprite source. (In other words, 1 divided by FrameRate  equals the delay in seconds for each frame.) The lava animation with a FrameRate  of `12` looks like this: ![Animated Lava Surface at 83 ms Delay](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109076.gif) ; the same animation with a FrameRate  of 4 looks like this: ![Animated Lava Surface at 250 ms Delay](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108754.gif) .



![Adding Lava Surface](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/109083.gif)


Now that we have all the sprites we want, we're ready to start using the Tile Editor.


 #  The TileEditor2D Tool


The TileEditor2D tool is used to create and modify a **tile map** object, which consists of sprites, collision information, and archetype definitions. This can be used to create 2D levels in a game.

- In the `Tool Bar`
  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108716.png)
 - Press the ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/107930.png) {nav icon=square-o, name=TileEditor2D} button

(NOTE) **Tool Control Info:** For quick reminders about the controls of the TileEditor2D tool, just hover  over the ![Circled Info Icon](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108711.png) icon in the upper-left corner of the `Tools Window`.

Selecting the TileEditor2D tool for the first time will show this:



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/107932.png)


*The TileEditor2D tool requires a tilemap object to work*


- In the `Level Window`
 - Click  the **No TileMap Object** message
   ![Adding a TileMap Object](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/107934.gif)

(NOTE) **TileMap Objects:** The TileEditor2D tool needs a tilemap object to work with. If there isn't one in the level, then you'll need to make one before you use it. Of course, you can have multiple tilemaps in the same level (say, for backgrounds and foregrounds). When you select the TileEditor2D tool, if no tilemap object is already selected, it will automatically select the one that was most recently edited.


 ##  Placing Tiles


Tiles can be added to the tilemap by using the TileEditor2D tool's **Draw sub-tool** and **Selection sub-tool**.


 ###  The Draw Sub-Tool


The Draw sub-tool allows you to paint tiles into a tilemap. All of your project's SpriteSources can be found in the list under the Sprite enum property.

- In the `Tools Window`
 - Set Sprite enum to the SpriteSource of your choice
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108232.png)
- In the `Level Window`
 - `Left-click and drag` to **place tiles**
   ![First Steps - Drawing](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108230.gif)
 - `Right-click and drag` to **erase tiles**
   ![First Steps - Erasing](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108234.gif)


 ###  The Selection Sub-Tool


The Selection sub-tool allows you to select one or more tiles to use as a "brush", which can then be used to paint using the Draw sub-tool.

- In the `Tools Window`
 - Set ToolType enum to [ SelectionTool](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#tileeditor2dsubtooltype)
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108285.png)

(NOTE) **TileEditor2D Tool Hotkeys:** You can quickly select the TileEditor2D tool by pressing key the `6` key. With the TileEditor2D tool active, you can select the Draw sub-tool and the Selection sub-tool by pressing key `Shift + 1` and `Shift + 2`, respectively.

- In the `Level Window`
 - `Left-click and drag` to **select tiles**
 - After making a selection, right-click  the selected tiles to **commit the selection** to be used as a brush
 - If you don't want to use the selected tiles as a brush, right-click  somewhere else in the `Level Window` to **clear the selection**
   ![First Steps - Selecting](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108316.gif)

After committing a selection with the Selection sub-tool, the Draw sub-tool is automatically selected, and you can draw and erase with the new brush.

- In the `Tools Window`
 - Confirm that the ToolType enum property is set to [ SelectionTool](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#tileeditor2dsubtooltype)
- In the `Level Window`
 - `Left-click and drag` to make a selection and right-click  it to commit it as a brush
 - `Left-click and drag` to **place tiles with the new brush**
 - `Right-click and drag` to **erase tiles with the new brush**
   ![First Steps - Brush Painting](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108320.gif)
 - Press key the `Esc` (Escape) key to **revert the brush** to the tile specified in the `Tools Window`


 ##  A Quick Test Run


Let's use what we've covered so far to throw together a very basic level (but really not much more than a couple of platforms) that we can play in using the swept character archetype that can be downloaded from the Zero Market, as covered in [ tutorial on the Zero Market](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/external_zero_engine_tools/the_market.markdown).

- Use the TileEditor2D tool to create a set of simple platforms:
  ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108816.png)
- Press the ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108714.png) Market button button in the top-right corner of the editor
- Click  the `Sample Character Controller` package
- Click  the download link for the `SAMPLECHARACTERCONTROLLERS[1.0].ZEROPACK` package
- In the `Import Content Package Window`
 - Press the Import button button
- Close the `Market Browser`
- In the `Library Window`
 - Under Archetype 
  - `Left-click and drag` `SweptPlayer2D` into the `Level Window`
    ![Adding a Swept Character](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108718.gif)
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)



![This Swept Character Cannot Jump High Enough](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/108720.gif)


*By default, the tiles placed with the TileEditor2D tool have collision*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

(NOTE) **Can't Jump High Enough?** Depending on how you constructed your level, you may want to adjust your player character's properties, such as the `SweptController`'s Gravity  and JumpSpeed .

The test run was a success: the swept character collides with the tiles as expected. In the [ next tutorial](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/editor/tile_editor_ii.markdown), we'll begin by learning about tile archetypes.


 #  Related Materials


 ##  Tutorials


- [sprite_animations](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/graphics/sprite_animations.markdown)
- [the_market](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/external_zero_engine_tools/the_market.markdown)
- [swept_character](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/gameplay/swept_character.markdown)
- [tile_editor_ii](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/editor/tile_editor_ii.markdown)


 ##  Manual


- [commands](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [spriteimporter](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/spriteimporter.markdown)
- [spritesourceeditor](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/spritesourceeditor.markdown)


 ##  Reference


 ###  Commands


- [ NewProject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)


 ###  Enums


- [ ImportFrames](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#importframes)
- [ TileEditor2DSubToolType](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/enum_reference.markdown#tileeditor2dsubtooltype)


 ##  Development Task


- T2174
 

 