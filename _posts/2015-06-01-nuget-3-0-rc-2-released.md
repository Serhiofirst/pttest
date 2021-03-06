---
ID: 226042
post_title: NuGet 3.0 RC 2 Released
author: seroha
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/nuget-3-0-rc-2-released/
published: true
post_date: 2015-06-01 00:00:00
---
In the month since the Visual Studio 2015 RC release, we have heard from many of you with compliments, complaints, and bug reports. The NuGet team is happy to hear about all of the experiences you've had with our add-in for Visual Studio. The team has been hard at work preparing for the final release of Visual Studio, and would like to issue an update to the [Visual Studio extension][1] to ensure that we have ironed out some of the issues you may have run into. You can also get a copy of the extension from Codeplex at <https://nuget.codeplex.com/releases/view/615507>.

## Feature Tuning

We did not want to add any new features while leading up to the final release with Visual Studio 2015, but we did find one or two items that we wanted to tune to ensure that developers have a great experience with the NuGet tools. You will find in this update to the extension we have applied a number of performance updates to reduce the number of calls back to the NuGet.org service, the caching of the results in the package user interface, and remembering the state of the preview version checkbox from session to session.

Performance tuning made the extension processor hungry, and we found that at times it would consume all resources on the processor of our workstations. We've also introduced some throttling to ensure that the NuGet extension does not consume all available resources.

Additionally, we heard from a number of you that the Preview Window was something that you were not interested in seeing. Funny enough, there is a configuration option already available to hide the preview window... but its not something that we think was easy to find. To simplify, we added a checkbox to the preview window that allows you to hide it and prevent it from returning in future package operations.

![Location of checkbox to hide preview window][2]

## Fixes Addressed

We know that many developers are publishing packages that contain portable class libraries (PCLs) to support a variety of project types. In this release you will find that we addressed issues related to the Windows Phone and new Universal Windows Platform choose which PCL from within a NuGet package that they should install.

Additionally, we corrected an issue that [prevented Xamarin iOS projects][3] from copying content into your project properly. Similarly, C++ developer will be happy to hear that an issue that [prevented .targets files][4] from merging into a vcxproj file has been corrected as well.

Authentication for secured feeds was addressed in this release. We've reintroduced an authentication dialog when attempting to fetch content from a secured feed and we've taken care of issues related to querying that feed from the Powershell console.

One thing that started to really bother us, and a number of customers reported it, was that the Powershell auto-complete function was case sensitive. If I started searching for a microsoft.aspnet package, I would never find Microsoft.AspNet.Mvc In this release, we've adapted the auto-complete in Powershell to be case insensitive.

## Package Logging

One of the decisions we made early in this development cycle was to log all messages to the output window in Visual Studio. This meant that we also started dumping error messages from the execution of the add-in into the output window as well, and we know you don't want to see those errors that are outside of your project's operation in there. Internal issues with the NuGet client will now be logged to the standard Visual Studio activitylog.xml file that our Visual Studio support teams work with.

For those messages from the NuGet package management process that you do need to interact with, we have improved a number of them to provide better clarity about errors or warnings during processing.

## Summary

There are a number of other lower level fixes in this release, and if you are curious about them you can review the issues list on GitHub. We're happy with this release, and we know there is more to be built in our client tools. We're planning to release a client update at least once a month through July and August. Thank you for your interest, and happy coding!

 [1]: https://visualstudiogallery.msdn.microsoft.com/5d345edc-2e2d-4a9c-b73b-d53956dc458d,
 [2]: https://devblogs.microsoft.com/nuget/wp-content/uploads/sites/49/2019/05/previewCheckbox.png
 [3]: https://github.com/NuGet/Home/issues/445
 [4]: https://github.com/NuGet/Home/issues/281