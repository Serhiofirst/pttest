---
ID: 227370
post_title: >
  Re-imagining collaboration for Visual
  Studio with Live Share app casting and
  contacts
author: Pierre Crutchfield
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/re-imagining-collaboration-for-visual-studio-with-live-share-app-casting-and-contacts/
published: true
post_date: 2019-11-06 11:40:00
---
The power of Visual Studio for desktop and mobile development is unmatched in the industry, and we wanted to ensure that the best in class also had the best collaboration story. Live Share is reimagining this collaboration story by reducing the barriers to collaboration, increasing the fidelity of the collaboration experience while building desktop apps, and enhancing this workflow**.** One of the barriers to collaboration for Visual Studio desktop, mobile and console application development was the inability to effectively share your progress while working on an app with your peer. With the VS16.4 release you will now be able to **share your application from within a collaboration session**.  With the cumbersome process of creating and sharing links to start a collaboration session. collaboration did not feel as intuitive. To solve this problem and make collaboration as low-touch as possible, we now have **contacts in Live Share** that are auto-populated with your recent and contextual collaborators, who can be directly invited to a collaboration session. With all of these new changes, we have also enhanced the interactiveness of a Live Share session with in-built audio calling. <img class="alignnone size-medium wp-image-227364 aligncenter" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/App-casting-1-e1573069121140-253x300.png" alt="" width="253" height="300" />   Application casting with contacts can enhance your collaboration workflow, whether it is for your scheduled pairing session, or for debugging a bug with someone with expertise on your team. You don’t need to lose the comfort of your IDE to make progress on blockers in your code. We know that good code takes multiple eyes on it, and with direct invitations to your contacts you easily collaborate with your team. 
# Getting started with app casting and contacts To use Live Share with app casting and add contacts, make sure you have 

**Visual Studio 16.4 or higher. **Once you have this version of Visual Studio, your Live Share extension will come with app casting when you choose to be an insider. To become an **Insider**, go to: *Tools > Options > Live Share > General > Features* and set it to *Insiders*, as seen in the screenshot below. <img class="aligncenter wp-image-227369 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/screen-shot-insiders-1.png" alt="" width="1397" height="929" /> With Insiders enabled, you will receive all the coolest new features of Live Share. Live Share is now enabled with not just app casting and contacts, but also **VS Live Share Audio. **You can jump on a quick call from within a Live Share session without context switching to any other application, thereby extending  your coding productivity time. 
# Directly invite your peers Contacts will appear automatically once you are an Insider under your contacts pane and are under two categories, 

1.  ** Recent Contacts** These are developers you have previously collaborated with using Live Share. In practice, most developers frequently collaborate with the same people, and therefore, the recent list enables a more repeatable means of working with your team/classroom/etc. 

<ol start="2">
  <li>
    <strong> Suggested Contacts</strong>
  </li>
</ol> These are developers that have contributed to your currently open project within the last 30 days. In practice, these are the folks you are likely to want to collaborate with, and therefore, we suggest them in order to make it easier to get started. All your contacts can be invited directly to a Live Share session from within your editor. They'll get a toast notification that gives them the option to join the session or not. This removes the need to exchange session URLs entirely. 

<img class="alignnone size-full" src="https://user-images.githubusercontent.com/51928518/68322800-f386e180-0078-11ea-9e55-0a2ae4174a97.gif" width="1620" height="1080" /> 
# Share your status With contacts, comes the ability to signal your availability for collaboration. Live Share contacts allow you to set your status to 

*Available*, *Do Not Disturb*, *Away* or *Offline. *The idea is to provide you the ability to choose the level of interaction you would like to have with your peers without the need to context switch. Its not only easy to directly invite contacts now, but also to let them know that you are not available to collaborate. You can read up more on how contacts and statuses work [here.][1] 
# Just hit F5 To share the desktop app, you are working on with your peer from within a Live Share session, just start a 

**debug session with F5** . The screenshot below shows an Expense Reporting WPF application being worked on during a Live Share session. <img class="alignnone size-full wp-image-227370" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/screen-shot-app-casting.png" alt="" width="2256" height="1504" /> When the host of the session presses f5 to start a debugging session, the app auto launches, and the guest can view the application on their side as well. All participants in the session can interact with the application (and  ) and modify it together without committing any changes . App casting currently works for **UWP, WinForms, Win32 C++ apps, C++ and CMake console apps** with many more to come! 
# Call from within your IDE Now you have app casting working and can share your entire working picture with your peer, but sometimes you really need to talk over the fine details. For this, Live Share has in-built audio calling from within your session! The ability to do an audio call from within your IDE allows you to be productive without context switching out of your focus mode while developing. 

<img class="alignnone size-full" src="https://user-images.githubusercontent.com/51928518/67993303-759c8380-fbfd-11e9-920b-c2325436c564.gif" width="1004" height="832" /> 
# Let us know what you think! With app casting your debugging sessions can be a powerful place to do real-time collaboration and make progress on hard bugs. With direct invitations and status sharing with contacts you now have a new ease to your collaboration process. We love hearing from you, so tell us what you think about this new feature, and how else you plan to use it alongside audio calling, by leaving feedback 

[here.][2] You can follow Live Share’s newest offerings through our GitHub [release notes][3], and file for feature request<a name="_GoBack"></a>s to let us know what you would like to see us offer next.

 [1]: https://docs.microsoft.com/en-us/visualstudio/liveshare/reference/contacts
 [2]: https://www.surveymonkey.com/r/JNRRJPX
 [3]: https://github.com/MicrosoftDocs/live-share/releases