---
ID: 226053
post_title: Announcing the NuGet 3.2 release
author: seroha
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/announcing-the-nuget-3-2-release/
published: true
post_date: 2015-09-16 00:00:00
---
Today we are publishing the version 3.2 updates to the NuGet clients. We took customer feedback regarding issues and feature direction and assembled this release to address those immediate concerns. There are fixes available for a number of blocking issues and adds support for push and list for compliant V3 servers. We also added support for the command line client to interact with v3 servers as well as project.json managed projects. You can download the updates to both the [nuget.exe command-line tool][1] and the [Visual Studio 2015 extension][2].

We also decided to increment the version of nuget.exe (NuGet command line) to 3.2 to match the release of the Visual Studio Extension. Both of these clients use the same core functionality, and we want to continue to publish them together. By aligning version numbers, we are communicating that they have matching feature sets.

Some of the NuGet 3.2 features related to project.json are depending on the win tools 1.1 release from today [available][3]

## Changes

Below are the top highlights of this release. Detailed [release notes for v3.2][4] are available.

### Command line

1.  Improve handling of authenticated feeds, and provide support for authenticated V3 feeds.
2.  Improve handling of network failures.
3.  Support list and push command against V3 feeds.
4.  Added Msbuild version selection support.
5.  Support for restoring packages in project.json managed projects

### Visual Studio Extension

1.  Improved handling of authenticated feeds, and added support for V3 authenticated feeds.
2.  Fixed issues with network connectivity failures. *
3.  Added restore context menu. This enables turning off "on build restore" or forcing a restore without building.
4.  Improved logging *
5.  Fixed issues for projects with linked app.config and web.config.
6.  Added support for multiple csproj in one folder with project.json.
7.  Fixed: NuGet in VS 2015 ignores disableSourceControlIntegration config setting.

*   *   These are areas we plan to invest more in the upcoming releases.

the complete list of issues is tracked here [Command line/NuGet.exe][5] and [Visual Studio Extension][6].

## Download from

NuGet extension for Visual Studio <https://dist.nuget.org/visualstudio-2015-vsix/v3.2.0/NuGet.Tools.vsix>

You can also update the NuGet extension with the Extensions and Updates feature inside of Visual Studio 2015.

Nuget command line <https://dist.nuget.org/win-x86-commandline/v3.2.0/nuget.exe>

### What's next

We have a collection of features and fixes that have been identified for our next client release. Included in this group are minor updates to the NuGet for Visual Studio 2015 user interface and some NuGet.org server updates that should help performance of all clients. We'll share a roadmap on a future blog post that outlines the features that are planned.

Over the next few weeks, we will be updating the NuGet.org service with new download statistics based on the traffic across our content delivery network and with reporting optimized to reduce stress on the main NuGet.org services. Additionally, a new status.nuget.org status page will be published that better demonstrates key metrics, availability of the service, and status messages from the NuGet team.

## Summary

With the release of high impact, targeted development items, we are confident that your development experience will improve. The near future of NuGet is exciting with several new features and several important customer feedback items targeted to be addressed in the Q3 2015 timeframe. We are also working on improving our documentation and our documentation publication process. NuGet is now a daily part of many developers process and we are going to continue to push to make it a quick and reliable component of your development effort.

 [1]: http://dist.nuget.org/index.html
 [2]: https://visualstudiogallery.msdn.microsoft.com/5d345edc-2e2d-4a9c-b73b-d53956dc458d?SRC=Home
 [3]: https://social.msdn.microsoft.com/Forums/en-US/e9df01f6-1474-4a4e-98fc-2567591c764f/update-11-release-notes-and-installation-instructions
 [4]: http://docs.nuget.org/release-notes/nuget-3.2
 [5]: https://github.com/nuget/home/issues?utf8=%E2%9C%93&q=is%3Aissue+milestone%3A3.2.0-commandline+is%3Aclosed+-label%3AClosedAs%3ADuplicate
 [6]: https://github.com/nuget/home/issues?q=is%3Aissue+is%3Aclosed+-label%3AClosedAs%3ADuplicate+milestone%3A3.2