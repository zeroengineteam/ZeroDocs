This page covers how to export your project.

 # Export to a stand alone executable
For small projects this is the easiest option. It will produce an executable that should run on any windows machine

 - Open your project
 - Run the [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands.markdown) : [ExportGame](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#exportgame)
 - Select a executable file name
 - You are done!

 # Export for an installer
If you project is a very large stand alone, executable may not be the right options since it has to extract the files when it runs.

 - Open your project
 - Run the [Command](https://github.com/zeroengineteam/ZeroDocs/zero_editor_documentation/zeromanual/editor/editorcommands.markdown) : [ExportContent](https://github.com/zeroengineteam/ZeroDocs/code_reference/command_reference.markdown#exportcontent)
 - A folder will be opened will all the files that need to be in the installer
 - The [Inno-Setup ](http://www.jrsoftware.org/isdl.php ) file will generate an installer
   ![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/47333.png)
 

 