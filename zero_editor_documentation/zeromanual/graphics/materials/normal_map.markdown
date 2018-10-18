Normal maps give texture to objects.  The idea of normal maps isn't to necessarily deform the model (though that is certainly possible), but to change the way that light interacts with the model`s surface.  Normal maps represent minor deformities on a surface, such as the notches on a wooden plank.  The three colors that store the values in a normal map are red, green, and blue.  Each color is interpreted as X, Y, and Z respectively, to makeup a vector.  These vectors represent the direction that is normal to the surface, hence the name NormalMap.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/46703.png) *Normal map for decals*


Most of the color on a normal map ends up blue because most of the direction vectors on a normal map are in the Z direction.  In the space of the normal map, otherwise known as tangent space, X and Y point in the U and V directions of the texture, while Z points away from the texture.  Z can also be thought of as the direction away from the surface, and so the more blue a pixel is, the more outward a normal will be.  It then follows that redder pixels represent horizontal normals, and greener pixels represent vertical normals, which would both be tangent to the surface.

NOTE: If the normal map seems like a mix of green and yellow, it's probably because the textures been compressed with `BC5`.  For more on block compression, visit [Block Compression](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/adding_assets/block_compression.markdown).

 # NormalMap Material Block
The NormalMap resource material block contains a few additional properties vs other mapping material blocks.  RedLeft checkBox and GreenDown checkBox can be used to reorient the normal map to the desired direction.  In addition, Bumpiness checkBox will change the amount a normal map will effect a surface.

 ## Related Materials
 ### Manual
- [Block Compression](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/graphics/adding_assets/block_compression.markdown) 

 