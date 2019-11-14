---
ID: 227368
post_title: Refactoring made easy with IntelliCode!
author: Mark Wilson-Thomas
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/refactoring-made-easy-with-intellicode/
published: true
post_date: 2019-09-05 10:00:53
---
Have you ever found yourself refactoring your code and making the same or similar changes in multiple locations? Maybe you thought about making a regular expression so you could search and replace, but the effort to do that was too great? Eventually you probably resigned yourself to the time-intensive, error prone task of going through the code manually. What if your developer tools could track your edits and learn about the repeatable changes you were making? After only a couple of examples they would spot you doing something repetitive and offer to take the remaining actions for you? With [Visual Studio 2019 version 16.3 Preview 3][1] we are happy to announce that refactorings can now be enhanced by IntelliCode. IntelliCode spots repetition quickly and suggests other places in your code where you might want to apply that same change, right in your IDE: [video poster="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2018/08/vsfeaturemed.png" width="2744" height="1780" mp4="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/intellicode-refactorings.mp4" autoplay="true" preload="auto"][/video] 
###    

### Try it now Refactoring is a preview feature of IntelliCode, so when you get 

[Visual Studio 2019 version 16.3 Preview 3][1]  it will be off by default. Visit the Tools-Options page, IntelliCode General tab, Preview features area, and switch C# refactorings to “Enabled” to turn it on. Once you change this setting, close any files you may have open, then restart Visual Studio: <img class="alignnone wp-image-226306 size-large" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/refactorings-toolsoptions-1024x660.png" alt="How to turn on the refactorings feature in tools-options" width="640" height="413" /> 
### 

<h3 style="text-align: left">
  How it works
</h3> Under the hood, IntelliCode looks at each of your edits as you type. It uses 

[PROSE][2] (PROgram Synthesis by Example) to synthesize generalized edit scripts that can take your code from the “before editing” state to the “after”. When IntelliCode discovers that it can apply one of these scripts elsewhere in your code (which can be based on as few as 2 examples in your code), we let you know via the Visual Studio lightbulb in the margin or when hovering the affected code, and through green “squiggles”. The lightbulb offers actions to apply the refactorings for you. The underlying technology is similar to the [Excel’s Flash Fill feature][3] and is described in [this research paper][4]. More details will be presented at the upcoming [OOPSLA 2019 conference][5]. This isn’t just tracking text changes – IntelliCode is aware of the syntactic structure of your code. This syntactic awareness allows it to detect cases where the variable names in your refactoring examples differ but the essential structure of the change is the same: <img class="alignnone wp-image-226305 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/refactorings-illustrated.png" alt="Illustration showing how IntelliCode can detect patterns syntactically and offer suggestions" width="1023" height="312" /> If you don’t like a suggested change you can select the ignore option on the lightbulb, and we won’t bother you about that detected pattern again unless you recreate it. 
### Let us know what you think! We would love to hear about your experiences as you try this new feature. Good or bad, they will help us improve. Please raise issues and comments via 

[Visual Studio “report a problem”][6] .  We’re interested to hear feedback about the recommendations themselves, the performance of the feature, or any capabilities you might be missing. When sending your feedback it would be really useful if you can share details of what was detected and what sort of edits you were making; we’ll follow up.

 [1]: https://visualstudio.microsoft.com/vs/preview/
 [2]: https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fmicrosoft.github.io%2Fprose%2F&data=02%7C01%7CMark.Wilson-Thomas%40microsoft.com%7Ccdb56ee2af63435d211b08d728b7d38b%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637022642299089700&sdata=HlNZ43YNaRARxWWWg7JmKYoNxpzkTHct7Ainp%2FuMd5E%3D&reserved=0
 [3]: https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fwww.microsoft.com%2Fen-us%2Fresearch%2Fblog%2Fflash-fill-gives-excel-smart-charge%2F&data=02%7C01%7CMark.Wilson-Thomas%40microsoft.com%7Ccdb56ee2af63435d211b08d728b7d38b%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637022642299089700&sdata=4Fe6vtMKRjyQuFdR7KYz4pPPHE7T1yK8YqM1lPwpKYk%3D&reserved=0
 [4]: http://aka.ms/repetitive-edits
 [5]: https://2019.splashcon.org/details/splash-2019-oopsla/27/On-the-Fly-Synthesis-of-Edit-Suggestions
 [6]: https://docs.microsoft.com/visualstudio/ide/how-to-report-a-problem-with-visual-studio?view=vs-2019