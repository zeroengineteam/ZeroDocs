
Randomness is an important part of most games, without randomness a game will be deterministic meaning the same outcome will always happen given the same set of player inputs.

 # Creating a Random Number Generator Object
There are two ways you can create a Random Number Generator Object in Zero Engine: 

- [randomcontext](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/randomcontext.markdown)
- [random](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/random.markdown) (only available through Zilch Scripts)

RandomContext is a component that can be added to an object while Random is a type (such as Real2 or Quaternion). While they both offer slightly different methods, they both can be used to accomplish the same goals and are often interchangeable.

 # RandomContext component
The RandomContext component can be added to a game object just like every other component.

 # Random class object
The Random class object can be created much like every other object in the game.

```
   class RandomScript : ZilchComponent
   {
     ...
       var RandomGenerator : Random = Random();
       ...
   }

```


or if you want to where exactly when the object is created

```
   function Initialize(init : CogInitializer)
   {
     ...
     this.RandomGenerator = Random();
     ...
   }

```


 # Using the Random Number Generator Object
Below are some examples on how to use the functions offered by the Random Number Generator object.
 ## DieRoll
DieRoll is a function that takes an integer that determines the number of sides of a die and returns a random number between `1` and `Sides`. Here's an example:

```
   function GenerateRandomNumber ()
   {
     Console.WriteLine(this.RandomGenerator.DieRoll(20));
   }

```


 ## Range
Real Range (Real Min, Real Max)
The Range function can be used when you need to generate a random number between two numbers.
We can call this function by

```
   function GenerateRandomRange ()
   {
     Console.WriteLine(this.RandomGenerator.Range(0, 100));
   }

```


 ## Linear vs Non-Linear
Up untill now we are only generating random numbers linearly. This means that all possible numbers in a specified range has an equal chance to be generated. There are functions that the generator offer that generates random numbers in a non-linear manner where all possible numbers in a specified range does not have an equal chance to be generated. Functions like BellCurve generate numbers in a non-linear manner so in a range of `0` to `1`, numbers in the middle of the range has a higher chance of being generated than the numbers on the edges.

 ## Deterministic Random Number Generator
In some situations, deterministic random number might be needed in order for a feature to work correctly. This can normally be found in a Replay feature or networked games. In a Replay feature, game sessions are recorded and replayed for people to see and evaluate. This means that we will have to record all randomness in the game as well. Or in a networked game where randomness are involved, we need to make sure that all the connected players are playing the same game which means we have to somehow make sure that random number generator generates the same number between the different players.

 ### Seeding a Random Number Generator
When we seed a random number generator, we make sure that the random number generator will generate the same sequence of number when it is called.

```
   function Initialize(init : CogInitializer)
   {
     ...
     this.RandomGenerator.Seed(0);
     ...
   }

```


When the following function is called multiple times, the same sequence of number will be generated every time.

```
   function GenerateRandomNumber ()
   {
     Console.WriteLine(this.RandomGenerator.DieRoll(20));
   }

```


So in a Replay feature, we simply save the current seed of the random number generator and then seed the random number generator with the seed to get the same sequence of random number every time we run the replay. Also, in a networked game, we can simply share the seed between all connected players to make sure that everyone shares the same gameplay experience between multiple random number generator.

 # Related Material
 ## Reference
- [randomcontext](https://github.com/zeroengineteam/ZeroDocs/code_reference/class_reference/randomcontext.markdown)
- [random](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/random.markdown) 

 