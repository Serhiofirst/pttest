---
ID: 227358
post_title: >
  Async loaded .NET projects may impact
  Visual Studio extensions
author: Mads Kristensen
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/async-loaded-net-projects-may-impact-visual-studio-extensions/
published: true
post_date: 2019-08-08 10:43:21
---
In Visual Studio 2019 version 16.3, the CSProj project system (C#/VB non-SDK style) introduces a new way of loading called Partial Load Mode (PLM). After the solution loads, the project system is doing design time builds in the background, leaving the UI responsive and interactive. However, for the time it takes to run the design time build, certain features may not be working as they used to. Extenders, read on. <img class="alignnone size-full wp-image-226072" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/PLM-IntelliSense.png" alt="" width="584" height="124" /> Today, CSProj projects block the UI thread and wait for design time build and Roslyn initialization before firing the project load event. To further reduce solution load time, CSProj will now fire the project load event immediately after evaluation, since that is early enough to display the project tree in Solution Explorer and provide project and source code files to Roslyn. Design time builds will happen on a background thread. This means that IntelliSense, code navigation, and designers will be in the Partial Load Mode after solution load and until the design time build results are ready. Most users will not even notice this happening beyond faster loading solutions. <img class="alignnone size-full wp-image-226073" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/PLM-progress.png" alt="" width="497" height="258" /> This will match the current behavior of .NET SDK-style projects that has had this capability since Visual Studio 2017. Now the experience is consistent between CSProj and SDK-style projects. 
## Breaking change Calls to Roslyn APIs, such as 

*Workspace.CurrentSolution* or *ProjectItem.FileCodeModel*, may return an incomplete code model in PLM because project references are not yet known to Roslyn. You may have to update your extension if it’s calling on the Roslyn API shortly after solution load. Here’s how: 
    var operationProgressStatusService = await this.GetServiceAsync(typeof(SVsOperationProgressStatusService)) as IVsOperationProgressStatusService;
    var stageStatus = operationProgressStatusService.GetStageStatus(CommonOperationProgressStageIds.Intellisense);
    
    await stageStatus.WaitForCompletionAsync(); Learn more in the 

[OperationProgress sample][1]. Editor owners should make an explicit decision regarding delaying the initialization of documents when IntelliSense is in progress. To opt-out of deferring document creation, set the following in the .pkgdef file: 
    [$RootKey$\Editors\<Editor-type-Guid>]
    "DeferUntilIntellisenseIsReady"=dword:00000000 To opt into deferring document creation (this is the current default behavior to avoid breaking compatibility with extensions depending on Roslyn data), set the following in the .pkgdef file: 

    [$RootKey$\Editors\<Editor-type-Guid>]
    "DeferUntilIntellisenseIsReady"=dword:00000001

## Test your extension This change brings a feature currently used by SDK-style projects to the CSProj based ones. As such, it is unlikely going to cause issues for most extensions unless they have different code paths for each of the two project systems. We therefore regard this as low impact for the extension ecosystem, but it could have a big impact on an individual extension. To find out if this change affected your extensions, download Visual Studio 2019 v16.3 Preview 1 today. Then drop a .json file containing the below code into 

**%LocalAppData%\Microsoft\VisualStudio\RemoteSettings\LocalTest\PersistentActions** 
    {
      "ActionPath": "vs\\core\\remotesettings",
      "ActionJson": {
        "FeatureFlags": {
          "CPS.UseOperationProgress": 0,
          "CSProj.PartialLoadMode": 1,
          "Designer.PartialLoadMode": 1,
          "Completion.PartialLoadMode": 1,
          "Roslyn.PartialLoadMode": 1
          }
      },
    
      "TriggerJson": null,
      "MaxWaitTimeSpan": "14.00:00:00",
      "Categories": [
      ]
    } Then restart Visual Studio twice. Yes, twice. This will enable PLM for CSProj based projects. To revert the feature flags change – delete the .json file and restart Visual Studio twice. Disabling PLM is only an option in the initial preview of Visual Studio 2019 v16.3. The option will be removed in a future update.

 [1]: https://github.com/microsoft/VSSDK-Extensibility-Samples/tree/master/OperationProgress