---
ID: 227225
post_title: >
  Visual Studio 2019 for Mac version 8.4
  Preview 2, now available
author: Pierre Crutchfield
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/visual-studio-2019-for-mac-version-8-4-preview-2-now-available/
published: true
post_date: 2019-11-04 06:00:16
---
Today we released the latest preview, Preview 2, of Visual Studio 2019 for Mac version 8.4. This preview comes with several exciting new features which we would love for you to try out. To get the preview: 
*   If you haven’t already, first [download and install Visual Studio 2019 for Mac][1]
*   [Switch to the preview version][2]

## Updates in this preview The focus of this preview is around accessibility improvements and .NET Core and ASP.NET Core. Let’s dive into the details of the updates. 

## Accessibility Enhancements Ensuring Visual Studio for Mac can be used by all users is important to us and we realize the need to support various assistive technologies to make this happen. Visual Studio for Mac previously had some built-in accessibility features compatible with VoiceOver and other assistive technologies. With the release of Preview 2, we’ve increased the surface area of the IDE accessible by assistive services to include several commonly used parts that were previously inaccessible. Those using assistive technologies will find general improvements over the entire IDE that include focus order, contrast, reduction of keyboard traps, more accurate VoiceOver navigation and reading, and more. We’ve also rewritten the UI for the debugger to make it accessible with VoiceOver. Improving accessibility of Visual Studio for Mac is a top priority for our team. While we have made rapid progress in this area recently, we are looking for some real-world users to assist in guiding the work. Try this preview and reach out to us to let us know what scenarios are working well and what and are not. If you would like to directly engage with us on our accessibility work, please email Dominic Nahous, the lead PM for the initiative at 

<dominicn@microsoft.com>. Now let’s move on to discuss the .NET Core specific updates. 
## .NET Core 3.1 Preview support In this release, we have added support for the latest preview of the .NET Core 3.1 SDK Preview 2. When you install the preview version of the IDE, that version of the .NET Core SDK will be installed automatically. We have full support for .NET Core 3.1 Preview 2 projects including: creating new projects, editing, building, debugging and other features. 

## ASP.NET Core Blazor Server Support In this release we are adding support for developing and publishing 

[ASP.NET Core Blazor Server][3] applications. If you haven’t heard of Blazor, it’s a framework for building interactive client-side web UI with .NET. Here are some of the advantages of using Blazor. 
*   Write code in C# instead of JavaScript.
*   Leverage the existing .NET ecosystem of .NET libraries.
*   Share app logic across server and client.
*   Benefit from .NET's performance, reliability, and security.
*   Stay productive with Visual Studio 2019 on PC, Linux, and macOS.
*   Build on a common set of languages, frameworks, and tools that are stable, feature-rich, and easy to use. In Visual Studio 2019 for Mac 8.4 Preview 2 you can create new Blazor server projects as well as get the standard support you would expect such as building, running and debugging Blazor projects. As you can see, the Blazor Server App project template is now available in the New Project dialog. 

<img class="alignnone wp-image-227228 size-large" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/vsmac-npd-blazor-1024x743.png" alt="" width="640" height="464" /> One of the areas where the team has focused on this release was adding support for editing .razor files. These are the files that you’ll be using when creating Blazor applications. If you’ve edited these files in the Windows version of Visual Studio 2019, then you’ll be very comfortable in Visual Studio 2019 for Mac. Both the Windows and Mac version of the IDE share the same editor for .razor files. You’ll see full colorization and completion support for your .razor files including completions for Razor components declared in the project. <img class="alignnone wp-image-227229 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/vsmac-blazor-editor01.gif" alt="vsmac blazor editor" width="902" height="578" /> You can also publish Blazor applications directly to [Azure App Service][4]. And if you don’t have an Azure account to run your Blazor app on Azure, you can always sign up for a free one [here][5] that also comes 12 months of free popular services, $200 free Azure credits, and over 25 always free services. 
## Updates to the editing experience

<img class="alignnone wp-image-227243 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/vsmac-blazor-editor-01.png" alt="vsmac blazor editor" width="1764" height="878" /> As mentioned before, the editor in Visual Studio for Mac now supports full colorization, IntelliSense and completion for .razor files. In addition to adding Blazor support, we’ve been hard at work adding features that have been top requests from our community. The biggest change that you will notice is that we brought back preview boxes for any code changes that may occur from a code fix or analysis suggestion. In the screenshot below, we see a preview of the changes that will occur if I use the “Make Static” codefix provided by Roslyn. <img class="alignnone wp-image-227244 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/vsmac-csharp-editor-01.png" alt="vsmac csharp editor" width="1514" height="764" /> To celebrate the new preview view, we are also providing several new code fixes like the aforementioned “Make Static” as well as the ability to add null checks to each parameter of a method. Finally, you may have noticed in the screenshots that the coloring looks more like what you may be used to on Visual Studio for PC. We’ve been working to standardize the Visual Studio theme, and we will be making more progress in this area in the releases ahead, so stay tuned! 
## Pack support for .NET Core library projects When creating .NET Core class libraries, you may be interested in distributing your library to a larger audience. To do this you need to create a NuGet package from your class library. In Visual Studio for Mac we made it very easy to create a NuGet package from a .NET Core library project. You right-click your project and then select the Pack menu option as per the example below: 

<img class="alignnone wp-image-227232 size-large" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/vsmac-pack-1024x561.png" alt="" width="640" height="351" /> After invoking the Pack menu option for a library project, you will find the NuGet package (.nupkg file) in the output folder. This experience is consistent with that in Visual Studio on PC. 
## Download and try today If you haven’t already make sure to 

[download Visual Studio 2019 for Mac][1] and then [switch to the preview channel][2]. With this release we are hoping that you’ll be able to easily get started with .NET Core 3.1 as well as Blazor Server applications. We encourage you to leave your comments either below in this post or by submitting issues to the developer community via [Report a Problem][6]. If you’re interested in upcoming releaseses, you’ll be happy to know that we have recently updated the [Visual Studio 2019 for Mac Roadmap][7] so please take a look and let us know your thoughts. Make sure to follow us on Twitter at [@VisualStudioMac][8] and reach out to the team. Customer feedback is important to us and we would love to hear your thoughts. Alternatively, you can head over to [Visual Studio Developer Community][9] to track your issues, [suggest a feature][10], ask questions, and find answers from others. We use your feedback to continue to improve Visual Studio for Mac 2019, so thank you again on behalf of our entire team.

 [1]: https://visualstudio.microsoft.com/vs/mac/
 [2]: https://aka.ms/vs4mac-preview
 [3]: https://docs.microsoft.com/aspnet/core/blazor/?view=aspnetcore-3.0
 [4]: https://azure.microsoft.com/services/app-service/
 [5]: https://azure.microsoft.com/free?ref=visualstudio
 [6]: https://docs.microsoft.com/en-us/visualstudio/mac/report-a-problem?view=vsmac-2019
 [7]: https://docs.microsoft.com/en-us/visualstudio/productinfo/mac-roadmap
 [8]: https://twitter.com/VisualStudioMac
 [9]: https://developercommunity.visualstudio.com/spaces/41/index.html
 [10]: https://developercommunity.visualstudio.com/content/idea/post.html?space=41