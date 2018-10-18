![Texture_ChangingBlockCompression](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46149.gif) [Block Compression](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#texturecompression) is a technique used on [Textures](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/adding_assets/adding_textures_and_sprites.markdown) in Zero Engine to greatly reduce texture size.  Compression takes advantage of common patterns found in an image to make assumptions, resulting in less explicit data storage.  When these assumptions are false, artifacts will appear on the image.  Whether or not the loss in quality is worth the size saved is up to the discretion of the user.  By selecting the different block compression types in the Properties window window of a `Texture`, one can see the size difference and the resultant image.  Simply select a block compression method from `BC1` to `BC6` (or `NONE`) from the Compression drop-down menu dropdown and hit the `Reload Content` button.  The table below can be used to choose the best compression technique for an image.  For more information, visit [this page](https://msdn.microsoft.com/en-us/library/windows/desktop/bb694531(v=vs.85).aspx) on the Microsoft MSDN website.

| Compression | Bytes Per Pixel | Color Format | Notes |
| -- | -- | -- | -- |
| `BC1` | `1/2` | RGB | no alpha |
| `BC2` | `1` | RGBa | low precision alpha |
| `BC3` | `1` | RGBa | has alpha |
| `BC4` | `1/2` | R | single channel |
| `BC5` | `1` | RG | two channels |
| `BC6` | `1` | RGB floats | for hdr images |

(NOTE)**Compressions with the same BPP:** When two or more compression types have the same bytes per pixel, one should choose the compression with the best fitting color format.  For example, `BC4` and `BC1` have the same bpp.  If the texture in question has RGB color, `BC1` should be used since the color format is RGB.  If the texture has only one color, such as a height map, then `BC4` should be preferred.  By choosing the best fitting compression type for the height map, precision is almost guaranteed to be better on that texture.

 # Related Material

 ## Manual
- [Adding Textures and Sprites](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/adding_assets/adding_textures_and_sprites.markdown)

 ## Code Reference
- [BlockCompression](https://github.com/zeroengineteam/ZeroDocs/code_reference/enum_reference.markdown#texturecompression)
 

 