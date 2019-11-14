---
ID: 226423
post_title: >
  Visual Studio 2019 version 16.2
  Generally Available and 16.3 Preview 1
author: Jacqueline Widdis
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/visual-studio-2019-version-16-2-generally-available-and-16-3-preview-1/
published: true
post_date: 2019-07-24 11:30:56
---
Today we are making Visual Studio 2019 version 16.2 generally available, as well as Preview 1 of version 16.3. You can download both versions from [VisualStudio.com][1]. If you already have Preview installed, you can alternatively click the notification bell from inside Visual Studio to update. We’ve highlighted some notable features below, but you can also see a list of all the changes in the [current release notes][2] or the [Preview release notes][2]. 
### What to expect in Visual Studio version 16.2

##### Test Explorer Test Explorer provides better handling of large test sets, easier filtering, more discoverable commands, tabbed playlist views, and customizable columns to fine-tune test information displayed. [video poster="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2018/08/vsfeaturemed.png" width="960" height="496" mp4="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/LnOrL9l-Imgur.mp4" loop="true" autoplay="true"][/video]     [caption id="attachment_225937" align="aligncenter" width="1156"]

<img class="wp-image-225937 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/VSTestExplorer1.png" alt="This image shows the expanded Test Explorer ." width="1156" height="406" /> *<span style="font-size: 10pt">Improved Test Explorer</span>*[/caption]   
##### .NET Developer Productivity Version 16.2 supports debugging JavaScript in the new Microsoft Edge Insider browser for ASP.NET and ASP.NET Core projects.  To do this, install the browser, set a breakpoint in the application’s JavaScript and start a debug session. There are improvements in .NET developer productivity as version 16.2 brings back the 

**Sort Usings** refactoring option. Developers also have the ability to convert switch statements to switch expressions and also generate a parameter for a variable from the Quick Actions menu. In addition, there is an enriched experience of creating and configuring [Azure SignalR services][3] when enabling real-time communication in web applications. 
##### C++ In the C++ space, changes include 

[Clang/LLVM support for MSBuild projects][4], incremental build for Windows Subsystem for Linux, and a new C++ quick action to install missing packages in CMake projects using vcpkg. [caption id="attachment_225945" align="aligncenter" width="427"]<img class="wp-image-225945 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/CMakeProject1.png" alt="CMake projects using vcpkg" width="427" height="94" /> *<span style="font-size: 10pt">C++ quick action to install missing packages in CMake projects using </span>*vcpkg[/caption]   Changes in the throughput of the C++ linker significantly improve iteration build times for the largest of input.  This should result in an improvement to all codebases.  Internal measurements taken on the C++ team saw 2X ranges for /debug:fast and /incremental, while /debug:full typically ranged from 3X to 6X and up.  More information is available on the [C++ Team Blog][5]. [caption id="attachment_225944" align="aligncenter" width="1420"]<img class="wp-image-225944 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/Cmake2.png" alt="C++ Iteration Build Time Demo" width="1420" height="489" /> *<span style="font-size: 10pt">Improvements to the C++ linker.</span>*[/caption]   
##### Usability To enhance usability, users who opted to hide their toolbars in Visual Studio receive additional vertical space. Upon hiding all toolbars, the Live Share, Feedback and Badge icons are moved to the top.  The steps to restore the toolbar are View > Toolbars and select the desired toolbar. [caption id="attachment_225940" align="aligncenter" width="1406"]

<img class="wp-image-225940 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/PreviewFeaturesListing1.png" alt="Adding and removing toolbar selections" width="1406" height="32" /> *<span style="font-size: 10pt">Increased usability of the toolbar</span>*[/caption]   A list of preview features is findable under Tools > Options > Environment > Preview Features.  This page also allows users to learn about upcoming features as well as participate in surveys to provide additional perspectives on future changes. 
### Looking forward to 16.3 Preview 1: .NET Core 3.0 Preview and C++

##### .NET Core 3.0 Preview Version 16.3 Preview 1 has added support for .NET Core 3.0 Preview.  Additional features include .NET Core project templates like Worker and gRPC for building microservices or Blazor for building client web apps using C#. 

##### Improved Search Because the ability to search in Visual Studio is a key driver for discoverability, there is an added search box in the start window for users to quickly locate recently used projects, solutions, and folders. The most recently used code containers also integrate with Visual Studio global search so they can be found there as well. This is a direct result of it being one of the highest voted feature requests.  Thanks for all of the feedback! [caption id="attachment_225942" align="aligncenter" width="1024"]

<img class="wp-image-225942 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/SearchRecentProjects.gif" alt="" width="1024" height="710" /> *<span style="font-size: 10pt">Improved search feature example</span>*[/caption] Finding the right project template should be easier than previous iterations.  Template search in the New Project Dialog now supports fuzzy search allowing for typos and plurals while also highlighting matching keywords and ranking results based on relevance. [caption id="attachment_225941" align="aligncenter" width="1021"]<img class="wp-image-225941 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/SearchAccuracyinProjectTemplate.gif" alt="" width="1021" height="706" /> <span style="font-size: 10pt"><em>Recent project search example</em></span>[/caption] Visual Studio will now pick up any updates made to the templates via the .NET CLI and, as a result, the two are kept in sync. New tooling is included in support of the new templates.  Examples include publishing worker projects to container registries and managing Open API & gRPC service references. This version of Visual Studio also includes many productivity improvements. C++ projects now have IntelliSense member lists filtered based on type qualifiers. Developers have the ability to toggle line comments with a quick command (Ctrl + K, Ctrl + /). .NET projects load more asynchronously and renaming classes in the editor can also rename the containing file. Furthermore, debugging and profiling includes better Edit and Continue support.  There is also auto-expanding of the hot path in the performance profiler and the ability to move both forwards and backward in the profiler during an investigation. 
### Give it a try today and let us know what you think! Everyone is encouraged to update to Visual Studio 2019 version 16.2 by

[ downloading directly from VisualStudio.com][1] or updating via the [notification bell inside Visual Studio][6]. An alternative option includes the Visual Studio Installer for updates. Try out the 16.3 Preview 1 release by [downloading it online][7] or updating from within the IDE from a previous Preview Channel release. Most noteworthy, Visual Studio teams are continuously driven by feedback, so we look forward to hearing what you have to say about our latest releases. If you discover any issues, make sure to let us know by using the [Report a Problem tool][8] in Visual Studio. Additionally, you can head over to [Visual Studio Developer Community][9] to track your issues, [suggest a feature][10], ask questions, and find answers from others. We use your feedback to continue to improve Visual Studio 2019, so thank you again on behalf of our entire team.

 [1]: https://visualstudio.microsoft.com/downloads/
 [2]: https://docs.microsoft.com/en-us/visualstudio/releases/2019/release-notes
 [3]: https://aka.ms/signalr-service-overview
 [4]: https://devblogs.microsoft.com/cppblog/clang-llvm-support-for-msbuild-projects/
 [5]: https://devblogs.microsoft.com/cppblog/
 [6]: https://docs.microsoft.com/visualstudio/install/update-visual-studio?view=vs-2019
 [7]: https://visualstudio.microsoft.com/vs/preview/
 [8]: https://docs.microsoft.com/en-us/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2019
 [9]: https://developercommunity.visualstudio.com/
 [10]: https://aka.ms/vs-suggest