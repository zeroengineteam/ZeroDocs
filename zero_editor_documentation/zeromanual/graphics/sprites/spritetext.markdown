(NOTE)**Recommended Reading**  This section covers topics that may not have been addressed yet. To learn or review those topics, please see: [Base Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/basesprite.markdown)

[spritetext](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/spritetext.markdown) is a useful component for quickly adding text into a project that allows the user to easily modify the properties of the text, such as the [font](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/resources/font.markdown), size, and runtime output. As with [sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/sprite.markdown), SpriteText can be added to any existing [Game Object](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/cogs/gameobjectsconcept.markdown). 

 # Common Uses
 - Scores, timers, and other HUD texts
 - Title, menu and button text

 # Using SpriteText
 ## Creating SpriteText
SpriteText can be made in different two ways: using the [Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : CreateSpriteText  or adding the `SpriteText` Component to any existing Game Object. The actual font is defined by the Font resource property, and all other properties control how the font is displayed:  The only differences in the objects are the values of a few properties:



![SpriteTextProperties](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47818.png) *SpriteText Component*


 ## Adding new Fonts
Importing and accessing different Font resource resources is arguably the most important thing to understand regarding SpriteText. Luckily, Zero Engine makes this very simple, allowing the user to drag and drop the [font](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/resources/font.markdown) into the Editor window. Alternatively, the user can use either [Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : Add  or click on the Add button button and select `Font  > IMPORT FONT`:



![AddButton](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47820.png) *Resource Add Button*




![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/45994.png) *Adding a Font*


This will open a new file explorer window where the user may select the Font or Fonts to import. Once a Font is imported into Zero, simply select the Font resource property on the SpriteText component and choose the desired Font.



![ChangeFonts](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47827.gif) *Selecting Multiple Fonts*


NOTE: Zero accepts both OpenType Font (OTF) and TrueType Font (TTF).


 ## Changing the Text
Typing the desired text into the Text  property and changing the FontSize  will adjust the text on screen, but that's also a bare minimum of what SpriteText is able to do. For example, by adjusting the PixelsPerUnit  property, it becomes possible to create different sized Fonts without losing any visual clarity.

 # Related Materials
 ## Manual Pages
- [BaseSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/basesprite.markdown)
- [TextBlock](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/architecture/resources/textblock.markdown)

 ## Reference Pages
- [SpriteText](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/spritetext.markdown)
- [Font](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/font.markdown)
- [Camera](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/camera.markdown)
- [Event](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/event.markdown) 

 