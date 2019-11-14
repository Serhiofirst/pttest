---
ID: 226879
post_title: >
  Update Visual Studio for Mac for an
  improved Unity experience!
author: Pierre Crutchfield
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/update-visual-studio-for-mac-for-an-improved-unity-experience/
published: true
post_date: 2019-10-24 10:00:29
---
<img class="aligncenter wp-image-226880 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/Picture1.png" alt="glasses focused on Visual Studio for Mac and Unity on a computer" width="974" height="647" /> The past year has been an exciting one for Unity developers. Unity is the leading real-time 3D creation platform. It's rooted in game development and expanding into other industries, too. Unity Reflect enables developers to view BIM (Building Information Modeling) data in real-time. Did you know that over 60% of AR/VR content is created with Unity? Likewise, there were also many other innovations for film, automotive, and marketing announced. With all that excitement, you may have missed the debugging improvements and productivity features we've made to Visual Studio for Mac. 
## Update for better debugging on Mac Earlier this month we 

[talked about the New Editor in Visual Studio for Mac][1] and the shared language services with Visual Studio. That brings a native experience, new features, and closer parity of experiences. Visual Studio Tools for Unity continues that theme by sharing the debugger experience for Unity projects between the two IDEs. This means if you're working on a Mac, you'll get an improved experience from the enhancements we made on Windows over previous years. We’re already [hearing great feedback from developers on these improvements][2]. That's not all, let’s look at the other improvements we've made to Visual Studio for Mac. 
## Easily follow best practices and focus on what matters I’m excited to share that Visual Studio for Mac and Visual Studio now have diagnostics unique to Unity projects. To begin, we’ve started with over a dozen Unity-specific scenarios where both IDEs recognize and offer informational suggestions or refactoring options. Even better, the IDE suppresses general C# diagnostics that don’t apply to Unity projects. For example, it will no longer 

[recommend that you change your [SerializeField] members to readonly][3] and break Unity Inspector links. This means you’ll find less noise in your error list, allowing you to focus on what really matters – scripting your games. To further improve on this, we plan to partner with you and the rest of the community by open sourcing these diagnostics. Together, we’ll improve how the IDE impacts your productivity and best practices. <img class="aligncenter wp-image-226881 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/Picture2.png" alt="Visual Studio for Mac showing refactoring of Unity specific diagnostics" width="974" height="593" /> 
## Iterate faster with background-building and more We’re continuing the productivity theme with more quality of life improvements. We noticed that developers don’t always need Visual Studio for Mac to build, which resulted in longer wait times. We made it faster to iterate and debug by reducing the (sometimes) unnecessary work the IDE was doing. In addition, save time with background building using the 

**Automatic refreshing of Unity’s AssetDatabase on save** setting. True by default, this triggers Unity to compile in the background while you’re editing in Visual Studio for Mac. Finally, save some time by using **Attach to Unity and Play** when starting a debug session. This attaches the debugger to Unity and signals for the Editor to Play all in a single step. You can seamlessly iterate on your debugging workflow right from the IDE. <img class="aligncenter wp-image-226883 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/attach-and-play.gif" alt="animated image showing Attach to Unity and Play from Visual Studio for Mac" width="1793" height="1080" /> 
## Ready for a more reliable debugger and productive scripting experience? Now is a great time to 

[update to the latest version of Visual Studio for Mac][4] to take advantage of all the improvements and time-saving productivity features for Unity projects. We’re continuing improvements for Visual Studio for Mac by listening to your feedback and sharing code between the IDEs. If you’d like to help make these tools better, share your feedback and report issues on [Developer Community][5]. Be sure to follow [@VisualStudioMac][6] for the latest news and updates!

 [1]: https://devblogs.microsoft.com/visualstudio/visual-studio-for-mac-top-features-of-the-new-editor/
 [2]: https://twitter.com/jmillerdev/status/1178718520219258880
 [3]: https://forum.unity.com/threads/visual-studio-ide0044-make-field-readonly.587848/
 [4]: https://docs.microsoft.com/en-us/visualstudio/mac/update?view=vsmac-2019
 [5]: https://developercommunity.visualstudio.com/spaces/41/index.html
 [6]: https://twitter.com/VisualStudioMac