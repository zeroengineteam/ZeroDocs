This lesson covers the Market, and how to use it to download content for your projects.

 #  Learning Objectives

- Becoming acquainted with the Market's interface
- Learning how to download content and use it in a project

 #  Level Setup

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ New Project](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
 - Create a new project using the {nav icon=clone, name=2D Project} template
- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- In the `Properties Window`
 - Under [ Transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
  - Set Translation  to `[0, -3, 0]`
  - Set Scale  to `[10, 1, 1]`
 - Under [ Sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
  - Set SpriteSource enum to `Square`
 - [ Add Component](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown) : `BoxCollider`



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101883.png) *The level so far*


[ The Market](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/using_the_market.markdown) is an online content collection. Users (including the #zero_engine_developers) can upload and download assets to and from the Market for use in their projects. The Market can be accessed from within the Zero Editor or from a web browser, but this tutorial will just use the Market's in-editor interface.

 #  Accessing the Market

To open the Market, just click its button in the upper right corner of the editor.

- Left-click  the **Market button**


![Market Button](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/100750.gif) *The Market button opens the Market*


There's a lot to see in the Market, but this tutorial will just cover downloading a specific package. Among the assets on the Market is a professional-quality character controller written by the Zero Engine developers, and that's what we want to download. It's included in the `Sample Character Controller` content pack.

- In the `Search field`
 - Search for `sample character controller`
   ![Searching the Market](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101083.gif)

The search results show the content pack we're looking for.

- In `the Market`
 - Left-click  the `Sample Character Controller` product banner image
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101085.png)

When you click the product's banner image, you're taken to its page.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101087.png) *The product page for the Sample Character Controller content pack*


This product supplies two separate downloads: a content pack and a demo project showing it off. The demo's file extension is `.zeroprojpack`, while the content pack's is `.zeropack`. Let's download the content pack.

- In `the Market`
 - In the `Sample Character Controller` product page
  - In the **Download** section
   - Left-click  the content pack download link
     ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101095.png)

After you click the download link, a few things will happen (usually very quickly). First, Zero adds the task of downloading the content pack to its list of **Background Tasks**, which can be viewed in the upper-right corner of the editor:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101098.png) *The Background Tasks panel*


When that task is completed, a notification to that effect will pop up in the lower-right corner of the editor:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101100.png) *The notification pop-up*


Finally, and most importantly, the `Import Content Package Window` will appear, listing the assets from the content pack:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101893.png) *The Import Content Package Window*


- In the `Import Content Package Window`
 - Left-click  the Import button button

This content pack includes the `SweptController` character controller component, plus a set of archetypes demonstrating it. Let's try out the 2D archetype.

- In the `Library Window`
 - Under Archetype 
  - `Drag and drop` an instance of `SweptPlayer2D` into the `Level Window`



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101885.png) *The level with a player*


- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
 - Use the `A` and `D` keys and the `Space` bar to move the player and jump



![SweptController Demonstration](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/101887.gif) *The SweptController in action*


You can use the Market to add content like the SweptController to any of your future projects.

- [ Command](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown) : [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)

 #  Related Materials
 ##  Manual
- [using_the_market](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/using_the_market.markdown)
- [commands](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/editorcommands/commands.markdown)
- [addremovecomponent](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/addremovecomponent.markdown)
 ##  Reference
 ###  Commands
- [ NewProject](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#newproject)
- [ CreateSprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#createsprite)
- [ PlayGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#playgame)
- [ StopGame](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/command_reference.markdown#stopgame)
 ###  Classes
- [transform](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/transform.markdown)
- [sprite](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/sprite.markdown)
- [boxcollider](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/boxcollider.markdown)
- [rigidbody](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/rigidbody.markdown)
 ##  Development Task
- {T1450}
 

 