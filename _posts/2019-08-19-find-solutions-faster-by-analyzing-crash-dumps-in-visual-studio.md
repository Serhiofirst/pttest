---
ID: 227362
post_title: >
  Find solutions faster by analyzing crash
  dumps in Visual Studio
author: Mark Downie
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/find-solutions-faster-by-analyzing-crash-dumps-in-visual-studio/
published: true
post_date: 2019-08-19 09:00:07
---
<span>When unexpected crashes occur in your managed application you are often left with little evidence of the issue; capturing and analyzing memory dumps may be your last best option. Thankfully Visual Studio is a great tool for analyzing your apps memory dumps! In this post we show you how easy it is to get important insights from a crash dump, and the steps to resolve the issue using Visual Studio.</span> 
### What is a crash? There are several different things that might be causing your managed application to crash, the most common are typically unhandled exceptions. These occurs where an exception is raised (First Chance Exception), but your code does not handle it (typically using a try-catch code construct). The exception goes up the stack and becomes, what we refer to as, a 

**S*econd Chance Exception*** and crashes your app’s process. **Out of Memory Exceptions**, **Stack Overflow Exceptions** and **Execution Engine Exceptions** also cause crashes. **Stack Overflow Exceptions** and **Out of Memory Exceptions** can occur when your app has insufficient memory space for any function to handle the exception, which again causes the process to crash. 
### Capturing a memory dump Memory dumps are a great diagnostic tool because they are a complete snapshot of what a process is doing at the time the dump is captured. There are several tools available for capturing memory dumps including 

[Visual Studio][1], [ProcDump][2], [DebugDiag][3] and [WinDbg][4]. The relative strength of each tool depends on your environment and the scenario you are investigating (e.g. high CPU, memory leaks, first/second chance exceptions, etc.). In the following example, I use the versatile [**ProcDump** command-line utility from Sysinternals][5] to capture a [full user-mode dump][6] (-ma) when an unhandled exception (-e) occurs (1145 is the process id of my application). <pre class="theme:dark-terminal font-size:16 toolbar:2 lang:default decode:true ">procdump.exe -ma -e 1145</pre> Once the crash occurs ProcDump immediately writes the memory dump to disk (*.dmp). Debugging crashes is made easier with the Visual Studio memory tools, so let me show you how I debug a Stack Overflow Exception in my application, and how the tools navigate me directly to the line of code that caused the problem. 

### Analyzing a crash dump with Visual Studio I can open my memory dump directly in Visual Studio and will be presented with the 

**Dump Summary** page. <img class="alignnone size-full wp-image-226165" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/visual-studio-dump-summary-page.png" alt="Visual Studio - Dump Summary Page" width="1085" height="822" /> The Dump Summary page highlights several pieces of important information from the dump file including the **OS Version** and **CLR Version**. I can also search through a list of the modules that were loaded into memory at the time I captured the memory dump. In this example the **Exception Code** and **Exception Information** state that the problem is *“The thread used up its stack”*. Simply put, we have a stack overflow exception. Knowing the problem is one half of the equation, but I also want to know the root cause of the issue, and this is where I think Visual Studio shines. On the right side of the Dump Summary page, I can choose from several **Actions**, but as this is a managed application, I will select the **Debug with Managed Only** option and Visual Studio immediately drops me onto the thread and code line that caused the stack overflow exception! <img class="alignnone size-full wp-image-226163" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/visual-studio-dump-line-of-code.png" alt="Visual Studio - Crash Dump Exception" width="1800" height="1154" /> I now have a more complete view of the problem, it’s as if I had managed to set a break point at the exact moment of the stack overflow. This also presents me with the opportunity to review my Call Stack (which confirms the issue), review other threads, and even verify the state of any Local variables at that point in time. In this instance Visual Studio is pointing me to a clear error on my definition of the get property. Instead of returning the private variable *m_MyText* I have mistakenly returned the public property *MyText*. This circular reference is the cause of the stack overflow exception. Finding the root cause of the problem may not always be this clear, so you could also collaborate with a colleague directly from the exception by using [Visual Studio Live Share][7]. This gives you the ability to co-debug in real time without teammates needing to set up their environment. <img class="alignnone wp-image-226164 size-medium" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/visual-studio-dump-start-live-share-300x126.png" alt="Visual Studio - Start Live Share Session from an Exception" width="300" height="126" /> 
### Conclusion Over the years Visual Studio has developed first class support for handling and debugging memory dumps. It allows you to consider the impact your code is having during the exact moment of a catastrophic failure. Having the ability to investigate a problem with the same tools used for developing code can help save time determining and providing a solution. Please let us know what you’d like to see next by 

[suggesting feature requests or reporting issues via Developer Community][8].

 [1]: https://visualstudio.microsoft.com/downloads/
 [2]: https://docs.microsoft.com/en-us/sysinternals/downloads/procdump
 [3]: https://www.microsoft.com/en-us/download/details.aspx?id=49924
 [4]: https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/debugger-download-tools
 [5]: https://www.poppastring.com/blog/taking-a-hang-dump-or-crash-dump-with-procdump
 [6]: https://docs.microsoft.com/en-us/windows-hardware/drivers/debugger/user-mode-dump-files#full
 [7]: https://docs.microsoft.com/en-us/visualstudio/liveshare/
 [8]: https://developercommunity.visualstudio.com/spaces/8/index.html