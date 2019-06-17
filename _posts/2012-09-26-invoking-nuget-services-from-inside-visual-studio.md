---
ID: 60
post_title: >
  Invoking NuGet Services from inside
  Visual Studio
author: Luan Nguyen
post_excerpt: ""
layout: post
permalink: >
  http://devblogs.microsoft.com/nuget/invoking-nuget-services-from-inside-visual-studio/
published: true
post_date: 2012-09-26 00:00:00
---
One of the best kept secrets of the NuGet extension is that besides the UI that everyone has become familiar with, it also exports some useful services, via [MEF][1], which allow other components in VS to interact with NuGet. These include installing packages, uninstalling packages and querying for installed packages.

Over the past year, the NuGet team has received many inquiries from various teams inside and outside Microsoft asking us how to perform such tasks from their components. We have solidified the guidance over time and wanted to share it broadly.

As of the current version (2.0), NuGet exports six interfaces/services via MEF, all of which reside in the **NuGet.VisualStudio** namespace in the **NuGet.VisualStudio.dll** assembly:

*   **IVsPackageInstaller** - Contains methods to install NuGet packages into projects.

*   **IVsPackageInstallerEvents** - Offers events which raise when packages are installed and uninstalled in the current solution.

*   **IVsPackageInstallerServices** - Contains a method to retrieve installed packages in the current solution, as well as methods to check if a specified package Id is installed in a project.

*   **IVsPackageUninstaller** - Contains methods to uninstall NuGet packages from projects.

*   **IConsoleInitializer** - Trigger eager initialization of the NuGet Package Manager Console.

*   **IVsTemplateWizard** - This interface is designed for project/item templates to include pre-installed packages, and is *not* meant to be invoked from code.

Here I will not discuss the detailed APIs in each of the interfaces. You can easily explore those for yourself in the Object Browser window.

Instead I will show you a step-by-step guide on how to reference the interfaces and use them in your code.

1.  #### First, install the **NuGet.VisualStudio** nuget package into your project
    
    The **[NuGet.VisualStudio][2]** package contains the NuGet.VisualStudio.dll assembly which includes all the above interfaces.  
      
    When installed, the package will automatically set the **Embed Interop Types** property of the assembly reference to **True**. The reason it does so is to make your code resilient against version changes when users update to newer versions of NuGet.  
      
    For the same reason, you must NOT use any other types besides the above interfaces in your code. You must NOT reference any other NuGet assemblies either, including **NuGet.Core.dll**.  
      
    ![Embed Interop Types set to True][3]  
      
    

2.  #### Obtain the services
    
    With the package installed, you are ready to obtain those services from your code. Because they are exported as MEF contracts, you can import them either via MEF's Import attribute, or through the [IComponentModel service][4] in code. Here's a sample code snippet:  
      
    `var componentModel = (IComponentModel)GetService(typeof(SComponentModel));`  
    `IVsPackageInstallerServices installerServices = componentModel.GetService<IVsPackageInstallerServices>();`  
    `var installedPackages = installerServices.GetInstalledPackages();`

So there you have it. If you find yourself needing to do something that the above services do not provide, feel free to open a discussion on the [NuGet discussions board][5].

 [1]: http://msdn.microsoft.com/en-us/library/dd460648.aspx "MEF"
 [2]: https://nuget.org/packages/NuGet.VisualStudio "NuGet.VisualStudio package"
 [3]: https://devblogs.microsoft.com/nuget/wp-content/uploads/sites/49/2019/05/embedinteroptypes.png
 [4]: http://msdn.microsoft.com/en-us/library/microsoft.visualstudio.componentmodelhost.icomponentmodel.aspx "IComponentModel interface"
 [5]: http://nuget.codeplex.com/discussions/topics/5362/general "NuGet Discussions Board"