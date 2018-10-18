
Before doing anything with crash dumps you should do 2 things:
	1. Checkout the DevTools repo
	2. Checkout a special depo of zero (or you could re-use one but it's best to make another) and add the environmental variable `ZERO_SOURCE` to point at the root of that depo.
	
The majority of what you care about is in the Readme.txt file under the SourceIndexer folder. Follow these steps to setup source indexing on your local machine. Currently the symbol server is only available on the local Engineering network.



Now to briefly describe how these things work (part of this is how the build server works). There are 3 things needed to debug crash dumps:	Symbols (pdb), Source, and the exe. These are handled by 2 separate processes: Symbol Server and Source Indexing.

Symbol Server
-------------
The symbol server caches copies of dlls, exes, pdbs and so on by a hashset to be looked up later. When opening a crash dump, if you set up the symbol server stuff as mentioned in the Readme.txt, visual studio will contact the symbol server and grab the correct copies of exes, dlls, and pdbs and cache them locally in some temp directory. This happens on the build server by running symstore.exe and giving it the path to the editor's output and the name to group it under (the name is just to make it easier to find stuff in the symbol store) as well as where the symbol server is. If you want to run this on a random machine you must first create the symbol server; look up documentation for symstore.exe.

Source Indexing
---------------
Even with the symbol server setup, we still don't get source for a file at that revision. This is handled via another step called source indexing. The pdb is actually a file format that can store various files under stream names. There is a special stream named "SRC_SRV" that stores information about how to get a copy of a file from source control. For source indexing, you write to this stream a file that contains something along the lines of: FileName at %Revision% comes from the mercurial repository at %ZERO_SOURCE% with the command hg checkout FileName at %Revision% > %OutLocation%. This is currently done via the SourceIndexer program in the DevTools repository. This program takes in a source tree location and a collection of repository locations to pull from and embeds them in the pdb. Note that the source indexing needs to be embedded into the pdb before the symbol server is run. Also note that at the moment there are hard-coded repository names in the SourceIndexer program that should ideally be removed later.

Crash dumps for zero are currently downloadable from http://zerocrash.digipen.edu. This website needs a large update though as it's really slow... 

 