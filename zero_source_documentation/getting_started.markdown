Before diving into Zero Source, it is important to become familiar with Zero itself as a game engine. Please visit [getting_started](https://github.com/zeroengineteam/ZeroDocs/blob/master/getting_started.markdown).

For more information specifically about the Zilch C++ API, visit:

 - [zilch.digipen.edu ](http://zilch.digipen.edu )

Requirements
------------
- Windows 7 or higher
- Visual Studio 2010 (2012/2013/2015 will work but require 2010 compiler)

  - Express versions will work with Zero and can be used Commercially
  - http://go.microsoft.com/?linkid=9709969 (2010 ISO)

- Tortoise HG

  - http://tortoisehg.bitbucket.org/download/
  - If you are not familiar with mercurial, visit http://hginit.com

Pulling the ZeroCore repository is all that is required to start building Zero (all dependencies are included).

When we start-up Zero on Windows, we use a .cmd file because the locations of libraries may be redefined by environmental variables. We've tried to keep it as simple as possible: downloading the Zero source and opening it via the .cmd should bring you to Visual Studio, and you can immediately build and run from there. You should set Win32Editor as the start-up project. Win32Editor implements the classic WinMain (and on other platforms we would have a similar system). The WinMain performs some Windows specific tasks such as setting up the crash handler or Visual Studio Output window, and then creates the engine by calling Startup. The Startup function is mostly generic and will probably be re-factored for different platforms, however currently the different systems that we initialize are very dependent on which Os you are running on so we left it there (Joysticks, Touch System, etc). Startup is also responsible for creating the Editor or running a game if this is a standalone exported project. The Editor currently has a lot of functionality on it and over time we'll be replacing parts of it with script, and separating a lot of different functionality out into separable modules.

Custom Components
-----------------
- Requires documentation

  - Dependencies
  - Serialization
  - Meta Binding
  - Editor vs Game

Creating a Space and Cog
------------------------
- Requires documentation

Custom Resources
----------------
- Requires documentation

  - Data resources
  - Complex / binary resources

Meta Binding
------------
- Requires documentation

Serialization
-------------
- Requires documentation

Tools
-----
- Requires documentation

Commands
--------
- Requires documentation

Resource Editors
----------------
- Requires documentation

Gizmos
------
- Requires documentation

Debug Draw
----------
- Requires documentation

  - Selection

 

 