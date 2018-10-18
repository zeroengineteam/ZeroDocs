 `Core`

|Methods|Properties|Base Classes|Derived Classes|
|---|---|---|---|
|[ Close](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#close-void)|[ StandardError](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#standarderror-zero-engin)| | |
|[ IsRunning](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#isrunning-zero-engine-do)|[ StandardInput](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#standardinput-zero-engin)| | |
|[ Constructor](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#processclass-void)|[ StandardOutput](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#standardoutput-zero-engi)| | |
|[ Start](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#start-void)| | | |
|[ Terminate](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#terminate-void)| | | |
|[ WaitForClose](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processclass.markdown#waitforclose-zero-engine)| | | |


 #  Properties


---  
 #  StandardError : [filestream](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/filestream.markdown)

 `read-only`

> The stream where standard error is re-directed to. Null if not re-directed
> ``` lang=cpp, name=Zilch
> var StandardError : FileStream


---  
 #  StandardInput : [filestream](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/filestream.markdown)

 `read-only`

> The stream where standard input is re-directed to. Null if not re-directed
> ``` lang=cpp, name=Zilch
> var StandardInput : FileStream


---  
 #  StandardOutput : [filestream](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/filestream.markdown)

 `read-only`

> The stream where standard output is re-directed to. Null if not re-directed
> ``` lang=cpp, name=Zilch
> var StandardOutput : FileStream


---  
 #  Methods


---  
 #  Close : Void

> Closes the wrapper around the process, does not close the process launched.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Close()
> ``` 


---  
 #  IsRunning : [boolean](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/boolean.markdown)

> Returns true if the process is still running, false otherwise.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function IsRunning() : Boolean
> ``` 


---  
 #  ProcessClass : Void

 `constructor`

> Process class used for managing external processes and redirecting their stdio. Used to launch and monitor various external programs.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function ProcessClass()
> ``` 


---  
 #  Start : Void

> Begins the execution of another process using the given parameters. 
> |Name|Type|Description|
> |---|---|---|
> |startInfo|[processstartinfo](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/processstartinfo.markdown)| |
> ``` lang=cpp, name=Zilch
> function Start(startInfo : ProcessStartInfo)
> ``` 


---  
 #  Terminate : Void

> Attempts to manually shut down the process. This is not safe for the other process or what it's handling.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function Terminate()
> ``` 


---  
 #  WaitForClose : [integer](https://github.com/zeroengineteam/ZeroDocs/code_reference/zilch_base_types/integer.markdown)

> Waits for a process to close, this will block until the process closes.
> |Name|Type|Description|
> |---|---|---|
> ``` lang=cpp, name=Zilch
> function WaitForClose() : Integer
> ``` 


---  
 

 