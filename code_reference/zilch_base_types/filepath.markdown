 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ AddTrailingDirectorySeparator](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#addtrailingdirectorysepa)|[ DirectorySeparator](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#directoryseparator-zero)| | |
|[ ChangeExtension](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#changeextension-zero-eng)|[ ExecutableDirectory](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#executabledirectory-zero)| | |
|[ CombineDirectories](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#combinedirectories-zero)|[ ExecutableFile](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#executablefile-zero-engi)| | |
|[ CombineDirectoriesAndFile](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#combinedirectoriesandfil)|[ TemporaryDirectory](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#temporarydirectory-zero)| | |
|[ GetCanonicalizedPathFromAbsolutePath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#getcanonicalizedpathfrom)|[ UserDocumentsDirectory](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#userdocumentsdirectory-z)| | |
|[ GetComparablePathFromAbsolutePath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#getcomparablepathfromabs)|[ UserLocalDirectory](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#userlocaldirectory-zero)| | |
|[ GetDirectoryName](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#getdirectoryname-zero-en)|[ WorkingDirectory](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#workingdirectory-zero-en)| | |
|[ GetDirectoryPath](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#getdirectorypath-zero-en)| | | |
|[ GetExtensionWithDot](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#getextensionwithdot-zero)| | | |
|[ GetExtensionWithoutDot](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#getextensionwithoutdot-z)| | | |
|[ GetFileNameWithExtension](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#getfilenamewithextension)| | | |
|[ GetFileNameWithoutExtension](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#getfilenamewithoutextens)| | | |
|[ IsRelative](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#isrelative-zero-engine-d)| | | |
|[ RemoveTrailingDirectorySeparator](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/filepath.markdown#removetrailingdirectorys)| | | |


 #  Properties


---  
 #  DirectorySeparator : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only` `static`

> Gets the character(s) used for separating directories and files. This value is often different depending on the operating system (generally either '/' or '\')

> ``` lang=cpp, name=Zilch
> var DirectorySeparator : String


---  
 #  ExecutableDirectory : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only` `static`

> The directory the executable lives with in (exe, elf...). This will always include a directory separator at the end of the result.

> ``` lang=cpp, name=Zilch
> var ExecutableDirectory : String


---  
 #  ExecutableFile : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only` `static`

> A path directly to the executable itself (exe, elf...).

> ``` lang=cpp, name=Zilch
> var ExecutableFile : String


---  
 #  TemporaryDirectory : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only` `static`

> Temporary files should be placed here. This will always include a directory separator at the end of the result.

> ``` lang=cpp, name=Zilch
> var TemporaryDirectory : String


---  
 #  UserDocumentsDirectory : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only` `static`

> User saved data that the user can backup or modify should be placed here (read/write/create permissions should be allowed). This will always include a directory separator at the end of the result.

> ``` lang=cpp, name=Zilch
> var UserDocumentsDirectory : String


---  
 #  UserLocalDirectory : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `read-only` `static`

> Application saved information should be placed here (read/write/create permissions should be allowed). This will always include a directory separator at the end of the result.

> ``` lang=cpp, name=Zilch
> var UserLocalDirectory : String


---  
 #  WorkingDirectory : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> A directory that all relative paths start resolving from. In general the changing of the working directory is discouraged because it may affect assumptions of the host application. This will always include a directory separator at the end of the result.

> ``` lang=cpp, name=Zilch
> var WorkingDirectory : String


---  
 #  Methods


---  
 #  AddTrailingDirectorySeparator : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Pass in a directory path with or without the separator and this will add it at the end (if needed).
Example: ('Content\Powerups') results in 'Content\Powerups\'
Example: ('Content\Powerups\') results in 'Content\Powerups\'

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function AddTrailingDirectorySeparator(p0 : String) : String
> ``` 


---  
 #  ChangeExtension : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Changes the extension of a path (with file name at the end) to a new extension. If the file has no extension, then this will automatically add the extension to the end. The extension is allowed to contain a leading dot '.' character (or not). The path is also allowed to contain a trailing dot '.' character (or not).
Example: ('Content\Player.png', 'jpg') results in 'Content\Player.jpg'
Example: ('Content\Player', 'jpg') results in 'Content\Player.jpg'
Example: ('Content\Player.', '.jpg') results in 'Content\Player.jpg'

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |p1|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function ChangeExtension(p0 : String, p1 : String) : String
> ``` 


---  
 #  CombineDirectories : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Combines directory paths and directories names together (empty entries are skipped). This will always include a directory separator at the end of the result.
Example: ('Content', 'Powerups') results in 'Content\Powerups\'
Example: ('Content\', 'Powerups\') results in 'Content\Powerups\'
Example: ('Content\', '', 'Powerups') results in 'Content\Powerups\'
Example: ('C:\Sandbox\', 'Content') results in 'C:\Sandbox\Content\'

> |Name|Type|Description|
> |---|---|---|
> |dir0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir1|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function CombineDirectories(dir0 : String, dir1 : String) : String
> ``` 


---  
 #  CombineDirectories : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Combines directory paths and directories names together (empty entries are skipped). This will always include a directory separator at the end of the result.
Example: ('Content', 'Powerups') results in 'Content\Powerups\'
Example: ('Content\', 'Powerups\') results in 'Content\Powerups\'
Example: ('Content\', '', 'Powerups') results in 'Content\Powerups\'
Example: ('C:\Sandbox\', 'Content') results in 'C:\Sandbox\Content\'

> |Name|Type|Description|
> |---|---|---|
> |dir0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir1|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir2|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function CombineDirectories(dir0 : String, dir1 : String, dir2 : String) : String
> ``` 


---  
 #  CombineDirectories : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Combines directory paths and directories names together (empty entries are skipped). This will always include a directory separator at the end of the result.
Example: ('Content', 'Powerups') results in 'Content\Powerups\'
Example: ('Content\', 'Powerups\') results in 'Content\Powerups\'
Example: ('Content\', '', 'Powerups') results in 'Content\Powerups\'
Example: ('C:\Sandbox\', 'Content') results in 'C:\Sandbox\Content\'

> |Name|Type|Description|
> |---|---|---|
> |dir0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir1|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir2|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir3|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function CombineDirectories(dir0 : String, dir1 : String, dir2 : String, dir3 : String) : String
> ``` 


---  
 #  CombineDirectories : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Combines directory paths and directories names together (empty entries are skipped). This will always include a directory separator at the end of the result.
Example: ('Content', 'Powerups') results in 'Content\Powerups\'
Example: ('Content\', 'Powerups\') results in 'Content\Powerups\'
Example: ('Content\', '', 'Powerups') results in 'Content\Powerups\'
Example: ('C:\Sandbox\', 'Content') results in 'C:\Sandbox\Content\'

> |Name|Type|Description|
> |---|---|---|
> |dir0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir1|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir2|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir3|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir4|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function CombineDirectories(dir0 : String, dir1 : String, dir2 : String, dir3 : String, dir4 : String) : String
> ``` 


---  
 #  CombineDirectoriesAndFile : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Combines directory paths, directories names, and a single file name together (empty entries are skipped). Because we are combining a file name at the end, this will not result in a trailing directory separator.
Example: ('Content\Powerups\', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('Content\Powerups', '', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('Content', 'Powerups', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('C:\Sandbox\', 'Content\Player.png') results in 'C:\Sandbox\Content\Player.png'

> |Name|Type|Description|
> |---|---|---|
> |dir0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |fileName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function CombineDirectoriesAndFile(dir0 : String, fileName : String) : String
> ``` 


---  
 #  CombineDirectoriesAndFile : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Combines directory paths, directories names, and a single file name together (empty entries are skipped). Because we are combining a file name at the end, this will not result in a trailing directory separator.
Example: ('Content\Powerups\', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('Content\Powerups', '', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('Content', 'Powerups', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('C:\Sandbox\', 'Content\Player.png') results in 'C:\Sandbox\Content\Player.png'

> |Name|Type|Description|
> |---|---|---|
> |dir0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir1|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |fileName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function CombineDirectoriesAndFile(dir0 : String, dir1 : String, fileName : String) : String
> ``` 


---  
 #  CombineDirectoriesAndFile : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Combines directory paths, directories names, and a single file name together (empty entries are skipped). Because we are combining a file name at the end, this will not result in a trailing directory separator.
Example: ('Content\Powerups\', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('Content\Powerups', '', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('Content', 'Powerups', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('C:\Sandbox\', 'Content\Player.png') results in 'C:\Sandbox\Content\Player.png'

> |Name|Type|Description|
> |---|---|---|
> |dir0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir1|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir2|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |fileName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function CombineDirectoriesAndFile(dir0 : String, dir1 : String, dir2 : String, fileName : String) : String
> ``` 


---  
 #  CombineDirectoriesAndFile : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Combines directory paths, directories names, and a single file name together (empty entries are skipped). Because we are combining a file name at the end, this will not result in a trailing directory separator.
Example: ('Content\Powerups\', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('Content\Powerups', '', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('Content', 'Powerups', 'Recharge.png') results in 'Content\Powerups\Recharge.png'
Example: ('C:\Sandbox\', 'Content\Player.png') results in 'C:\Sandbox\Content\Player.png'

> |Name|Type|Description|
> |---|---|---|
> |dir0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir1|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir2|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |dir3|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> |fileName|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function CombineDirectoriesAndFile(dir0 : String, dir1 : String, dir2 : String, dir3 : String, fileName : String) : String
> ``` 


---  
 #  GetCanonicalizedPathFromAbsolutePath : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Changes all directory separators to be the current operating system directory separator, removes duplicate separators, and removes '..' and '.' from the paths. Canonicalized is only guaranteed to work on absolute paths. This behavior is operating system dependent and may call the related OS functions.
Example: ('C:/Sandbox//Engine/../Content/./Player.png') results in 'C:\Sandbox\Content\Player.png'

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetCanonicalizedPathFromAbsolutePath(p0 : String) : String
> ``` 


---  
 #  GetComparablePathFromAbsolutePath : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> First this normalizes the path, then if the operating system is case insensative, it will make the path all lowercase so that it compares.
Example: ('C:\Sandbox\Engine\..\Content\.\Player.png') results in 'c:\sandbox\content\player.png'

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetComparablePathFromAbsolutePath(p0 : String) : String
> ``` 


---  
 #  GetDirectoryName : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> If a file path is passed in, this will return the name of the parent directory. If a directory path is passed in (ending in a separator), this will return the name of the directory. A directory path without a trailing separator is abiguous with a file that has no extension. In this case, we always assume it is a file and therefore get the parent directory's name.
Example: ('Content\Powerups\Recharge.png') results in 'Powerups'
Example: ('Content\Powerups\') results in 'Powerups'
Example: ('Content\Powerups') results in 'Content'
Example: ('Content') results in ''

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetDirectoryName(p0 : String) : String
> ``` 


---  
 #  GetDirectoryPath : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> If a file path is passed in, this will return the parent directory. If a directory path is passed in (ending in a separator), this will return the directy back with no modifications. A directory path without a trailing separator is abiguous with a file that has no extension. This will always include a directory separator at the end of the result. In this case, we always assume it is a file and therefore get the parent directory's name.
Example: ('Content\Powerups\Recharge.png') results in 'Content\Powerups\'
Example: ('Content\Powerups\') results in 'Content\Powerups\'
Example: ('Content\Powerups') results in 'Content\'
Example: ('Content') results in ''

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetDirectoryPath(p0 : String) : String
> ``` 


---  
 #  GetExtensionWithDot : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Returns only the extension of a file (everything after the last dot, including the dot). If the file has no extension then this will return an empty string.
Example: ('Content\Player.png') results in '.png'
Example: ('Content\Player.') results in ''
Example: ('Parent.Directory\Log') results in ''

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetExtensionWithDot(p0 : String) : String
> ``` 


---  
 #  GetExtensionWithoutDot : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Returns only the extension of a file (everything after the last dot, not including the dot). If the file has no extension then this will return an empty string.
Example: ('Content\Player.png') results in 'png'
Example: ('Content\Player.') results in ''
Example: ('Parent.Directory\Log') results in ''

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetExtensionWithoutDot(p0 : String) : String
> ``` 


---  
 #  GetFileNameWithExtension : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Returns only the file portion of a path (everything past the last separator including the extension).
Example: ('Content\Player.png') results in 'Player.png'
Example: ('Content\Powerups\') results in ''
Example: ('Content\Powerups') results in 'Powerups'

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetFileNameWithExtension(p0 : String) : String
> ``` 


---  
 #  GetFileNameWithoutExtension : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Returns only the file portion of a path (everything past the last separator excluding the extension).
Example: ('Content\Player.png') results in 'Player'
Example: ('Content\Powerups\') results in ''
Example: ('Content\Powerups') results in 'Powerups'

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function GetFileNameWithoutExtension(p0 : String) : String
> ``` 


---  
 #  IsRelative : [boolean](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/boolean.markdown)

 `static`

> Returns true if a path has no root (such as a volume/hard drive specifier, or unix like systems a beginning slash). Even a beginning slash that means 'relative to the current working directory volume' is still relative. Empty paths will return that they are relative.
Example: ('C:\Sandbox\Engine\..\Content\.\Player.png') results in 'false'
Example: ('Sandbox') results in 'true'
Example: ('Content\Powerups\Recharge.png') results in 'true'
Example: ('/usr/Content/Player.png') results in 'false'

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function IsRelative(p0 : String) : Boolean
> ``` 


---  
 #  RemoveTrailingDirectorySeparator : [string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)

 `static`

> Pass in a directory path with or without the separator and this will remove it from the end (if needed).
Example: ('Content\Powerups') results in 'Content\Powerups'
Example: ('Content\Powerups\') results in 'Content\Powerups'

> |Name|Type|Description|
> |---|---|---|
> |p0|[string](https://github.com/zeroengineteam/ZeroDocs/blob/master/code_reference/zilch_base_types/string.markdown)| |
> ``` lang=cpp, name=Zilch
> function RemoveTrailingDirectorySeparator(p0 : String) : String
> ``` 


---  
 

 