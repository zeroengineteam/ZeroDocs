**This section is important for anyone doing cross platform work**

The Platform library provides file IO, threading, timers, sockets, and other common operating system primitives. Platform by itself is mostly a collection of headers (interface only) with a PIMPL style pattern to hide the implementation of each primitive. In specific it provides:

- File

  - Read/write stream, seeking, etc

- File Path

  - Concatenation of paths and helpers with OS specific / or \

- File System

  - Iteration over directories/files, file existence, delete / move files, etc

- Floating Point Control

  - Turning on or off processor specific float extensions

- Process

  - Execution of an external process with stdin/out hooks (not via the sell)

- Socket
- Thread
- Thread Synchronization

  - Mutex, Critical Section, Semaphore, Events, etc

- Timer

  - Highest resolution timer supported by the OS

- External Library Loading (.dll, .so)
- Crash Handler
- Directory Watcher

Project Layout
--------------
Some code exists within Platform where we determined it was similar enough on most operating systems (e.g. Berkeley sockets). We have separate projects for each operating system, e.g. WindowsPlatform, PosixPlatform, etc. These platforms implement each primitive interface to the best of their ability. The reason we chose to use separate implementation projects was to avoid the explosion of #if/#endif. Any code that is considered 'helper' code that would be exactly the same among all platforms can be directly implemented in Platform.

The PosixPlatform is ideally usable among Unix like platforms with minor #ifdef modifications (Linux, OsX, iOS, Android). The EmptyPlatform is ideally a stub that can be copied onto brand new platforms (with all functions stubbed out to do nothing) just to get code up and running quickly.

Private Implementation
----------------------
One particular point of interest is the ZeroDeclarePrivateData macros inside of PrivateImplementation.hpp. Typically the PIMPL pattern is implemented via a pointer on the class to a forward declared private data structure. This pattern typically requires allocation of some sort. To avoid allocation, we instead created a byte buffer on each primitive that is sized to the largest size of all platforms we implement. ZeroDeclarePrivateData will create this buffer, and other macros allow us easy access to the buffer. Static asserts are used to ensure that the buffer will never be too small for the contents placed within it. Though this pattern does avoid allocation, we may in the future opt for a more classic PIMPL pattern to allow objects to vary more widely in size and just for ease of use.

Shell Library
-------------
Platform differs from the Shell library (e.g. WindowsShell or any other platform Shell) in two ways. Platform does not rely on virtual functions for its abstraction, and it separates the interface from implementation via header and cpp files. The Shell library uses an abstract base class with virtual functions that get overridden for the current platform. Moreover, the Shell also may not exist such as when running from a console or server. In the future, the Shell may change to be more like the Platform library.

How To Extend Platform
----------------------
Any time a new primitive needs to be implemented that touches OS specific code, it is often best done in Platform. The simplest approach to add a new primitive is to copy the Thread or File header, clear them out, and start from there. Go into EmptyPlatform and copy either the Thread or File cpp, and stub it out to match the hpp interface. From there, copy it into WindowsPlatform, PosixPlatform, and any other platforms. Be sure to adjust 'ZeroDeclarePrivateData' on the header to account for enough space for all the private data. Global functions are useful for quick helpers (such as getting the OS user-name, where no primitive needs to be allocated and stored).

Another consideration is what errors we return from the OS when using primitives. In the beginning we either opted to ignore errors (asserting when they would happen) or to return bools. This proved to be insufficient because often we needed to give feedback to the user. For example, we attempt to open a file in their game's Content directory, but it fails due to security permissions. The assert would catch this on developer computers only because asserts are stripped in Release mode. These situations typically happen in the wild, and not on developer machines. A bool would at least give us information as to why it failed, but that's not enough for the user to correct a situation. The best approach was to use the 'Status' object. is basically a standardized way for us to return pseudo exceptions without using exception handling. We generally take the Status object by reference as the first parameter, and we set it to either success or failure with an error message provided by the OS. Callers can easily check status for failure, as well as print messages to the console or do popups in the GUI. In the future, all primitives will be moved to status (status may also get an option to automatically assert on failure, just to give more control to the caller).
 

 