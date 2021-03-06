---
ID: 226040
post_title: NuGet 2.8.5 Released
author: seroha
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/nuget-2-8-5-released/
published: true
post_date: 2015-03-31 00:00:00
---
In the last few weeks we saw a significant change in the NuGet ecosystem with the renaming of the K utilities and framework monikers to DNX. To support that change and provide backwards compatibility for existing versions of Visual Studio, we are publishing an update to NuGet extensions for Visual Studio 2010, 2012, and 2013. This update does not work with Visual Studio 2015 and is an update for existing 2.x NuGet extensions only. A copy of the [release notes][1] are available online.

[Download the NuGet 2.8.5 update now][2]

## Framework Monikers Added

To allow packages that also target older versions of the .NET framework to continue to support the new capabilities of ASP.NET 5 and DNX we introduced three new framework monikers that can be used in the NuGet spec and package folder names:

*   **core50** - A 'base' target framework moniker (TFM) that is compatible with the Core CLR.
*   **dnx452** - A TFM specific to DNX-based apps using the full 4.5.2 version of the framework
*   **dnx46** - A TFM specific to DNX-based apps using the full 4.6 version of the framework
*   **dnxcore50** - A TFM specific to DNX-based apps using the Core 5.0 version of the framework

## Other fixes

we also included an important fix of an issue that prevented packages from installing into FSharp projects properly:

<https://nuget.codeplex.com/workitem/4400>

## Summary

NuGet continues to support older versions of Visual Studio as newer technologies are released. We will continue this practice so that newer versions of packages and NuGet services do not impair your development experience on older versions of development tools.

 [1]: http://docs.nuget.org/release-notes/nuget-2.8.5
 [2]: http://nuget.codeplex.com/releases/view/612846