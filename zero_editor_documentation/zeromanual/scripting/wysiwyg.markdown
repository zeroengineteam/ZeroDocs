Properties are one of the easiest ways to make components more reusable. While some properties affect runtime behavior, others are simply items that help set the initial state of one’s components.

One can see the WYSIWYG (what-you-see-is-what-you-get) effect with some of the built-in components.

Here the [ Sprite ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/sprites.markdown)'s orientation is changed the moment the FlipX checkBox box is checked in the editor. 



![flipped](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47657.gif)


As a demonstration, the following custom [ ZilchScript ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown) will emulateFlipX checkBox while using a Property:

```
class Flipper : ZilchComponent
{
  [Dependency] // Need the Transform component to perform the flip
  var Transform : Transform;
  
  [Dependency]
  var Orientation : Orientation;
  
  [Serialized] // This is the backing field that saves the value.
  var FlipXs : Boolean = false;
  
  [Editable]   // This is displayed in the Properties Window, but doesn't save
  var FlipX : Boolean = false;
  
  function Initialize(init : CogInitializer)
  {
    // If they chose to Flip, do so now
    if(this.FlipX)
      this.Flip();
  }
  
  function Flip()
  {
    this.Transform.RotateWorld(Math.AxisAngle(this.Orientation.WorldUp, Math.Pi));
  }
}
```




![propertyset](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/1265.png)


While this works, it doesn't flip when FlipX checkBox is altered at runtime. By only 
calling `Flip()` during initialization, it runs once and then never again. Although other scripts can access and call `Flip()` themselves, this function doesn't update FlipX checkBox, which means it doesn't represent the state of the object, like it does in the  Sprite component. 

To link the call of flip with the setting of the variable, we'll use a [Get-Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/properties.markdown) for editing and a field for the backing variable. i.e.

Update `Flipper.z` to the following:
```
[RunInEditor]
class Flipper : ZilchComponent
{
  [Dependency] // Need the Transform component to perform the flip
  var Transform : Transform;
  
  [Dependency]
  var Orientation : Orientation;
  
  [Serialized] // This is the backing field that saves the value.
  var FlipXs : Boolean = false;
  
  [Editable]   // This is displayed in the Properties Window, but doesn't save
  var FlipX : Boolean
  {
    get { return this.FlipXs; }
    set
    {
      // Using a get-set allows us to add functionality when the value is set;
      // in this case, performing the flip when the value is changed. 
      if (this.FlipXs != value)
      {
        this.Flip();
        this.FlipXs = value;
      }
    }
  }
  
  function Initialize(init : CogInitializer)
  {
    // If they chose to Flip, do so now
    if(this.FlipX)
      this.Flip();
  }
  
  function Flip()
  {
    this.Transform.RotateWorld(Math.AxisAngle(this.Orientation.WorldUp, Math.Pi));
  }
}
```





![flippereditorruntime](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47671.gif)


Employing [ RunInEditor ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown), [ Serialized ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown), and [ Editable ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown) we've created the WYSIWYG feel, and the sprite can now be flipped at editor runtime. This design pattern can be reused to create the polished WYSIWYG feel with most scripted components.

---
 # Related Materials
 ## Manual
 [ ZilchScript ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero.markdown)
- [ Sprites ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/graphics/sprites.markdown)
- [RunInEditor](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown)
- [Get-Set](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/properties.markdown)
- [ RunInEditor ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown)
- [ Serialized ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown)
- [ Editable ](https://github.com/ArendDanielek/ZeroDocsTest/blob/master/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown) 
  
  
  
  
  
  
  

 