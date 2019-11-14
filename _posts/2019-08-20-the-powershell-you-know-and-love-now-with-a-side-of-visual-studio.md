---
ID: 227361
post_title: >
  The PowerShell you know and love now
  with a side of Visual Studio
author: Ruben Rios
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/the-powershell-you-know-and-love-now-with-a-side-of-visual-studio/
published: true
post_date: 2019-08-20 08:00:33
---
While we know that many of you enjoy, and rely on the Visual Studio Command Prompt, some of you told us that you [would prefer to have a PowerShell][1] version of the tool. We are happy to share that in Visual Studio 2019 version 16.2, we added a new Developer PowerShell! 
## Using the new Developer PowerShell We also added two new menu entries, providing quick access to not just the 

**Developer PowerShell,** but also for the **Developer Command Prompt**. These menu entries are located under **Tools** > **Command Line**. <img class="alignnone wp-image-226140" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/c-users-rurios-appdata-local-microsoft-windows-in-6.jpeg" alt="C:\Users\rurios\AppData\Local\Microsoft\Windows\INetCache\Content.MSO\7DF5E1ED.tmp" width="700" height="489" /> Also, you can access the Developer Command Prompt and Developer PowerShell via the search (Ctrl +Q): <img class="alignnone wp-image-226143" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/word-image-15.png" alt="" width="650" height="189" /> Selecting either of these tools, will launch them in their respective external windows, and with all the predefined goodness (e.g. preset PATHs and environment variables) you already rely on. Opening them from Visual Studio automatically adjust their directories based on current solution or folder’s location. Additionally, If no solution or folder is open at the time of invocation, their directories are set based on the “Projects location” setting. This setting is located under **Tools > Options > Locations**. <img class="wp-image-226144" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/word-image-16.png" /> 
## 

## 

## Try it out and let us know what you think! We’d love to know how it fits your workflow. Please reach out if you have any suggestions or comments around how we could further improve the experience. Send us your feedback via the 

[Developer Community][2] portal or via the **Help > Send Feedback** feature inside Visual Studio.

 [1]: https://twitter.com/shanselman/status/953749597620457472
 [2]: https://developercommunity.visualstudio.com/spaces/8/index.html