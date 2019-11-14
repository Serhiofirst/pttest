---
ID: 225908
post_title: >
  Visual Studio 2019 for Mac version 8.2
  is now available (and a Preview for 8.3)
author: Pierre Crutchfield
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/visual-studio-2019-for-mac-version-8-2-is-now-available-and-a-preview-for-8-3/
published: true
post_date: 2019-07-24 10:00:58
---
Today we are announcing the release of Visual Studio 2019 for Mac version 8.2, as well as Preview 1 of version 8.3. We have a lot of new features and updates in both releases that we’d like to share with you! 
*   [Download Visual Studio 2019 for Mac 8.2][1]
*   [Download Visual Studio 2019 for Mac 8.3 Preview 1][2] If you already have Visual Studio for Mac 2019 installed, you can update to either of these versions using the 

[integrated updater][3]. You can view the release notes for each of these releases at the [Release Notes][4] page. You also may be interested in checking our [Roadmap][5] to get a sense of our future plans. We hope you have a great experience with these new features, but if you do run into any issues please use [Report a Problem][6] to make us aware of them. 
## Visual Studio 2019 for Mac version 8.2 The 8.2 release has a lot of great features that are now ready for you to use. One big area we continue to invest heavily on is the code editing experience. Let’s start with the improvements to the editors, and then go from there. Over the past few weeks, we have been working hard to improve the different editor experience in Visual Studio for Mac. In this release, we are including a new editor in the IDE for XAML and AXML files. These editors are the same as those available in Visual Studio on Windows, but the implementation uses the Cocoa APIs to provide a native experience on macOS. 

### C# Editor In version 8.1 of Visual Studio 2019 for Mac, we introduced the new C# editor and we continue to add features to further improve the code editing experience in Visual Studio for Mac. With the latest release, we are introducing IntelliSense Type Filtering as well as the ability to include import items in your IntelliSense completion list. IntelliSense Type Filtering allows you to better organize your completion list to only include the types you are looking for. For example, if you only want to see classes, either clicking the class icon or hitting the hotkey for classes ( ⌥ + C) will limit the results to only classes. You can also include multiple filters. We’ve also added the ability to add import items to the completion list for IntelliSense, which will populate your list with types from packages which are not yet imported into your project. Adding a class or other type from the list will then automatically add the import statement to your project, allowing you to focus solely on writing code. 

<img class="alignnone size-full wp-image-225910" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/TypeFilteringDark-Retina.gif" alt="type filtering" width="1702" height="1023" /> 
### XAML Editor This update includes some notable XAML improvements in the following areas: IntelliSense, performance, reliability, and linting. In the animated gif below you can see the new experience for XAML files. 

<img class="alignnone size-full wp-image-225912" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/vs4mac-xaml-editor.gif" alt="xaml editor" width="1331" height="890" /> By adding the new XAML editor, we also included a new XAML Language Service. This is the same language service that is found in Visual Studio. One benefit of this new language service is an improved experience for matching capabilities. As an example, it now supports fuzzy, substring and CamelCase matching. This should help you author your XAML faster and more accurately. 
*   **Fuzzy Matching:** Typing any portion of a string will provide a list of matching and like matches. If you type “stck”, StackLayout will still appear as an option.
*   <span style="font-size: 1rem"><strong>Substring Matching:</strong> Matches will be listed when you type a part of a string, even if it is in the middle of the string. This is a great feature if you recall a section of a command, but not the entire command. Typing “Lay” will match “StackLayout” along with any other string which contains “lay”. </span>
*   **Case Insensitive Matching:** If you can’t recall the exact casing of a string you’re trying to find, case insensitive matching will ensure you can still find what you’re looking for. With support for this kind of matching, typing “stack” will match to “StackLayout”. In addition to these updates, you’ll also see a much-improved auto-complete experience for XAML files. 

### AXML Editor When developing Android applications, you often find yourself editing .axml files. These files are used to define the Android application’s UI and resources. In this release, we have also updated the editor for these files. The enhancements are similar to those in the XAML editor. Some specific improvements include: IntelliSense, semantic editing of these files, as well as support for go-to-definition. Here is a screenshot of this new editor: 

<img class="alignnone wp-image-225913 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/vs4mac-axml-editor.png" alt="vsmac-axml-editor" width="974" height="385" /> 
### Support for .NET Core 3.0 and C# 8.0 Preview The team has been hard at work to add support for .NET Core 3.0 Preview and C# 8 into Visual Studio for Mac. With this release you’ll find that we officially support .NET Core 3.0 Preview and C# 8. To get started, after installing Visual Studio for Mac, you will need to install a preview of the 

