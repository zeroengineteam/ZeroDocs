[ String](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown) is a Zilch type used to represent text as a sequence of characters.

 #  Making Strings

In Zilch, a string literal is made by enclosing zero or more characters in double quotation marks:

```lang=csharp, name=String Literal Examples
var greeting = "hello world";
var colorCode = "#F9EF1A";
var empty = "";
```

 #  String Interpolation

*String interpolation* is a way of evaluating an expression and inserting it directly into a string literal. In Zilch, string interpolation is done using the **grave accent** character, ##`##. Anything in a string literal that is entered between two ##`##s is evaluated, and the result of that evaluation is used instead. For example:

```lang=csharp, name=String Interpolation Examples
var xp = Integer.PositiveMax;
var message = "Gained `xp` experience points.";
Console.WriteLine(message);

message = "Turn `Math.ToDegrees(Math.ACos(0.2)) - 15.0` degrees to starboard.";
Console.WriteLine(message);

message = "This component is attached to `this.Owner`.";
Console.WriteLine(message);
```
```name=Console Window
Gained 2147483647 experience points.
Turn 63.463 degrees to starboard.
This component is attached to <Cog 'LevelSettings' [425]>.
```

String interpolation presents a handy means of joining two strings:

```lang=csharp, name=String Interpolation Joining
var str0 = "GAME";
var str1 = "OVER";
Console.WriteLine("`str0` `str1`");
```
```name=Console Window
GAME OVER
```

It can also be used to effectively "append" to a string:

```lang=csharp, name=String Interpolation Appending
var evenDigits = "";
var oddDigits = "";

for (var i = 0; i < 10; ++i)
{
  if (i % 2 == 0)
    evenDigits = "`evenDigits` `i`";
  else
    oddDigits = "`oddDigits` `i`";
}

Console.WriteLine("Even base-ten digits: `evenDigits`");
Console.WriteLine("Odd base-ten digits: `oddDigits`");
```
```name=Console Window
Even base-ten digits:  0 2 4 6 8
Odd base-ten digits:  1 3 5 7 9
```

Note that strings in Zilch are **immutable**, which means they cannot be altered after they have been created. Thus, strictly speaking, no true *appending* takes place. In the above code block, where it appears that `evenDigits` is being appended via string interpolation, a new string is actually created using the previous value of `evenDigits` and the value of `i`, and that new string is assigned back to the `evenDigits` variable.

(NOTE) Since this means of string appending involves the creation of another new string each time it occurs, it is less efficient than using a [ StringBuilder](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/stringbuilder.markdown), which is intended for just this purpose. In certain situations, such as a deeply nested loop, this performance difference may be significant.

 #  Escape Sequences

Some characters are entered in a string literal via special sequences of characters called //escape sequences//. In Zilch, all escape sequences consist of a backslash followed by another character.

```lang=csharp, name=Escape Sequence Examples
// \" -- double quotation marks
Console.WriteLine("Say \"hello\" to Dr. Cosmo for me.");
Console.WriteLine();

// \` -- grave accent
Console.WriteLine("Press the \` key to open the console");
Console.WriteLine();

// \\ -- backslash
Console.WriteLine("C:\\Logs\\Analytics\\ForestLevel.Analytics.gamedata");
Console.WriteLine();

// \n or \r -- newline
Console.WriteLine("BEWARE\n  OF\r DOUG");
Console.WriteLine();

// \t -- horizontal tab
Console.WriteLine("+---+---+---+");
Console.WriteLine("1\t12\t123\t|");
Console.WriteLine("+---+---+---+");
```
```name=Console Window
Say "hello" to Dr. Cosmo for me.

Press the ` key to open the console

C:\Logs\Analytics\ForestLevel.Analytics.gamedata

BEWARE
  OF
 DOUG

+---+---+---+
1   12  123 |
+---+---+---+
```

 #  Strings and StringRanges

[ StringRange](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/stringrange.markdown) is a separate but related class to **String**. It is an iterable range that can be used in a [ For Each loop](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/looping.markdown#for-each-loop). A string can be **implicitly cast** to StringRange, so a string can be passed into any function that expects a StringRange. However, a StringRange *cannot* be implicitly cast to String:

```lang=csharp, name=String and StringRange Implicit Casting Examples
  var string = "";
  var stringRange = StringRange();
  
  this.FunctionTakingString(string);                  // okay
