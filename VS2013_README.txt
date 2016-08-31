Visual Studio 2013
==================

pythonnet contains a new solution file for Visual Studio 2013: pythonnet.sln
It should make development under Windows much easier since you don't have to
install MSys or Cygwin to run the makefile.

The solution file should work with the free VS 2013 .NET Express Edition.

Note: The solution project requires the following NuGet dependencies in order to build properly:

	Microsoft.Net.Compilers Version 1.3.2 which is needed to enable C# 6.0 language support
	Unmanaged Exports by Robert Giesecke Version 1.2.7
	NUnit 2.6.2

Depending on your local Visual Studio configuration, you may need to open Solution Explorer, then right-click on top-level Solution and select Enable NuGet Package Restore 
to download dependencies prior to building.

Available configurations
------------------------

Every configuration copies the dll, pdf and exe files to the root directory
of the project.

 * Release
   Builds Python.Runtime, Python.Tests, clr.pyd and python.exe. The console
   project starts a Python console
   
 * Debug
   Same as Release but creates a build with debug symbols
   
 * UnitTest
   Builds a Debug build. The console project invokes runtests.py instead of
   opening a Python shell.
   
 * EmbeddingTest
   Builds Python.EmbeddingTests and its dependencies. The configuration
   requires the NUunit framework.
   
Python version
--------------

You can switch the destination version by defining either PYTHON27, PYTHON32, PYTHON33, PYTHON34, PYTHON35
inside the Python.Runtime and clrmodule projects.

 ** Don't forget to force a rebuild after you have altered the setting! **

MS VS doesn't take changes to define into account.

Thanks to Virgil Duprasfor his original VS howto!

Christian 'Tiran' Heimes

Updated by Alexander McLin for Visual Studio 2013.