[.NET Core 3.0 SDK][7]. Please note that currently the [.NET Core 3.0 SDK][8] is not bundled with the IDE, but we will include it in a future release. After installing the SDK and restarting Visual Studio for Mac, you can create, build, run, debug and publish .NET Core 3.0 applications. In addition, to enable C# 8 in [.NET Core 3.0 SDK][8], you will need to use the [Project Options][7] in Visual Studio for Mac. In Project Options, go to Build > General > Language Options and set the C# language version to Version 8 as per the image below <img class="alignnone wp-image-225914 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/vsmac-project-options-csharp8.png" alt="vsmac-project-options-csharp8" width="960" height="702" /> When you’re editing C# 8.0 files in Visual Studio for Mac all the existing functionality will work including IntelliSense and Quick Fixes. For more info on what’s new in C# 8.0, head over to the docs [What’s new in C# 8.0][9]. 
## Visual Studio 2019 for Mac version 8.3 Preview 1 For the first preview release of 8.3, we are focusing on .NET Core improvements. We have several exciting features to share with you here. We would love it if you can try this out and give us some feedback regarding these new capabilities. 

### Publish support for .NET Core Console and .NET Standard Library Projects In a previous release we added the ability to 

[publish an ASP.NET Core project to a folder][10]. In this preview we added support to publish .NET Core Console and .NET Standard Library Projects. For more information on how to use this feature, [head over to the docs][10]. Here is a screenshot of this new option when working on a console application. <img class="alignnone wp-image-225916 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/publish-console-app.png" alt="publish-console-app" width="589" height="577" /> After using the Publish to Folder feature, a publish profile is automatically created and becomes available in in the fly-out menu. You can create multiple different profiles, and each will be displayed in the fly-out menu for easy access. 
### ASP.NET Core: Support for launchSettings.json When developing ASP.NET Core applications, you can configure how the application is launched for development purposes using the lauchSettings.json file. For more info on this file, see 

[this section][11] of the environments doc. In launchSettings.json, you can configure the URL for the app to listen on as well as environment variables that are applied on run or debug. With this update, we make it easier for you to collaborate on projects with others that may not be using Visual Studio for Mac. Visual Studio, Visual Studio Code and the dotnet CLI (Command Line Interface) already support this file. 
### ASP.NET Core: File Nesting support In this preview, we are also adding automatic File Nesting for ASP.NET Core projects. The auto file nesting rules applied are the same as what you find in Visual Studio. With file nesting enabled, you can focus better on the files that you edit most frequently. Generated files, and less frequently edited files will be nested under other related files. Check out the screenshot of the Solution Pad showing the nesting behavior. 

<img class="alignnone wp-image-225917 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/filenesting.png" alt="file nesting" width="657" height="532" /> In a future release we will add the ability to disable automatic file nesting, for those that prefer to view the files as a flat list. 
### Download and try today If you haven’t already, please 

[download and try out the 8.2 release today][1]! We hope that this release will allow you to develop your applications more efficiently and that it will give you a better experience overall. We will continue our work on improving the other code editors in the IDE as well as the features we planned on our [roadmap][5]. We would also love for you to [download and try out the 8.3 Preview][2]. If you run into any issues with the 8.2, or the 8.3 Preview release, please use the [Report a Problem][6] feature in the IDE. <img class="alignnone wp-image-225918 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/report-a-problem-ctx-menu.png" alt="report a problem context menu" width="368" height="318" /> Finally, make sure to follow us on Twitter at [@VisualStudioMac][12] and reach out to the team. We look forward to hearing from you. Alternatively, you can head over to [Visual Studio Developer Community][13] to track your issues, [suggest a feature][14], ask questions, and find answers from others. We use your feedback to continue to improve Visual Studio for Mac 2019, so thank you again on behalf of our entire team. <p style="text-align: center">
  <a class="cta_button_link x-hidden-focus" style="text-transform: titlecase;background-color: #5c2d91;color: white;padding: 10px;margin: 10px 0;text-decoration: none" href="https://visualstudio.microsoft.com/vs/mac/" target="_blank" rel="noopener noreferrer">Download</a>
</p>

 [1]: https://visualstudio.microsoft.com/vs/mac/
 [2]: https://aka.ms/vs4mac-preview
 [3]: https://docs.microsoft.com/en-us/visualstudio/mac/update?view=vsmac-2019
 [4]: https://docs.microsoft.com/en-us/visualstudio/releasenotes/vs2017-mac-relnotes
 [5]: https://docs.microsoft.com/en-us/visualstudio/productinfo/mac-roadmap
 [6]: https://docs.microsoft.com/en-us/visualstudio/mac/report-a-problem?view=vsmac-2019
 [7]: https://docs.microsoft.com/en-us/visualstudio/mac/managing-solutions-and-project-properties?view=vsmac-2019
 [8]: https://dotnet.microsoft.com/download/dotnet-core/3.0
 [9]: https://docs.microsoft.com/en-us/dotnet/csharp/whats-new/csharp-8
 [10]: https://docs.microsoft.com/en-us/visualstudio/mac/publish-folder?view=vsmac-2019
 [11]: https://docs.microsoft.com/en-us/aspnet/core/fundamentals/environments?view=aspnetcore-2.2#development
 [12]: https://twitter.com/VisualStudioMac
 [13]: https://developercommunity.visualstudio.com/
 [14]: https://developercommunity.visualstudio.com/spaces/41/index.html