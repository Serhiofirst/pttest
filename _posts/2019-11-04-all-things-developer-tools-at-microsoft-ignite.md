---
ID: 227170
post_title: >
  All Things Developer Tools at Microsoft
  Ignite
author: Anthony Cangialosi
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/all-things-developer-tools-at-microsoft-ignite/
published: true
post_date: 2019-11-04 06:00:01
---
There is a lot of developer goodness happening at Ignite this week. Visual Studio Online is available as a public preview for developers to try cloud hosted development environments with your tool of choice. Visual Studio 2019 version 16.4 Preview 3 and Visual Studio 2019 for Mac version 8.3 Preview 2 just released with tons of new productivity features. There are also a bunch of great sessions that deep dive into all this and much more. 
### Welcome to the family Visual Studio Online Today Visual Studio Online moved to a public preview; providing managed, on-demand development environments for long-term projects, to quickly prototype a new feature, or for quick tasks like reviewing pull requests. 

<span style="font-size: 1rem">You can work with environments from any device using Visual Studio Code, Visual Studio 2019 or the built-in browser-based editor. The features for connecting to a cloud environment from the Visual Studio 2019 IDE are available </span>[in private preview][1]. Read more about the exciting announcement in the [Visual Studio Online blog post][2]. The Visual Studio 2019 IDE can also create and connect to Visual Studio Online environments and take advantage of all the benefits of a cloud powered development environment to build any application. 
*   Get up and running quickly by letting Visual Studio Online install runtimes, SDKs and dev tools
*   Create environments quickly to isolate your work across different projects
*   Spin up extra capacity with a premium environment to gives you the memory and compute to run your toughest workloads
*   Give your teammates a ready to go environment for rich code reviews without tying up your dev box or asking anyone to setup their own environment We’re eager to invite developers that love working in a full IDE to 

[join our private preview][1]. 
### Visual Studio 2019 version 16.4 Preview 3 is here Preview 3 of Visual Studio 2019 version 16.4 is now available. If you aren’t already running the Preview builds you can 

[download][3] and try out the latest side by side with our current version of Visual Studio. Of course, if you already have a Preview installed just click the notification or go to Help menu and click Check for updates. 
#### Speedy code navigation In 16.3 we introduced file search for all languages and semantic 

