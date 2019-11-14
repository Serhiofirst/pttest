---
ID: 226421
post_title: >
  Checklist for writing great Visual
  Studio extensions
author: Mads Kristensen
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/checklist-for-writing-great-visual-studio-extensions/
published: true
post_date: 2019-07-11 08:00:35
---
Great Visual Studio extensions share a few key features that sets them apart from the rest. They look and feel well crafted, are performant and reliable, do what they advertise to perfection, and blend in naturally among Visual Studio’s own features. To make it easier to write great extensions, we’ve worked with the extensibility community to come up with a simple checklist to follow. There’s even a [GitHub issue template][1] you can use so you remember to go through the checklist. <img class="alignnone wp-image-225862 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/VS-extensibility-checklist-small.png" alt="A .vsixmanifest file showing best practices" width="1222" height="499" /> 
## Rules The following list is in no specific order. Remember to complete all items for best results. 

### Rule 1: Adhere to threading rules Add the 

[Microsoft.VisualStudio.SDK.Analyzers][2] NuGet package to your VSIX project. This will help you discover and fix common violations of best practices regarding threading. 
### Rule 2: Add high-quality icon All extensions should have an icon associated with it. Make sure the icon is a high-quality .png file with the size 

**128x128** pixels in 96 DPI or more. After adding the icon to your VSIX project, register it in the .vsixmanifest file as both the Icon and Preview image. The Visual Studio Marketplace makes use of the larger icon and it will get resized dynamically when shown inside Visual Studio. 
### Rule 3: Name and description Studies show that users are more likely to install extensions with short and descriptive names and accurate descriptions. Make sure the name reflects the essence of what the extension does. The description in the .vsixmanifest file should set expectations as to what the extension does. So, a brief mention of what problems it solves and what main features it has are key. 

### Rule 4: Write good Marketplace description This is one of the most important things you should do to make your extension successful. A good description consists of: 

*   Screenshots/animated GIFs of the UI added by the extension
*   Detailed description of the individual features
*   Links to more details if applicable

### Rule 5: Add license The license is visible on the Marketplace, in the VSIX installer and in the Extensions Manager dialog. Always specify a license to set the expectations for the users. Consider using 

[choosealicense.com][3] to help find the right license for you. The reason for this rule is to remove any ambiguity, which is important for many Visual Studio users. 
### Rule 6: Add privacy notice If the extension collects data such as telemetry or in any other way communicates with a remote endpoint, add a note about it in the description. 

### Rule 7: Use KnownMonikers when possible Visual Studio ships with thousands of icons which are available in the 

[KnownMonikers][4] collection. When adding icons to command buttons, see if you can use the existing KnownMonikers icons since they are part of a design language familiar to the Visual Studio users. Here's a full [list of KnownMonikers][5] and grab the [KnownMonikers Explorer][6] extension to find the right one for your scenarios. 
### Rule 8: Make it feel native to VS Follow the same design patterns and principles that Visual Studio itself uses. This makes the extension feel natural to the users. It also reduces distractions caused by poorly designed UI. Make sure that all buttons, menus, toolbars and tool windows are only visible by default when the user is in the right context to use them. There are some rules of thumb to follow: 

*   Don't ever add a new top-level menu (next to File, Edit, etc.)
*   No buttons, menus and toolbars should be visible in contexts they don't apply to
*   If [auto load][7] is necessary (it probably isn't), do it as late as possible.
*   Use [VisibilityConstraints][8] to toggle visibility of commands instead of relying on auto load

### Rule 9: Use proper version ranges It can be tempting to support versions of Visual Studio all the way back to Visual Studio 2010 to ensure that everyone can use your new extension. The problem with that is that by doing so, it is no longer possible to use any APIs introduced later than that minimum version the extension supports. Often, those new APIs are important and help improve performance and reliability of both your extension as well as Visual Studio itself. Here are our recommendations for deciding what versions of Visual Studio to support: 

*   Support only the previous and current version of Visual Studio - don't support older versions if possible
*   Don't specify an open-ended version range. E.g. [16.0,). Learn more about [version ranges][9].

## Your thoughts What do you think of this checklist? Do you agree with the rules? Please let us know your thoughts in the comments below or on the 

[GitHub repo for the checklist][10]. I hope this makes it a little easier to give your extensions that little extra something that sets it apart from the rest.

 [1]: https://gist.github.com/madskristensen/7310c0d61694e323f4deeb5a70f35fec#file-vsix-issue-template-md
 [2]: https://www.nuget.org/packages/Microsoft.VisualStudio.SDK.Analyzers/
 [3]: https://choosealicense.com/
 [4]: https://msdn.microsoft.com/en-US/library/mt628927.aspx
 [5]: http://glyphlist.azurewebsites.net/knownmonikers/
 [6]: https://marketplace.visualstudio.com/items?itemName=MadsKristensen.knownmonikersexplorer
 [7]: https://github.com/microsoft/VSSDK-Extensibility-Samples/tree/master/AsyncPackageMigration
 [8]: https://github.com/Microsoft/VSSDK-Extensibility-Samples/tree/master/VisibilityConstraints
 [9]: https://devblogs.microsoft.com/visualstudio/visual-studio-extensions-and-version-ranges-demystified/
 [10]: https://gist.github.com/madskristensen/7310c0d61694e323f4deeb5a70f35fec