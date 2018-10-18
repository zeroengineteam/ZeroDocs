While Zero provides a number of pre-defined Eases (e.g., `QuadIn`, `QuadOut`, `SinIn`, `SinOut`), these may not cover all situations that may arise. In those cases, a custom ease may be created by adding a [samplecurve](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/resources/samplecurve.markdown).

 # A Closer Look at Easing Functions
Eases are used primarily in what is called "tweening", short for *in-betweening* (and [Actions](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/action.markdown) are Zero Engine's form of tweening). Tweening is a procedure for interpolation between two values that can provide animation through the use of mathematical functions without the user having to adjust any frames. Eases are functions that control the rate of acceleration of the change in value. Usually, eases are used to make animations look more natural or "life-like", though the most basic of eases--`Linear`--is decidedly sterile-looking or robotic, as can be seen in this example of a simple moving platform:



![LinearPlatform](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/2083.gif)


The platform moves side to side at a steady, constant rate of motion. In other words, its rate of movement is linear. For the sake of comparison, let's look at another, nicer-looking, more "life-like" ease; specifically, the `QuadInOut` ease (which uses the quadratic function to derive acceleration):



![QuadInOutPlatform](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/2088.gif)


In this case, the acceleration changes throughout the movement from left to right (and vice versa). It start slow, builds up speed, then slows back down once it nears the end. This type of movement is common in everyday life. For example, elevators use a non-linear movement. Imagine if a high-speed elevator in a high-rise building did not change its acceleration, and the elevator comes to a complete stop while at the relatively high speed it moves at as it passes floors: every one in it would go flying to the ceiling. Instead, as the elevator approaches its destination, it slows down so that it comes to a smooth, non-person-launching stop.

 # Standard Easing Classes
There are five "standard" (and consequently, the most popular) easing types: Linear, Quadratic, Cubic, Quartic, and Quintic. These names refer to the power by which a part of the ease equation is raised. Linear has an exponent of 1, Quadratic is rasied to the 2nd power, and so on. Whether the ease is In, Out, or InOut depends on whether the animation desired starts slow and then speeds up at the end (EaseIn), starts fast and then slows down at the end (EaseOut), or starts out slow, speeds up, but then slows back down at the end (EaseInOut). When the exponent is increased, the essential part of the ease equation (the representing current percentage of completion of the tween) is multiplied by itself. For example, if there was an EaseOut that is moving to 70% of the desired value change, 0.7 would be multiplied with the exponent of the ease. For Quadratic, the exponent is two, so the result would be: 0.7 * 0.7 = .49, instead of 0.7. This means the value would move to 70% of the desired value in 49% of the time it would take linearly, moving quicker at the start and slower at the end. To make this relationship explicit, here's the function usually used for determining ease (though this one will just be a linear tween without any proper easing applied).

```lang=csharp
function LinearTween(beginningVal, changeToVal, currentTime, totalTime)
{
    return changeToVal * currentTime / totalTime + beginningVal;
}
```

Here's what each argument of the function stands for:

 - `beginningVal` is the beginning value of the property that is being animated
 - `changeToVal` is the change between the beginning value and the end value of the property that is being animated
 - `currentTime` is the start time of the tween and can be described using any unit (e.g. frames, seconds, etc...) as long as the unit stays the same for `totalTime` as well.
 - `totalTime` is the total amount of time the tween will take

One thing to note is that the `currentTime / totalTime` portion of the equation represents the percentage of completion for the tween (if 5 seconds of a 10 second duration has elapsed, it is 50% of the way through). To see this in action, let's look at a simple example. At the start of a level, a platform at position `Real3(0,5,0)` should move up the y-axis to `Real3(0,15,0)` over the course of 2 seconds.

 - `beginningVal` would be 5 (this is the y-value from `Real3(0,5,0)`)
 - `changeToVal` would be 10 (this is the differnce in the y-value from `Real3(0,5,0)` to `Real3(0,15,0)`)
 - `currentTime` would be 0 (seconds) as the tween should start when the level starts
 - `totalTime` is 2 as the tween should occur over 2 seconds
 - Using the equation provided above: 10 * 0 / 2 + 5 = 5, leaving the platform where it started.

The next case to consider is checking the value **during** the tween itself, say 50% of the way through. This would only change the `currentTime` value to 1 (2 * 0.5 = 1). Our equation now gives us:

`10 * 1 / 2 + 5 = 10`

10 is the exact midpoint on the y-axis between the start and end values of 5 and 15, which is exactly the value one would expect given that the equation was changed to provide the value at 50% of the way through the tween. With any change in the percentage of the completion of tween (the `currentTime/totalTime` portion of the equation), the result will be the value at that particular percentage of time elapsed.

The portion of this equation that will be affected by the exponent associated with the standard eases is `currentTime/totalTime`. One could even substitute 0 for `beginningVal` and 1 for `changeToVal` so that the result is a **factor**, which could then be multiplied by the difference between the values, while also adding back in the original value, to end up with the same thing as the original equation, like so:

```lang=csharp
function EasingFunction(beginningVal, changeToVal, currentTime, totalTime)
{
    return changeToVal * currentTime / totalTime + beginningVal;
}
function EaseIn(beginningVal, changeToVal, currentTime, totalTime)
{
    var easeFactor = this.EasingFunction(0, 1, currentTime, totalTime);
    this.Owner.PropertyToChange = (endValue - originalVal) * easeFactor + originalVal;
}
```
 ## Quadratic Ease Functions
The Quadratic ease function includes a new argument--the exponent by which to multiply the completion percentage:

```lang=csharp
function QuadEaseIn(0, 1, currentTime, totalTime, easePower)
{
    easePower = 2;
    return changeToVal * Math.Pow(currentTime / totalTime) + beginningVal;
}
```

This function can be reduced by removing the value parameters from the function altogether. Doing so will work nearly identically as the equation above in all the standard eases:

```lang=csharp
function QuadEaseIn(currentTime, totalTime, easePower)
{
    easePower = 2;
    return Math.Pow(currentTime/totalTime, easePower);
}
```

For an EaseOut function, which starts fast and then slows down, the same equation is used but is subtracted from 1 so that it comes at the end of the tween:

```lang=csharp
function QuadEaseOut(currentTime, totalTime, easePower)
{
    easePower = 2;
    return 1 - Math.Pow(1 - (currentTime/totalTime), easePower);
}
```

For the EaseInOut function, the previously omitted parameters will need to be incorporated back in:

```lang=csharp
function QuadEaseInOut(beginningVal, changeToVal, currentTime, totalTime, easePower)
{
    easePower = 2;
    if((currentTime /= totalTime / 2) < 1)
    {
        return changeToVal / 2 * Math.Pow(currentTime/totalTime, easePower) + beginningVal;
    }
    else
    {
        return -changeToVal / 2 *  (currentTime * (currentTime - 2) - 1) + beginningVal
    }
}
```

All of these eases can be visualized on a graph. In Zero, graphs like this may be plotted on a [SampleCurve](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/resources/samplecurve.markdown), allowing their use as the ease parameter in Actions.

 # Applying a Custom Ease

After creating a SampleCurve, it can be directly applied to an Action. The following ZilchScript illustrates how to apply a SampleCurve to an Action that translates an object back and forth.

```
class EasedMovement : ZilchComponent
{
  [Dependency] var Transform : Transform;
  
  [Property] var TargetPos : Real3;
  [Property] var Time : Real;
  [Property] var EaseToUse : SampleCurve;
  
  var Property : Real3;
  
  var StartPos : Real3;
  
  function Initialize(init : CogInitializer)
  {
    // Call the function to move the object
    this.Move();
  }
  
  function Move()
  {
    // Save starting position to move back to 
    this.StartPos = this.Transform.Translation;
    
    var seq = Action.Sequence(this.Owner.Actions);
    
    // Move the object 
    Action.Property(seq, @this.Transform.Translation, this.TargetPos, this.Time, this.EaseToUse);
    // Call the function that will move it back
    Action.Call(seq, this.MoveBack);
  }
  
  function MoveBack()
  {
    var seq  = Action.Sequence(this.Owner.Actions);
    
    // Move the object back
    Action.Property(seq, @this.Transform.Translation, this.StartPos, this.Time, this.EaseToUse);
    // Call the function to move the object
    Action.Call(seq, this.Move);
  }
}
```


 # Related Materials
 ## Manual
- [ResourceAdding](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/ZeroManual/Editor/EditorCommands/ResourceAdding.markdown)
- [samplecurve](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/architecture/resources/samplecurve.markdown)

 ## Code Reference
- [action](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/action.markdown) 

 