[ Textures  ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/texture.markdown) are a special type of image used to render 3D graphics. It's commonly mapped to [ meshes ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/models/mesh.markdown), [ particles ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/graphics/particles.markdown) and surfaces and it controls different aspects of rendering through colors, normals and masks and more.

Textures are not a final picture of the object; they are inputs that, when combined with lighting and other visual effects, produce a variety of graphical results. One of the most important aspects of textures is the ability to be drawn at different sizes efficiently. This is accomplished through [Mipmapping ](http://en.wikipedia.org/wiki/Mipmap) and anisotropic filtering.

For information on importing textures, see [adding_textures_and_sprites](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/adding_assets/adding_textures_and_sprites.markdown).

NOTE: Zero only supports images up to 4096 x 4096 pixels. If a larger image is imported, Zero will clamp it down to its maximum size.

 - Due to Mipmapping and compression, it is highly recommended to use images with powers of 2 proportions. They DO NOT need to be squares, however.
 - Zero supports the following image types:
  - **PNGs:** Lossless and compressed. We highly recommend that you use it. 
  - **TGAs:** Lossless and compressed.
  - **TIFs:** Lossless and compressed.
  - **PSDs:** Lossless but large in file size.
  - **JPGs:** Lossy. We do not recommend using it for final assets.

 # Texture Builder
The Texture Builder is a collection of settings used to convert your image file into a texture that's suitable for the game. They can be accessed by clicking on the texture in the Library Window.

 ## Texture Types

 - **Texture 2D:** Standard 2D texture.
 - **TextureCube:** A cubemap consisting of six faces used for a SkyBox and Reflection. Images will be read as a series of faces as illustrated by the image below.




![cubemap](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1145.png)


 ## Compression

By default, Zero performs an operation called [block_compression](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/adding_assets/block_compression.markdown) on all textures. While this can reduce image quality it greatly reduces memory usage allowing it to be rendered faster. This setting should not be disable unless color accuracy is extremely important. For more information on this topic we recommend [this article ](http://www.reedbeta.com/blog/2012/02/12/understanding-bcn-texture-compression-formats/).

---

 # Related Materials
 ## Manual
- [adding_textures_and_sprites](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/adding_assets/adding_textures_and_sprites.markdown)
- [mesh](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/models/mesh.markdown)
- [particles](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/graphics/particles.markdown)
 ## Code Reference
- [texture](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/texture.markdown)  

 