*this.FunctionTakingString(stringRange);             * error
  this.FunctionTakingString(stringRange.ToString());  // okay
  this.FunctionTakingStringRange(string);             // okay
  this.FunctionTakingStringRange(stringRange);        // okay
```

 #  Static String Functions

[ As with all static functions](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/attributes.markdown#static), the static functions of the String class are not invoked from instances of the class, but instead are found in the String namespace itself.

 ##  Compare

[ Compare](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#compare-zero-engine-docu) returns an Integer indicating the *relative sort order* of the two given strings; that is, whether one string would be sorted before another when comparing the character codes of the two strings:

```lang=csharp, name=Relative Sort Order Example
var str0 = "abc";
var str1 = "def";

Console.WriteLine(String.Compare(str0, str1));
Console.WriteLine(String.Compare(str1, str0));
Console.WriteLine(String.Compare(str0, str0));
```
```name=Console Window
-1
1
0
```

This results in more or less the same ordering as one would use to sort entries in an English dictionary, except that because it goes by character codes, uppercase letters are sorted before lowercase letters, etc.:

```lang=csharp, name=Letter Case Sorting Example
var str0 = "cat";
var str1 = "dog";
var str2 = "DOG";

Console.WriteLine(String.Compare(str0, str1));
Console.WriteLine(String.Compare(str0, str2));
```
```name=Console Window
-1
1
```

This method is handy for sorting arrays of strings. [ Sort](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/array_t.markdown#sort-void) is an [ Array](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/array_t.markdown) method that sorts an array in place using a given comparison function:

```lang=csharp, name=Compare Sort Example
var strings = Array[String]();

strings.Add("hi");
strings.Add("greetings");
strings.Add("nice to see you");
strings.Add("good morning");

Console.WriteLine(strings);

strings.Sort(String.Compare); // the Compare function is passed as a delegate

Console.WriteLine(strings);
```
```name=Console Window
{hi, greetings, nice to see you, good morning}
{good morning, greetings, hi, nice to see you}
```

 ##  Concatenate

[ Concatenate](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#concatenate-zero-engine) can be used to join two existing strings:

```lang=csharp, name=Concatenate Example
Console.WriteLine(String.Concatenate("exa", "mple"));
```
```name=Console Window
example
```

 ##  FormatC

[ FormatC](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#formatc-zero-engine-docu) produces a string using C-style string formatting syntax:

```lang=csharp, name=FormatC Example
var score = 12340;
Console.WriteLine(String.FormatC("Score: %08d", score));
var hull = 100.0 * 43.0 / 64.0; // actual value 67.1875
Console.WriteLine(String.FormatC("Hull integrity at %.2f percent", hull));
```
```name=Console Window
Score: 00012340
Hull integrity at 67.19 percent
```

**FormatC** uses the same syntax as [the C printf function](http://www.cplusplus.com/reference/cstdio/printf/ ), with the following notes:
- the `p` format specifier can only be used with references to objects of reference types
- the `n` format specifier cannot be used
- the `#` flag can only be used with the `o`, `x`, and `X` specifiers
- the `.` precision marker must have its precision value specified

 ##  FromRune

