---
layout: post
title: Solution User Options (.Suo) File
date: 2022-02-01 08:00:00.000000000 +00:00
type: post
tag: Visual Studio
---

The solution user options (.suo) file contains per-user solution options. ___This file should not be checked in to source code control.___

The solution user options (.suo) file is a structured storage, or compound, file stored in a binary format. You save user information into streams with the name of the stream being the key that will be used to identify the information in the .suo file. The solution user options file is used to store user preference settings, and is created automatically when Visual Studio saves a solution.

When the environment opens a .suo file, it enumerates all currently loaded VSPackages. If a VSPackage implements the IVsPersistSolutionOpts interface, then the environment calls the LoadUserOptions method on the VSPackage asking it to load all of its data from the .suo file.

It is the VSPackage's responsibility to know what streams it might have written into the .suo file. For each stream that it wrote, the VSPackage calls back to the environment through LoadPackageUserOpts to load a particular stream that is identified by the key, which is the name of the stream. The environment then calls back to the VSPackage to read that particular stream passing the name of the stream and an IStream pointer to the LoadPackageUserOpts method.

At that point, another call is made to LoadUserOptions to see if there is another section of the .suo file that has to be read. This process continues until all of the data streams in the .suo file have been read and processed by the environment.

When the solution is saved or closed, the environment calls the SavePackageSolutionProps method with a pointer to the SaveUserOptions method. An IStream containing the binary information to be saved is passed to the WriteUserOptions method, which then writes the information to the .suo file and calls the SaveUserOptions method again to see if there is another stream of information to write to the .suo file.

These two methods, SaveUserOptions and WriteUserOptions, are called recursively for each stream of information to be saved to the .suo file, passing in the pointer to IVsSolutionPersistence. They are called recursively to allow for the writing of multiple streams to the .suo file. In that way, user information is persisted with the solution and is guaranteed to be there the next time the solution is opened.

Source: 
<a href="https://docs.microsoft.com/en-us/visualstudio/extensibility/internals/solution-user-options-dot-suo-file?view=vs-2022" target="_blank">Click here to visit</a>

Hope it helps.
