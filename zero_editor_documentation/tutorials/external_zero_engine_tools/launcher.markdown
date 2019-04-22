This lesson introduces the **Zero Launcher** and explains how to use it.

 #  [Download the Engine](https://downloadlauncher.zeroengine.io)


 #  Learning Objectives


- Launcher tabs and sections
- Creating new projects
- Build installation


 #  The Discover Tab


The Discover tab is the Launcher's information hub. It features a number of useful links to informative websites:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90305.png)



#  The **ZeroHub** link opens the Zero Engine open-source development site.

# The **Documentation** link opens the Zero Engine documentation website.

#  The **Zilch** link takes you to the manual on Zilch, the programming language used by Zero Engine.

# The **Roadmap** link shows you Zero Engine's long term roadmap workboard.

#  The **Market** opens the Zero Market where you can find free and commercial assets for you projects.

# The **Q&A** link connects you to Zero Engine's Q&A page, where you can ask questions about the engine, the editor, Zilch, etc.


 #  The Projects Tab


 ##  The New Project Sub-Tab




![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90326.png)

1. Choose a template to start with:
 - Empty **2D Project** and **Empty 3D Project** will both result in an empty Zero project, but with a few differences in in editor settings and initial project configuration.
 - **Networked Project** is an empty 3D project with some pre-configured elements to facilitate proper architecture for a networked project.

| New Project Default Settings by Template |
|--|
| **Setting**  | **Description**| **EMPTY 2D PROJECT** | **EMPTY 3D PROJECT**|
|[ PhysicsSpace ](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/class_reference/physicsspace.markdown) {nav icon=check-square-o, name=Mode2D}| Default behavior for collision resolution| `true`|`false`|
|EditorCamera|Settings of editor camera|2D (orthographic, etc...)|3D (perspective, etc...)|
|Default Camera|Settings of the camera that is placed by default in each new level|2D (orthographic, etc...)|3D (perspective, etc...)|
|GridDraw Axis|Perpendicular axis to the grid plane|`ZAxis`|`YAxis`|

(NOTE) **Remember**, even if you start with the 2D template, **you can still use 3D elements and concepts in your game**, and vice versa. The template you choose simply specifies the default settings for certain properties.

2. Type a name for the project in the **Name** field. (You will be notified if a project by the same name already exists in the folder specified in the **Location** field.)

3. Specify where the project should be created in the **Location** field. The default path for new projects can be changed in [The Settings Tab ](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/editor/launcher.markdown#the-settings-tab). 
 - You can use the **Open Path** button next to the field to browse to a desired folder in your operating system's Folder Selection dialog.

4. Optionally, you may give the project *tags* by typing them, separated by commas, in the **Tags** field. Tags are just bits of text that can be used as keywords when searching for projects in the [Recent Projects](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/editor/launcher.markdown#recent-projects) subtab.

5. Specify which Zero Engine [build version](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/editor/launcher.markdown#the-builds-tab) that you want to use to create the project in the **Build** popup menu.

6. When you are ready, click the **Create Project** button. This will create a
  folder with the project name in the specified location containing the project
  file and Content folder.
Clicking the **Recent** button will bring up the Recent Projects subtab.


 ##  The Recent Projects Sub-Tab


Here, you will see a list of the latest Zero projects that you have worked on.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90330.png)

1. Each recently-used project appears here, with its name and modified date shown next to a thumbnail screenshot.
2. You may use the **Search** field to search through your recent projects, either by name or by tags.
3. When you mouse over a recent project, its **Remove** button will appear, which you may use to remove the project from the Recent Projects subtab.
 - Removing a project in this way only removes it from this list. It does not delete the project from your computer.

When you click on a recent project, you will see this:


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90332.png)


*The Recent Projects sub-tab, with a project selected*


1. To open the project, click the **Launch Project** button.
2. You may choose which installed Zero Engine [build version](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/editor/launcher.markdown#the-builds-tab) you wish to open the project in by selecting the desired build from the **Build** popup menu.
3. Clicking the **Open Path** button will open the project folder in your operating system.
4. To return to the list of recent projects, click the **Back** button.

Finally, in the Projects tab, there's the **Browse** button.


 ##  Browse Projects


Click Browse button to find a Zero project through your operating system's Open dialog.


 #  The Builds Tab


The Builds tab features a list of Zero Engine build versions that are installed on your computer or available for download.



![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90356.png)


1. Each build is listed in the **Build List** section of the builds tab, with its build number, release date, and tags.

2. Further information on the selected build can be found in the **Details** pane.

3. You may use the **Search** field to search through the Build List, either by build number or by tags.

4. Click the **Install Build** button to download and install the selected build.

5. Click the **Uninstall** button to remove the selected build from your computer.

NOTE: You may have **any number of different builds** installed simultaneously.


 # The Settings Tab


Finally, there's the **Settings** tab, found by clicking the little orange horizontal lines. Here, you can configure a number of different properties about how the Launcher itself behaves.


![image](https://media.githubusercontent.com/media/zeroengineteam/ZeroFiles/master/doc_files/90360.png)


1. The `Project Settings` drop down menu controls what happens when you open a project from your operating system (i.e., by double-clicking on its icon):
 - **Always open launcher**: Opening a project will open the Launcher and bring you directly to it in the Recent Projects subtab
 - **Auto run project if build installed**: If the Zero Engine build version that was used to save the project is installed on your computer, then the project will directly open in that version, bypassing the Launcher.

2. The `Default Project Location` field defines the default path where new projects will be created.
 - You can use the **Open Path** button next to the field to browse to a desired folder in your operating system's Folder Selection dialog.
 - New projects can still be created elsewhere, by specifying a different path in the [New Project subtab](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/tutorials/editor/launcher.markdown#the-new-project-sub-tab).

3. The `Default Download Location` field defines the path to which new build versions are downloaded and installed.
 - You can use the **Open Path** button next to the field to browse to a desired folder in your operating system's Folder Selection dialog.

4. The `Max Recent Projects` field sets how many recent projects will appear in the Recent Projects subtab.

5. The `Auto Check for Major Updates` field allows the launcher to periodically check the ZeroHub server to see if a new major version of Zero Engine has been released.

6. The `Show Development Builds` causes all public builds built off the **develop** branch in rZCORE to be seen in the Builds Tab. Many of these builds will be simple bug fixes and minor functionality changes. However, these builds are usually not guaranteed to be stable, and as such, most users should stick to builds tagged **stable**.

7. The `Show Experimental Builds` causes all public builds built off an **experimental** branch in rZCORE to be seen in the Builds Tab. These builds are often unstable and may contain large refactors or experimental functionality.

8. The `Revert to default` button restores the Launcher to its default settings.

 #  Related Materials
 ##  Manual
- [launcher](https://github.com/zeroengineteam/ZeroDocs/blob/master/zero_editor_documentation/zeromanual/editor/launcher.markdown) 

 
