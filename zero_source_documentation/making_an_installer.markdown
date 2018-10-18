These steps are what the build machine does to make a build. This assumes you have msbuild installed (normally through Visual Studio), Innosetup, and currently Winrar, although a different kind of zipping utility can be used.

Note that I will use mix using cmd style environment variables: %EnvironmentVarName and msbuild style environment variables: `$(EnvironmentVarName)`.

How to build an Zero for an installer (not actually making the installer, just the exe):

1. The first thing you have to do to build zero is have a copy of it. You  must check out the ZeroCore depo. This should check out the necessary sub-depos of Tools, ExtensionLibraries, StandardLibraries, and Zilch.

  - To actually make the installer you also need to checkout the DevTools repo into the Zero folder, that is you should have `Zero/DevTools/OpenDevTools.cmd`.

2. For a clean build, make sure that any old build artifacts are deleted for the configuration you are running. That is, go to wherever `$(ZERO_OUTPUT)` is defined and delete the folders `$(ZERO_OUTPUT)/Int/$(Platform)/$(Configuration)` and `$(ZERO_OUTPUT)/Out/$(Platform)/$(Configuration)`.

  - For example, `$(Platform)` is Win32 and `$(Configuration)` is Release.

3. Actually build the configuration. In Visual Studio this is just done by opening and building. To use msbuild via command line you must first open via the visual studio command prompt or first run `vcvars32.bat` which is located at `%VS100COMNTOOLS%/../../VC/bin/vcvars32.bat` (or whatever version of visual studio, where VS100 is 2010). The arguments for msbuild are: `msbuild Zero.sln /p:Configuration=$(Configuration) /p:Platform=$(Platform) /t:rebuild`. Expand `$(Configuration)` and `$(Platform)` yourself to whatever the correct names are. For making an actual build use Win32 and Release.
4. You should now have `ZeroEditor.Exe` located at `$(ZERO_OUTPUT)/Out/$(Platform)/$(Configuration)/Win32Editor`

How to make an installer from an already built exe:

1. Make sure the devtools depo is checked out
2. Make sure that you run `SetUpBuildEnvironment.cmd` under `Zero/DevTools`. This setups up the location of `$(ZERO_OUTPUT)` and `$(ZERO_SOURCE)` for use in further steps
3. Run the `BuildMaker.exe` tool. It is located in `DevTools/BuildMaker`. You can either run the pre-cached exe in this folder or open the project and build it. To make a build run the command: `BuildMaker.exe -outputSuffix Out/$(Platform)/$(Configuration)/Win32Editor -prefix ZeroEngineSetup -branch default`. The `-prefix` command is the prefix to assign to the exe's name. This will invoke innosetup and make the `ZeroEngineSetup.Version.Date.exe` under the folder `Zero/Build/Output`. For details on how this works see the section on the inno setup build script.
4. To make the .zerobuild file currently you must install zero and then zip up the install directory. Ideally you should also delete the `unins00.exe` and other uninstaller portions first. The current command line to do this (ignoring the deletion of the uninstall exe) is for winrar. WinRar.exe: `a -r -ep1 -m5 "$(OutputDir)/ZeroEngine.zip" "$(InstallDir)\*. $(OutputDir)` is wherever you want to save the output zip to and `$(InstallDir)` is likely to be `C:\Program Files (x86)\ZeroEditor`. The arguments for winrar archive the entire directory with a good compression and it recursively iterates all folders while keeping the folder structure (in case you need to do this in another zipping program). This zip should then be renamed to match the exe's name (with the version and date).

How to archive data for symbol servers and source indexing:

- These steps are how to save data for debugging at a later date from a built exe. Note that this works after building the zero's exe and must be performed on the same exe (and pdb and so on) as the one used to make the installer.

1. Make sure the devtools repo is checked out.
2. Make sure that you run SetUpBuildEnvironment.cmd under `Zero/DevTools`. This setups up the location of `$(ZERO_OUTPUT)` and `$(ZERO_SOURCE)` for use in further steps
3. Add source indexing to the pdb. Source indexing adds information to the pdb to check out the correct version of a file for the date the exe was made. A small tools was added to make this easier. The current arguments are:

  - `SourceIndexer.exe -depo "$(ZERO_SOURCE)" -depo "$(ZERO_SOURCE)\Zilch" -depo "$(ZERO_SOURCE)\ExtensionLibraries" -depo "$ZERO_SOURCE)\ExtensionLibraries\StandardLibraries" -pdb "$(ZERO_OUTPUT)/Out/$(Platform)/$(Configuration)/Win32Editor/ZeroEditor.pdb"`
  - Basically you need to add every location that a repository exists (including sub-repos) and then provide the location of the pdb to edit. For more information on how to use/test this see `Readme.txt` in `Zero/DevTools/SourceIndexer`.