[code search for C# and VB into the new Search bar][4]. In 16.4 we have rewritten the Find in files tool window to address suggestions and feedback on the most popular search control in the IDE. Performance has been significantly improved and reliability issues that previously led to frustrating hangs have been fixed. We cleaned up the UI and added a few improvements like adding exclusions to a search query. <img class="alignnone size-full wp-image-227172" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/fif.jpg" alt="" width="624" height="567" /> 
#### IntelliSense without Using Directives IntelliSense is indispensable for browsing and finding members of a type but if you’re missing a Using directive you might not find what you need. In 16.4 IntelliSense shows members and types for any assemblies referenced from your project and automatically adds the Using directive to keep your code neat and tidy. 

<img class="alignnone size-full wp-image-227285" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/using.jpg" alt="" width="785" height="313" /> 
#### IntelliCode helps with argument completion IntelliCode saves you time by putting what you’re most likely to use at the top of your IntelliSense completion list. IntelliCode can also provide suggestion for arguments as you type, bringing the most likely arguments to the top of your completion list. Set your cursor on a method and type CTRL+SPACE to give it a try. 

<img class="alignnone size-full wp-image-227283" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/ParameterIntelliCodeRecommendations.png" alt="" width="1286" height="335" /> 
#### Automatically re-train and acquire IntelliCode team models Since we released the ability to create team models trained on your own code last year, we’ve heard feedback that sharing team models through links can be cumbersome and it’s difficult to remember to retrain your models. With our new 

[Azure DevOps task][5] and [ automatic acquisition of models][6], you can set up your pipeline to take care of team model updates and automatically share the model with others working in the same repository. 
#### Refactoring with help from IntelliCode ItelliCode goes beyond smarter IntelliSense. IntelliCode learns from your edits and provides refactoring suggestions for repeated edits as you type. IntelliCode understands the syntactic structure of your changes so suggestions include locations with similar structure but different variables and formatting. These suggestions appear with your other refactoring quick fixes and are available from the CTRL + ”.” shortcut. Remember to enable this early IntelliCode feature from Tools Options. 

<img class="alignnone size-full wp-image-227284" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/RefactoringGif-2.gif" alt="" width="957" height="671" /> 
#### More real estate for code and easier navigation with vertical document tabs We’re excited to include with 16.4 the 

[most popular customer suggestion][7], [vertical document tabs][8]. Real estate for code is a premium in many environments. Vertical document tabs give vertical space to your source code while better utilizing your horizontal screen space. Stretch to bring long file names into view, sort tabs alphabetically and use tab groups to get more code on the screen. <img class="alignnone size-full wp-image-227174" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/VerticalTabs.gif" alt="" width="1280" height="711" /> 
#### XAML code editor pop up, merge resource dictionaries and more In this release there are multiple new features for desktop developers building WPF or UWP applications. One such feature is the ability to open the XAML code editor window separately from the XAML designer using our new “pop up” button next to XAML tab: 

<img class="alignnone size-full wp-image-227286" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/xaml.png" alt="" width="1099" height="672" /> Other features include the ability to easily merge an existing resource dictionary into your application with our new solution explorer command “Merge Resource Dictionary Into Active Window”, the ability to filter Live Visual Tree to “Just My XAML” and more. For a complete list of what’s new for desktop developers see the [release notes][9]. 
#### Audio calls and app sharing for desktop apps in Live Share Real time collaboration with Live Share opens the door for pair programming, rich code reviews, and help from experts even when they are remote. A quick call can often provide more context behind the code. Now the Live share tool window lets you start an audio call with other collaborators in a Live Share session. 

<img class="alignnone size-full wp-image-227282" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/67993303-759c8380-fbfd-11e9-920b-c2325436c564.gif" alt="" width="1004" height="832" /> You can now App Share a desktop and web apps in a Live Share conversation. Start a Live Share conversation with another developer or tester and start debugging. Guests will see the same running app you see on your local machine. They can even interact with the application and trigger breakpoints in the debugger. 
#### Pin Properties in the Debugger Identifying objects by their properties while debugging has just become easier and more discoverable with the new Pinnable Properties tool. In short, hover over a property you want to display in the debugger window of the Watch, Autos, and Locals windows, click that pin icon, and immediately see the information you are looking for at the top of your display! 

<img class="alignnone size-full wp-image-227287" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/Debugger-pinnable-properties.gif" alt="" width="1368" height="598" /> 
### Visual Studio 2019 for Mac version 8.4 Preview 2 Today we're releasing Visual Studio 2019 for Mac version 8.4 Preview 2. This is an exciting release because it adds significant accessibility improvements to the overall IDE as well as support for .NET Core 3.1 Preview and full Blazor (server-side) support. With the latest version you can create, build, debug and run Blazor projects and then deploy your Blazor app directly to Azure without ever leaving the IDE. Learn more about this release on the latest Visual Studio for Mac 

[blog post][10]. 
### Ignite sessions to check out this week The above is just a glimpse of the developer topics that will be covered at Microsoft Ignite this week. Make sure you head on over to 

<https://www.microsoft.com/ignite> to catch the following sessions and more. Times listed are in Eastern Time (ET). <table style="height: 2008px;width: 100%" border="1">
  <tbody>
    <tr style="height: 53px">
      <td style="height: 53px;width: 352px">
        Monday, Nov 4 2:00 PM - 2:45 PM
      </td>
      
      <td style="height: 53px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81274">Empowering every developer to innovate with Microsoft Azure</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Monday, Nov 4 3:15 PM - 4:00 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81607">Increase your .NET productivity with Visual Studio and Visual Studio for Mac</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Tuesday, Nov 5 9:00 AM - 10:15 AM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81591"><strong>Keynote</strong>: App development for everyone with Hanselman and friends</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Tuesday, Nov 5 10:30 AM - 11:15 AM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81612">Visual Studio Online: A look at the future of developer productivity and collaboration</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Tuesday, Nov 5 11:45 AM - 12:30 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81613">Visual Studio Code tips and tricks</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Tuesday, Nov 5 1:00 PM - 1:45 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81599">The now and then of cloud native application in the enterprise using containers</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Tuesday, Nov 5 2:15 PM - 3:00 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81619">Ship it! Build for any platform with Azure Pipelines, and make shipping fun and stress-free</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Tuesday, Nov 5 2:15 PM - 3:00 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81606">Building serverless web applications in Azure</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Tuesday, Nov 5 3:30 PM - 4:15 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81614">Enterprise-grade Node.js on Azure</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Tuesday, Nov 5 4:30 PM - 5:15 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/84134">Being a social developer</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Wednesday, Nov 6 9:15 AM - 10:00 AM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81605">Building enterprise capable serverless applications</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Wednesday, Nov 6 10:30 AM - 11:15 AM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81609">Create amazing web apps with ASP.NET Core</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Wednesday, Nov 6 12:30 PM - 1:45 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81592">.NET platform overview and roadmap</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Wednesday, Nov 6 12:45 PM - 1:30 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81330">Windows App Development Roadmap: Making Sense of WinUI, UWP, Win32, .NET</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Wednesday, Nov 6 2:15 PM - 3:00 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81617">Community powered continuous integration with GitHub Actions</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Thursday, Nov 7 9:15 AM - 10:00 AM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81598">Applying best practices to Azure Kubernetes Service (AKS)</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Thursday, Nov 7 10:30 AM - 11:15 AM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81610">Debugging tips and tricks in Visual Studio 2019</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Thursday, Nov 7 12:45 PM - 1:30 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/79806">Moving the web forward: Microsoft Edge for web developers</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Thursday, Nov 7 1:00 PM - 1:45 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81608">Cloud native applications with .NET Core and Azure Kubernetes Service</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Thursday, Nov 7 2:15 PM - 3:00 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81615">Build Python apps in Azure faster with Visual Studio Code</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Thursday, Nov 7 3:30 PM - 4:15 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81611">Mobile app development reimagined with Xamarin and .NET</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Friday, Nov 8 9:15 AM - 10:00 AM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81593">.NET Microservices with Azure Service Fabric: A real-world perspective</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Friday, Nov 8 10:30 AM - 11:15 AM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81602">Linux based web app development made easy on App Service</a>
      </td>
    </tr>
    
    <tr style="height: 85px">
      <td style="height: 85px;width: 352px">
        Friday, Nov 8 11:45 AM - 12:30 PM
      </td>
      
      <td style="height: 85px;width: 1174.4px">
        <a href="https://myignite.techcommunity.microsoft.com/sessions/81622">Build a highly secure and scalable mobile backend using App Center</a>
      </td>
    </tr>
  </tbody>
</table> If you’re at the event in Orlando this week, be sure to stop by the Development & Architecture Center to chat with our team and catch one of the many theater and lightning talks. There are also hands-on workshops throughout the week for you to experience these technologies first-hand. Thanks, Anthony & the entire Visual Studio team

 [1]: https://vsfutures.azurewebsites.net/
 [2]: http://aka.ms/vsoblog
 [3]: https://visualstudio.microsoft.com/vs/preview/
 [4]: https://devblogs.microsoft.com/visualstudio/code-recent-items-and-template-search-in-visual-studio/
 [5]: http://www.aka.ms/vsic-ci-task
 [6]: http://www.aka.ms/vsic-auto-acquire
 [7]: https://developercommunity.visualstudio.com/search.html?f=&type=question+OR+problem+OR+idea&type=question+OR+problem+OR+idea&c=&redirect=search%2Fsearch&sort=relevance&q=Vertical+tabs
 [8]: https://devblogs.microsoft.com/visualstudio/document-management-improvements-vertical-document-tabs-are-here/
 [9]: https://docs.microsoft.com/en-us/visualstudio/releases/2019/release-notes-preview
 [10]: https://aka.ms/vs4mac-blog