---
ID: 225958
post_title: Support for Native Projects
author: seroha
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/support-for-native-projects/
published: true
post_date: 2013-04-26 00:00:00
---
In the [NuGet 2.5 release notes][1], we called out that NuGet now has support for native projects. We wanted to explain exactly what "support for native projects" means.

## Visual Studio Support

Until NuGet 2.5, if you were working in a Visual C++ project, the 'Manage NuGet Packages' context menu would not show up for the project; with NuGet 2.5, we now light this up. Any time we start supporting a new project type, we have to test to ensure all operations are working as expected. Each project system has slightly different behavior and this proved to be true with Visual C++ as well. We made the changes necessary to get NuGet install/update/uninstall operations working.

## MSBuild Integration

C++ projects tend to have many different configurations--more than what NuGet is able to handle. To address NuGet's configuration limitations, we are relying heavily on MSBuild properties and targets for native packages. These MSBuild properties and targets do the heavy lifting of providing references at build time, based on your project's configuration.

To make MSBuild integration better, NuGet has created a new convention for automatically importing MSBuild properties and targets from a NuGet package. Alongside the existing content, lib, and tools folders, NuGet now recognizes a new top-level folder: **build**.

Within the build folder, you can provide a ".props" file and/or a ".targets" file that will be automatically imported into the project. For this convention, the file name must match your package id with either a ".props" or ".targets" extension. For example, the '[cpprestsdk][2]' package includes a 'cpprestsdk.targets' file in its build folder. Files with the ".props" extension will be imported at the top of the project file, and files with the ".targets" extension will be imported at the bottom of the project file.

Note that this build folder can be used for all NuGet packages and not just native packages. The build folder respects target frameworks just like the content, lib, and tools folders do. This means you can create a buildnet40 folder and a buildnet45 folder and NuGet will import the appropriate props and targets files into the project. You no longer need to write PowerShell install.ps1/uninstall.ps1 scripts to import MSBuild targets files!

## Native Target Framework

When targeting native projects, a new target framework name is now recognized: **native**. There is no versioning within the 'native' target framework; NuGet treats all C++ projects the same.

We expect that most native packages will be produced using the **buildnative** folder, with at least a targets file and then a props file if needed. The 'native' target framework is also recognized for the content and tools folders, but because NuGet cannot directly add references to native projects, the 'native' target framework *is not* recognized within the lib folder.

## Creating Native Packages

If you’re interested in publishing your native libraries via NuGet, you can choose to create the NuGet packages manually. However, there’s an easier way--the CoApp project volunteered to write C++ oriented tools to create NuGet packages, and they have [released a beta version][3] of their tools. These tools simplify the process of generating the MSBuild files and NuGet packages from existing header and library files--you just need to create a configuration script to describe the contents of the package and then run the tools to generate the NuGet package.

There are [tutorials][4], [reference documentation][5], and a [video][6] on how to use the tools to create NuGet packages. The CoApp project organizers also plan to create and publish packages for several open source libraries into the NuGet Gallery over the next several weeks.

We’re encouraging people to publish packages with the "native" tag to make it easier to find packages you can use in C++ projects. You can search the NuGet Gallery using "tag:native" to find packages tagged with "native". This works from both [nuget.org][7] and within Visual Studio. *Note that not all packages tagged with "native" are actually C++ projects though.*

The [CoApp][8] and [Openness@Microsoft][9] blogs have additional information about this project.

## Feedback

Please leave us feedback here on the blog--we’d love to hear your experiences trying out NuGet in your C++ projects, and whether there are additional features we could add to make this work even better for you. This is just the start of C++ integration in NuGet and we need your input on where we should take this in the future to make working with C++ libraries in Visual Studio easier.

## Related Links and Announcements

*   [NuGet 2.5 Release Announcement][10]
*   [NuGet 2.5 Download Page][11]
*   [CoApp's PowerShell Tools Installer to create NuGet packages for C++ libraries and tools][12]
*   [Announcement on the Visual C++ Team Blog][13]
*   [Announcement on the Openness@Microsoft Blog][9]
*   [Announcement on the CoApp Blog][8]

 [1]: http://docs.nuget.org/docs/release-notes/nuget-2.5
 [2]: https://nuget.org/packages/cpprestsdk/
 [3]: http://coapp.org/pages/releases.html
 [4]: http://coapp.org/pages/tutorials.html
 [5]: http://coapp.org/pages/reference.html
 [6]: https://www.youtube.com/watch?v=l4MAkR13JPA
 [7]: https://nuget.org/packages?q=tag%3Anative
 [8]: http://coapp.org/news/2013-04-26-Announcing-CoApp-Tools-For-NuGet.html
 [9]: http://blogs.technet.com/b/openness/archive/2013/04/26/nuget-coapp-release.aspx
 [10]: http://blog.nuget.org/20130425/nuget-2.5-released.html
 [11]: https://nuget.codeplex.com/releases/view/96733
 [12]: http://coapp.org/releases
 [13]: http://blogs.msdn.com/b/vcblog/archive/2013/04/26/nuget-for-c.aspx