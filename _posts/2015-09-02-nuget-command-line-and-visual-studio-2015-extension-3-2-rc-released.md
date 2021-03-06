---
ID: 226051
post_title: >
  NuGet Command line and Visual Studio
  2015 Extension 3.2 RC released
author: seroha
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/nuget-command-line-and-visual-studio-2015-extension-3-2-rc-released/
published: true
post_date: 2015-09-02 00:00:00
---
Today we are releasing nuget.exe 3.2-RC command line. In addition to fixing a significant number of bugs, support has been added for push and list for compliant V3 servers.

This wave also includes a release of the visual studio extension version 3.2-RC. This version is about addressing top blocking customer scenarios.

The 3.2 RTM release is planned for September, for both nuget.exe and the NuGet extension.

Note: We decided to bump the version of nuget.exe (NuGet command line) to 3.2 to match the release of the Visual Studio Extension.

## Changes

Below are the top highlights of this release

### Command line

1.  Improve handling of authenticated feeds, and provide support for authenticated V3 feeds.
2.  Improve handling of network failures.
3.  Support list and push command against V3 feeds.
4.  Added Msbuild version selection support.

### Visual Studio Extension

1.  Improved handling of authenticated feeds, and added support for V3 authenticated feeds.
2.  Fixed issues with network connectivity failures. *
3.  Added restore context menu. This enables turning off "on build restore" or forcing a restore without building.
4.  Improved logging *
5.  Fixed issues for projects with linked app.config and web.config.
6.  Added support for multiple csproj in one folder with project.json (pending release of win 10 tools).
7.  Fixed: NuGet in VS 2015 ignores disableSourceControlIntegration config setting.

*   *   These are areas we plan to invest more in the upcoming releases.

the complete list of issues is tracked here [Command line/NuGet.exe][1] and [Visual Studio Extension][2].

## Download from

NuGet extension for Visual Studio <https://dist.nuget.org/visualstudio-2015-vsix/v3.2.0-rc/NuGet.Tools.2015.vsix>

Nuget command line <https://dist.nuget.org/win-x86-commandline/v3.2.0-rc/nuget.exe>

### Why did we move to the dist model?

1.  We moved off codeplex and we wanted a new easy-to-find place for the binaries.
2.  NuGet 3.2 command line has some breaking changes from NuGet.exe 2.8, and although subtle we didn't want to break existing users that auto pull the latest version.

### What's next

When we go live with the RTM release we plan to introduce both an html page linked from nuget.org that shows all available downloads, and a most recent version download link (per major version and globally). We later plan to add a json end point to be able to programmatically get the available downloads.

## What else is going on with the team

We are working on finalizing the RTM releases for the above packages, as well as planning the work for the 3.3 release. Now that most of the critical blockers have been addressed, we started working on the UI update. [UI Design meeting][3] are available here, along with links to discussion and feedback items.

On the server side we are working on boosting performance, scalability and reliability as well as moving the download statistics to a new mechanism that will reduce a large portion of the server stress. We are also finalizing a new status page to better communicate the status of the service. Both of these are in final stages of testing and validation and we hope to deploy them soon.

## Summary

Since the last release (3.1.1) in July, we have been focusing on the improving the quality of the NuGet extension. The focus was on high impact, short development items that we felt confident delivering in a shorter release cycle. We are also working on enhancing the documentation towards the RTM release of 3.2 and beyond. We plan to keep investing in the quality push, bug fixes towards the next release, as well as tackle bigger items than we did in this release.

 [1]: https://github.com/nuget/home/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A3.2.0-commandline+is%3Aclosed+-label%3AClosedAs%3ADuplicate
 [2]: https://github.com/nuget/home/issues?q=is%3Aissue+is%3Aclosed+-label%3AClosedAs%3ADuplicate+milestone%3A3.2
 [3]: https://github.com/NuGet/Home/wiki