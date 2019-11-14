---
ID: 226597
post_title: >
  Introducing solution-level NuGet Package
  Management in Visual Studio for Mac
author: Pierre Crutchfield
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/introducing-solution-level-nuget-package-management-in-visual-studio-for-mac/
published: true
post_date: 2019-10-03 11:35:23
---
Visual Studio 2019 for Mac version 8.3 comes with many new features as summarized in [this blog post][1]. While the entirety of this release was greatly influenced by your feedback, having the ability to manage packages at the solution level was one of the capabilities that most of you expressed as lacking in Visual Studio for Mac. A new solution-level NuGet Package Manager is one of the exciting new features of Visual Studio 2019 for Mac version 8.3. We've made improvements to help you discover packages more easily. This includes an improved experience while searching for new packages, gaining an understanding of what packages are already installed in your project, and finding packages that have updates available. In this blog post, we will focus on the package management experience for a Solution. However, most of the experiences including installing, updating, and viewing installed packages have a similar new experience at the project-level, too. To launch the NuGet Package Manager for a Solution, you can go to the context menu for the Solution and select “Manage NuGet Package…”: <img class="alignnone wp-image-226607" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/Solution-NuGet-Package-Manager-context-menu.gif" alt="Context menu for Solution-level NuGet Package Manager" width="634" height="404" />   
## Add new packages When you search and try to add a new package, you can now select the projects you want to install the package into. At any time, you can go to the 

**Installed** tab and view list of all the packages installed in your solution, allowing you to uninstall to update them. <img class="wp-image-226604 alignnone" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/npm-solution-install-1024x677.png" alt="NuGet Package Management Install" width="617" height="408" />   
## Update packages The 

**Updates** tab shows you all the packages in the solution for which updates are available (or a project, if you invoke the command at a project level). <img class="alignnone wp-image-226606" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/npm-solution-update.png" alt="NuGet Package Manager Updates" width="621" height="412" /> 
## Consolidate packages Often, large solutions end up in situations where different projects refer to different versions of a package. To consolidate these versions into one single version of the package that you might want to use across the solution, you can go to the consolidate tab of the NuGet Package Manager invoked at the solution node, select the package’s version to you would like all the projects in the solution to use and choose to 

**consolidate packages**: <img class="alignnone wp-image-226602" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/npm-solution-consolidate.png" alt="Consolidate packages" width="622" height="411" /> 
## Download today! To try out these new NuGet capabilities, 

[download the Visual Studio 2019 for Mac version 8.3 release][2] today or [update to the latest release using the Stable channel][3] if you already have Visual Studio for Mac installed. If you run into any issues with the version 8.3 release, please use the Help > [Report a Problem][4] menu in the IDE to let us know about it. You can also provide suggestions for future improvements to Visual Studio for Mac by using the Provide a Suggestion menu. <img class="alignnone wp-image-226609" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/VSMac-Report-a-Problem.png" alt="Report a Problem" width="249" height="223" /> Finally, make sure to follow us on Twitter at [@VisualStudioMac][5] to stay up to date on the latest Visual Studio for Mac news and let us know what your experience has been like. We look forward to hearing from you!  

 [1]: https://devblogs.microsoft.com/visualstudio/visual-studio-2019-for-mac-version-8-3
 [2]: https://www.visualstudio.com/vs/mac
 [3]: https://docs.microsoft.com/en-us/visualstudio/mac/update?view=vsmac-2019#changing-the-updater-channel
 [4]: https://docs.microsoft.com/en-us/visualstudio/mac/report-a-problem?view=vsmac-2019
 [5]: https://twitter.com/VisualStudioMac