4. This modifies the pdb in place to contain all extra symbol information. Do not release this pdb to other people as it tells them how to check out source code.
5. Add the symbols to the symbol server. The symbol server is a local "server" that stores information to be looked up by visual studio at a later date for debugging crash dumps. Search for symstore for more information on command line args. The current arguments we use to store are:

  - `symbstore add /f "($ZERO_OUTPUT)/Out/$(Platform)/$(Configuration)/Win32Editor" /s "$(SymbolServerLocation)" /t ZeroEditor /compress`
  - The `$(SymbolServerLocation)` is the local location of the symbol server. `/t` gives a name to the items being added (change accordingly) and `/compress` compresses the symbols by a significant factor. The `symstore.exe` is located under `Zero/DevTools/SourceIndexer/symstore`. Additional tools useful for debugging this process are lcoated in the srcsrv folder next to it.

How to run a project unit test:

- First assume that we already have an exe for zero somewhere defined via $(ZeroExe).
- Before running all tests it is a good idea to delete all cached content for zero to avoid any build artifacts. This is accomplished by deleting the folder %Temp%/ZeroContent.
- For each project you want to test:

  1. Delete the old project folder so as to avoid any accidental build artifacts.
  2. Check out the project via mercurial. The exact location doesn't matter.
  3. Run the project via the args: `$(ZeroExe) -file $(ZeroProjPath) -RunUnitTests -logStdOut -ProjectName $(ProjectName) -Builder $(BuilderName)`

      -ProjectName and -Builder are arguments that affect where screenshots are saved to. This depends on the project's exact implementation, but most go to $(Temp)/ZeroScreenshots/$(Builder)/$(ProjectName).

  4. To diff screenshots currently you must run the ImageDifferTest.py script in the buildbot depo with the location of the saved previous results and the new results.

Zero's InnoSetupScript:
- The inno setup script is located at Zero/Build/ZeroEngineInstall.exe. Do note that we expect `$(ZERO_SOURCE)` and `$(ZERO_OUTPUT)` to be defined. Read the first comment to show how to replace #defines via command line arguments.
- Now for some important locations:

  1. The `[Files]` tag defines what folders/files we package up. This currently includes everything in the Tools, Resource, and Data folders next to zero. Additionally we grab the Win32Editor folder's contents, ignoring certain file types (see the Excludes: section).
  2. `[Registry]` defines the additional registry keys we make. These are to define the file association, the icon, and the open command.
  3. `[Run]` deletes the old content cache. This should be less necessary now that content is cached into a folder based upon the version number.
  4. `[Code]` section runs some commands to uninstall zero if it was already installed and to close any open copies.

Zero Launcher:

1. Checkout and build the launcher the same as with zero, the only difference is that the output exe and dll go to the Win32ZeroLauncher folder.
2. Make sure the devtools repo is checked out.
3. Run the ZeroLauncherVersionIdUpdater:

  - This program does 3 things, first of all it copies all of the necessary files into one location to make it easier to generate an installer and zip (it makes the zip for you). It also will contact the server and check the current ZeroLauncherVersionId.txt file (located currently under `data/www/Builds/StandAlones` and then generate a local copy of the file with a newer version number. Finally it'll actually run the inno setup script.
  - The current arguments for this are:
    - `ZeroLauncherVersionIdUpdater.exe --ZeroOutDir "$(ZERO_OUTPUT)/Out/$(Platform)/$(Configuration)/Win32ZeroLauncher" --SourceDir "$(ZERO_SOURCE)" --OutDir "$(PackageOutDir)"` where the `$(PackageOutDir)` is wherever you want to save the package to.

4. To actually update what's on the server you must then copy the `ZeroLauncherVersionId.txt` file and the `ZeroLauncherPackage.zip` file to `data/www/Builds/StandAlones` folder on the server. You should also copy the `ZeroLauncherSetup.exe` to `data/www/Builds` folder.
5. To debug crashes with the launcher SourceIndexing and the SymbolServer should also be run. This is basically the same, just provided the correct different names and paths.

Zero Launcher Innoscript:

1. `[Registry]` section is almost the same, the main new items are the subkey's of Upgrade and Run which add new right-click context menus. There's alos a section down below that adds the ValueName: "Icon" which adds custom icons for these items.
2. `[Files]` since the package is made with all of the needed files, we only have to include this folder.
 

 