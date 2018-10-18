[SpriteSource](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/spritesource.markdown) is the Resource used to create [Sprites](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/sprite.markdown), which represent all 2D graphical assets in Zero.  Sprites can take the form of a single 2D image or a SpriteSheet displaying all the Sprites needed for an animation in the same file. See [resourceadding](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/resourceadding.markdown) for how to import an image as a SpriteSource.

NOTE: The only file format that may be imported to create a SpriteSource is `.png`. Other formats, such as `.jpg`, are lossy and can result in undesirable artifacts, especially when scaled. If the image only exists as a `.jpg` and it is absolutely necessary, there are a number of websites that offer free conversion from `.jpg` (and many other formats) to `.png`.

 #  SpriteSource Setup
To change the values applied to a SpriteSource when an image is imported, double-click the appropriate SpriteSource from the Library window window, which will open the [Sprite Source Editor](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/spritesourceeditor.markdown):



![SpriteSourceEditor](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47311.png) *Sprite Source Editor window*


There are many different properties that may be modified such as where to set the origin, the type of sampling, and the SpriteFill mode (to change from Fill to [Nine Slice](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/area.markdown) for example). If the SpriteSource is a sprite sheet created for [ Sprite animation](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/spritesourceeditor.markdown#creating-sprite-animatio), click on `Convert to Animation` to open the Sprite Importer window.

 # Related Material

 ## Manual
 [BaseSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/basesprite.markdown)
 [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/sprite.markdown)
 [Sprite Source Editor](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/sprites/spritesourceeditor.markdown)
 [Block Compression](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/adding_assets/block_compression.markdown)

 ## Reference
 [SpriteSource](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/SpriteSource.markdown) 
 [Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/code_reference/class_reference/Sprite.markdown)  

 