---
ID: 226066
post_title: NuGet 3.2.1-RC and NuGet 2.9-RC released
author: seroha
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/nuget-3-2-1-rc-and-nuget-2-9-rc-released/
published: true
post_date: 2015-10-12 00:00:00
---
Today we are releasing nuget.exe 3.2.1-RC and NuGet 2.9-RC. A number of issues were identified in both versions that prevented interoperability on Linux and OSX operating systems. We also made some fixes to 3.2 in order to reduce network utilization.

## Changes

Below are the top highlights of these releases

### 2\.9-RC

1.  Now skipping interpreting nuspec documents that are not well formed
2.  Corrected an issue that prevented the NuGet extension from loading properly in Visual Studio 2013 Express
3.  Improved handling the /r/n characters during network communication from a non-Windows operating system

The complete 2.9 issue list is available in [GitHub][1]

### 3\.2.1-RC

1.  Corrected the casing of the NuGet.Config file being read. This fixes an issue for operating systems with case-sensitive filenames
2.  NuGet restore now ignores dnx projects (*.xproj) that should be processed with dnu
3.  Improved resource handling when interacting with v2 services
4.  Now updating csproj/vcxproj references properly when packages.config is updated
5.  Improved handling of packages in the local machine cache that may have gotten corrupted during download

The complete 3.2.1 issue list is available in [GitHub][2]

## Download from

NuGet 3.2.1 extension for Visual Studio 2015 <https://dist.nuget.org/visualstudio-2015-vsix/v3.2.1-rc/NuGet.Tools.vsix>

NuGet 3.2.1 command line <https://dist.nuget.org/win-x86-commandline/v3.2.1-rc/nuget.exe>

NuGet 2.9 extension for Visual Studio 2013 <https://dist.nuget.org/visualstudio-2013-vsix/v2.9.0-rc/NuGet.Tools.vsix>

### What's next

We are working through a number of changes to the Visual Studio 2015 user interface and to improve the upload experience to the NuGet.org service in addition to reviewing your feedback and addressing any issues that are presented to us. Look for a follow-up blog post later this week discussing the planned NuGet User Interface improvements.

 [1]: https://github.com/NuGet/Home/issues?q=milestone%3A2.9+is%3Aclosed
 [2]: https://github.com/NuGet/Home/issues?q=milestone%3A3.2.1+is%3Aclosed