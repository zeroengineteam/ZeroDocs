Direct lighting comes from any lights that are created and setup by the user. This includes directional and point lights. While there may appear to be some surface-level similarities between the two, they make use of certain components and are implemented entirely differently.

Please note that when using a [forward renderer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/renderer.markdown), the only direct lighting allowed is the DirectionalLight that is present by default in any new level. DirectionalLight cogPath on the ForwardRenderer component should be set to this DirectionalLight. If dynamic lighting is needed on a project that uses a forward renderer, it must implemented by the user. There is no single implementation for dynamic lighting with a forward renderer that may be applied as there with a [deferred renderer](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/renderer.markdown), so any particular implementation must be based off the particular requirements of a project.

 # [Directional Light](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/lighting/direct_lighting/directional_light.markdown)
A light that is applied over an entire scene, emitting light from a specific direction.

 # [Point Light](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/graphics/lighting/direct_lighting/point_light.markdown)
A light that has a defined shape, exists at particular point in space, and sends light out equally from all points on that shape. 

 