[ FromRune](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#fromrune-zero-engine-doc) returns a one-character string that consists of the given rune, which can either be passed in directly, or be specified by its code point:

```lang=csharp, name=FromRune Example
Console.WriteLine(String.FromRune(65));
Console.WriteLine(String.FromRune(Rune(90)));
```
```name=Console Window
A
Z
```

 ##  IsNullOrEmpty and IsNullOrWhitespace

[ IsNullOrEmpty](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#isnullorempty-zero-engin) returns true if the given string is either **null** or the empty string, `""`, and false otherwise. [ IsNullOrWhitespace](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#isnullorwhitespace-zero) works just the same way, except that it also returns true if the given string consists only of **whitespace** characters:

```lang=csharp, name=IsNullOrWhitespace Example
Console.WriteLine(String.IsNullOrWhitespace("  \n  \t  "));
```
```name=Console Window
true
```

 ##  Join

[ Join](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#join-zero-engine-documen) combines two, three, or four strings into one, placing a given separator string between them in the result:

```lang=csharp, name=Join Example
var word0 = "Eeny";
var word1 = "Meeny";
var word2 = "Miney";
var word3 = "Moe";
var separator = ", ";
Console.WriteLine(String.Join(separator, word0, word1, word2, word3));
```
```name=Console Window
Eeny, Meeny, Miney, Moe
```

 #  String Properties

 ##  All

[ All](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#all-zero-engine-document) converts the string into a StringRange. In Zilch, strings can be implicitly cast to StringRanges, so it is typically not necessary to use this property:

```lang=csharp, name=All Example
// Contains takes a StringRange
Console.WriteLine("homeowner".Contains("meow"));
Console.WriteLine("homeowner".Contains("meow".All));
```
```name=Console Window
true
true
```

 ##  Begin and End

[ Begin](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#begin-zero-engine-docume) gets the RuneIterator at the start of the string, and [ End](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#end-zero-engine-document) gets the RuneIterator at the end of it:

```lang=csharp, name=Begin and End Example
var fileName = "SnowLevel.Analytics.gamedata";
var levelName = fileName.SubString(fileName.Begin, fileName.FindFirstOf(".").Begin);
var extension = fileName.SubString(fileName.FindLastOf(".").End, fileName.End);
Console.WriteLine(levelName);
Console.WriteLine(extension);
```
```name=ConsoleWindow
SnowLevel
gamedata
```

 ##  ByteCount and Count

[ ByteCount](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#bytecount-zero-engine-do) gets the number of bytes in the string. For a string that contains one or more characters outside of the ASCII range, this will be different from the number of runes represented by the string (see [ComputeRuneCount](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/strings/.markdown#computerunecount) below). Consider the following code example, attached to a cog that has a SpriteText component whose Text property is set to the French word //garçon//:

```lang=csharp, name=ByteCount Example
var englishString = "string";
var frenchString = this.Owner.SpriteText.Text;

Console.WriteLine("The English string has `englishString.ByteCount` bytes");
Console.WriteLine("The French string has `frenchString.ByteCount` bytes");
```
```name=Console Window
The English string has 6 bytes
The French string has 7 bytes
```

The [ Count](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#count-zero-engine-docume) property gets the same value as **ByteCount**, and exists for legacy purposes.

 ##  Empty and IsNotEmpty

[ Empty](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#empty-zero-engine-docume) gets whether the string contains any characters at all:

```lang=csharp, name=Empty Example
var userNameInput = "";

if (userNameInput.Empty)
  Console.WriteLine("Please enter a name.");
else
  Console.WriteLine("Welcome, `userNameInput`.");
```
```name=Console Window
Please enter a name.
```

[ IsNotEmpty](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#isnotempty-zero-engine-d) is always the exact opposite of **Empty**.

 #  String Methods

String methods are found on string instances, including literals:

```lang=csharp, name=String Method on Literal Example
Console.WriteLine("hello world".ToUpper());
```
```name=Console Window
HELLO WORLD
```

 ##  CompareTo

A string's [ CompareTo](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#compareto-zero-engine-do) method returns an Integer indicating its relative sort order when compared with a given StringRange. It works much like the static [Compare](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/strings/.markdown#compare) function seen above, except that it compares a given StringRange to the string on which this method is being invoked.

 ##  ComputeRuneCount

The [ ComputeRuneCount](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#computerunecount-zero-en) method calculates the number of runes represented by the string by iterating through it from its [Begin iterator to its End](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/strings/.markdown#begin-and-end). As noted [above](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/strings/.markdown#bytecount-and-count), a string that contains one or more characters outside of the ASCII range will have a different rune count from its byte count:

```lang=csharp, name=ComputeRuneCount Example
var englishString = "string";
var frenchString = this.Owner.SpriteText.Text;

Console.WriteLine("The English string has `englishString.ComputeRuneCount()` runes");
Console.WriteLine("The French string has `frenchString.ComputeRuneCount()` runes");
```
```name=Console Window
The English string has 6 runes
The French string has 6 runes
```

 ##  Contains

The [ Contains](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#contains-zero-engine-doc) method checks whether a string contains a given substring:

```lang=csharp, name=Contains Example
var sentence = "DR. COSMO: \"I'm looking for a person named Brianna.\"";
var name0 = "Brian";
var name1 = "Anna";

Console.WriteLine(sentence);

if (sentence.Contains(name0))
  Console.WriteLine("* BRIAN: \"Did someone mention me?\"");
if (sentence.Contains(name1))
  Console.WriteLine("* ANNA: \"My ears are burning.\"");
```
```name=Console Window
DR. COSMO: "I'm looking for a person named Brianna."
* BRIAN: "Did someone mention me?"
```

As this example shows, **Contains** is case-sensitive, but it does *not* match only complete words. `Brianna` contains `Brian`, and it does contain `anna`, but not `Anna`.

 ##  EndsWith and StartsWith

The [ EndsWith](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#endswith-zero-engine-doc) method checks whether a string ends with a given substring:

```lang=csharp, name=EndsWith Example
var fileNameToOpen = "DesertLevel.Analytics.gamedata";

var validFileExtension = ".gamedata";

if (fileNameToOpen.EndsWith(validFileExtension))
  Console.WriteLine("Opening `fileNameToOpen`....");
else
  Console.WriteLine("`fileNameToOpen` is not a valid file");
```
```name=ConsoleWindow
Opening DesertLevel.Analytics.gamedata....
```

The [ StartsWith](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#startswith-zero-engine-d) method works the same way, except that it checks the beginning of the string instead the end.

 ##  Replace

The [ Replace](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#replace-zero-engine-docu) method returns a new string, with all occurrences of a given old substring replaced with a given new substring:

```lang=csharp, name=Replace Example
var dialogueFromFile = "Oh, [HERO_NAME]! Your friend [VILLAIN_NAME] was looking for you.";

var heroName = "Brianna";
var villainName = "Dr. Cosmo";

var dialogue = dialogueFromFile.Replace("[HERO_NAME]", heroName);
dialogue = dialogue.Replace("[VILLAIN_NAME]", villainName);

Console.WriteLine(dialogue);
```
```name=Console Window
Oh, Brianna! Your friend Dr. Cosmo was looking for you.
```

 ##  Split

The [ Split](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#split-zero-engine-docume) method scans a string for a given delimiter StringRange of one or more characters. The substrings that were found separated by occurrences of that delimiter, if any, are returned as an iterable range. The delimiter itself is not present in the split results:

```lang=csharp, name=Split Example
var dataFromFile = "0,0,2,0,5,4,1,1,0,0,0,1,1,3,5,1";
var splitResults = dataFromFile.Split(",");

// splitResults now contains "0", "0", "2", "0", "5", "4", and so on

var total = 0;

foreach (var result in splitResults)
  total += Integer.Parse(result);

Console.WriteLine("Data Total: `total`");
```
```name=Console Window
Data Total: 24
```

NOTE: [ Parse](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown#parse-zero-engine-docume) is a static [ Integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown) function. It takes a StringRange and interprets it as if it were an Integer, and returns that value. Equivalent static functions exist in other classes, such as [ Real](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/real.markdown), [ DoubleInteger](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/doubleinteger.markdown), etc.

 ##  SubString, SubStringBytes, and SubStringFromRuneIndices

The [ SubString](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#substring-zero-engine-do) method returns the snippet of a string that is bounded by the two given RuneIterators. This may be the entire string itself, or it may be a smaller portion thereof:

```lang=csharp, name=SubString Example
var name = "The Evil Dr. Cosmo";

var firstSpace = name.FindFirstOf(" ");
// firstSpace refers to the space directly after "The"
var title = name.FindFirstOf("Dr.");
// title refers to the "Dr." between "Evil" and "Cosmo"
var lastSpace = name.FindLastOf(" ");
// lastSpace refers to the space directly before "Cosmo"

var part0 = name.SubString(name.Begin, firstSpace.Begin); // "The"
var part1 = "Handsome but Misunderstood";
var part2 = name.SubString(title.Begin, title.End);       // "Dr."
var part3 = "Eugene";
var part4 = name.SubString(lastSpace.End, name.End);      // "Cosmo"
var part5 = "IV";

var revisedName = "`part0` `part1` `part2` `part3` `part4` `part5`";

Console.WriteLine(revisedName);
```
```name=Console Window
The Handsome but Misunderstood Dr. Eugene Cosmo IV
```

 - See also [FindFirstOf](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/strings/.markdown#findfirstof)
 - See also [FindLastOf](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/strings/.markdown#findfirstof)

Besides **SubString**, there are two other String methods that return substrings:

- [ SubStringBytes](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#substringbytes-zero-engi) returns a string's substring that starts at the given byte index and runs for the given byte length:

```lang=csharp, name=SubStringBytes Example
var str = "abcdefghij";
//         0123456789
//      start ^
//            12345
//                ^ 5 bytes long
var sub = str.SubStringBytes(3, 5);
Console.WriteLine(sub);
```
```name=Console Window
defgh
```

IMPORTANT: A string that contains characters that are outside of the ASCII range will not have a matching rune count and byte count. Using **SubStringBytes** on such a string may produce undesired behavior.

- [ SubStringFromRuneIndices](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#substringfromruneindices) returns a string's substring that starts at the given starting rune index and ends one past the given ending rune index:

```lang=csharp, name=SubStringFromRuneIndices Example
var str = "abcdefghij";
//         0123456789
//     start ^      ^ one past the end
var sub = str.SubStringFromRuneIndices(2, 9);
Console.WriteLine(sub);
```
```name=Console Window
cdefghi
```

NOTE: Finding a given rune by its index requires a linear search through a string. Because **SubStringFromRuneIndices** requires two such searches, this method can be slower than **SubString**. In certain situations, such as a deeply nested loop, this performance difference may be significant.

 ##  ToLower and ToUpper

The [ ToLower](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#tolower-zero-engine-docu) method returns a copy of the original string with all of its letters converted to lowercase. Any character that is not an uppercase alphabetical character is unchanged:

```lang=csharp, name=ToLower Example
var sentence = "gEt ReKT scRUb";
var forbiddenWord = "scrub";

var lower = sentence.ToLower();

if (lower.Contains(forbiddenWord))
  Console.WriteLine("You have been reported for bad manners.");
else
  Console.WriteLine(sentence);
```
```name=Console Window
You have been reported for bad manners.
```

The [ ToUpper](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#toupper-zero-engine-docu) method is just like ToLower, except that it converts letters to uppercase:

```lang=csharp, name=ToUpper Example
var name = "Johnny";
var upperName = name.ToUpper();
var dialogue = "`upperName`: \"This is `name`.\"";
Console.WriteLine(dialogue);
```
```name=ConsoleWindow
JOHNNY: "This is Johnny."
```

 ##  Trim, TrimEnd, and TrimStart

The [ Trim](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#trim-zero-engine-documen) method returns a copy of the original string with all of its whitespace characters removed from its beginning and end:

```lang=csharp, name=Trim Example
var untrimmedID = "    f08b47e1            ";
Console.WriteLine("Your ID is `untrimmedID`. Write it down.");

var trimmedID = untrimmedID.Trim();
Console.WriteLine("Your ID is `trimmedID`. Write it down.");
```
```name=Console Window
Your ID is     f08b47e1            . Write it down.
Your ID is f08b47e1. Write it down.
```

[ TrimEnd](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#trimend-zero-engine-docu) and [ TrimStart](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown#trimstart-zero-engine-do) work just the same as **Trim**, except that **TrimEnd** only trims whitespace characters from the end of the string, and **TrimStart** only trims from the start of the string.

 #  Related Materials
 ##  Manual
- [ Looping](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/zilch_in_zero/looping.markdown)

 ##  Code Reference
- [ String](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/string.markdown)
- [ StringRange](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/stringrange.markdown)
- [ StringBuilder](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/stringbuilder.markdown)
- [ StringSplitRange](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/stringsplitrange.markdown)
- [ Rune](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/rune.markdown)
- [ RuneIterator](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/runeiterator.markdown) 

 