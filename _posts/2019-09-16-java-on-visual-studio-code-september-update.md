---
ID: 226411
post_title: >
  Java on Visual Studio Code September
  Update
author: Xiaokai He
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/java-on-visual-studio-code-september-update/
published: true
post_date: 2019-09-16 09:30:23
---
Welcome to the September update of Java on Visual Studio Code! There're a lot we've been working on during the summer which we'd like to share with you now. You will see new refactoring and code action features such as move member and class, live linting as well as improvements for Debugger, Test Runner and Maven. We've also improved getting started experience with our new Pack release. 
### Refactoring and Code Actions

##### Move refactoring support The 

**Move** refactoring lets you move packages and classes between the source roots of a project, class members to other classes and inner classes to upper hierarchy levels. For example, you can perform the **move** refactoring on *static method* if it is used more in another class than in its own class. <img class="alignnone size-full wp-image-226449" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/move-static-member.gif" alt="" width="1024" height="768" /> You can also **move** a class to another package. <img class="alignnone size-full wp-image-226448" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/move-file.gif" alt="" width="1024" height="768" /> And **move** inner class to new a new file. 
##### <img class="alignnone size-full wp-image-226447" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/move-inner-type.gif" alt="" width="1024" height="768" />

##### Other new code actions A couple of other code actions and quick fixes are also included in the latest release 

1.  **Invert local variable** lets you change the sense of a Boolean variable to the opposite one.
2.  **Convert lambda to anonymous class** (as we already support Convert to lambda expression).
3.  **Create unresolved types** which covers create simple class/enum/interface/annotation in various scenarios.

### Linting and Checkstyle

<div class="css-1dbjc4n r-xoduu5">
  We<span class="css-901oao css-16my406 r-1qd0xha r-ad9z0x r-bcqeeo r-qvutc0"> now support Live Linting and batch check for Java through <a href="https://marketplace.visualstudio.com/items?itemName=shengchen.vscode-checkstyle">Checkstyle</a> extension</span><span class="css-901oao css-16my406 r-1qd0xha r-ad9z0x r-bcqeeo r-qvutc0"> so you no longer need to save the file one by one to update the check result. </span>
</div>

<div>
</div> See live linting in action. 

<img class="alignnone size-full wp-image-226429" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/LiveLinting.gif" alt="" width="1024" height="768" /> And batch check is now also available. <img class="alignnone size-full wp-image-226430" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/batchcheck.gif" alt="" width="1024" height="768" /> Other improvements in <span class="css-901oao css-16my406 r-1qd0xha r-ad9z0x r-bcqeeo r-qvutc0"><a href="https://marketplace.visualstudio.com/items?itemName=shengchen.vscode-checkstyle">Checkstyle</a> extension include</span> 
1.  Open problems panel when click the status icon in the status bar
2.  Automatically detect potential Checkstyle configuration files when using command to set the configuration

### Debugger One of the changes we've recently made is to use integrated terminal as default debug console. With this change, you no longer need to make specific configuration to allow the console to accept your input. The only drawback of this change is the integrated terminal doesn't support expression evaluation. In order to use this feature, you would now need to change the console to use the Internal Console in 

`launch.json`. <pre class="lang:default decode:true ">"console": "internalConsole"</pre>

<div>
  <div>
    If you'd like to use that setting each time you launch a Java program, you can configure it as a global user setting with <code>java.debug.settings.console</code>.
  </div>
</div>

<div>
</div>

<div>
  In order to make run and debug even easier, another change we've made is to add menu entries to <strong>Run </strong>and <strong>Debug</strong> a Java application when you right click a Java file in file explorer or opened editor.
</div>

<img class="alignnone size-full wp-image-226431" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/DebugContextMenu.png" alt="" width="446" height="227" /> 
### Test Runner More JUnit 5 annotations are now supported by VS Code Java Test Runner. Support JUnit 5 meta-annotations and composed annotations. 

<img class="alignnone size-full wp-image-226433" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/meta-annotation.gif" alt="" width="1530" height="768" /> Support JUnit 5 @TestTemplate. 
### <img class="alignnone size-full wp-image-226434" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/test-template.gif" alt="" width="1024" height="768" />

### Getting Started Experience For developers new to Java or new to VS Code, we're now providing a refreshed Getting Started experience. Once you've installed the 

[Java Extension Pack][1], you can use the command **Java: Getting Started** to get the quick start guide. <img class="alignnone size-full wp-image-226436" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/GettingStarted.png" alt="" width="1358" height="1231" /> The new **Getting Started** view provides a quick start guide as well as tips for code editing and debugging. It also has an FAQ to answer some of the most asked questions. We plan to add more section to it in future. One of the other hurdle for new Java developer is to get the JDK right. For that, we've also upgraded our **Configure Java Runtime** page which now shows the JDK configuration we detect with priority order and allow you to jump to the setting by a simple click. If a working JDK configuration is not detected, this page will be presented automatically, otherwise you can also use the command **Java: Configure Java Runtime** to get there. <img class="alignnone size-full wp-image-226437" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/09/JDK.png" alt="" width="1363" height="971" /> With those new features, we've also released our new version of VS Code Installer for Java. You can try it at <https://aka.ms/vscode-java-installer-win> with improved downloading and installation experience. 
### External contributions As VS Code becomes popular among Java developers, we're getting more and more issues reported. They're very helpful and please keep them coming! In addition, we'd like to express our gratitude for those from the community who spend more time with us to make the product even better. 

*   Contribution from [pi1024e][2]: User face change: say "Do not show again" instead of "Not show again". https://github.com/microsoft/vscode-java-debug/pull/630
*   Contribution from Christian Lutz [thccorni][3]: Typo 'gourpId' in hoverProvider. https://github.com/microsoft/vscode-maven/issues/368 There're also a few pull requests from community currently under review. We'd like to thank all of you to help us build better tool for the Java community. 

### Sign up {#signup} If you'd like to follow the latest of Java on VS Code, please provide your email with us using the form below. We will send out updates and tips every couple weeks and invite you to test our unreleased feature and provide feedback early on. 

<div data-form-block-id="a98bf458-e066-e911-a96e-000d3a340154">
</div>

<div id="dgCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU">
</div> (function (id, f, t, ws, ms_tr_il_08, ms_tr_il_w_01) { var tr = function (cb) { var count = 0; var callback = function () { if (count == 0) { count++; if (w) { w.w(id, t, cb); } } }; var ts = document.createElement('script'); ts.src = ws; ts.type = 'text/javascript'; ts.onload = callback; ts.onreadystatechange = function () { if (this.readyState == 'complete' || this.readyState == 'loaded') { callback(); } }; var head = document.getElementsByTagName('head')[0]; head.appendChild(ts); }; if (typeof ms_tr_il_08 === 'function') { if (ms_tr_il_w_01 === null) { tr(function() { ms_tr_il_08(id, f, t); }); } else { ms_tr_il_w_01.w(id, t, function(websiteVisitedParams) { ms_tr_il_08(id, f, t, websiteVisitedParams); }); } } else { tr(); }})('gCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/f', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t/w', typeof ms_tr_il_08 === "undefined" ? null : ms_tr_il_08, typeof ms_tr_il_w_01 === "undefined" ? null : ms_tr_il_w_01); 

### Try it out Please don’t hesitate to give it a try! Your feedback and suggestions are very important to us and will help shape our product in future. 

*   Learn more about <a href="https://code.visualstudio.com/docs/languages/java" target="_blank" rel="noopener noreferrer">Java on Visual Studio Code</a>.
*   Explore our step by step <a href="https://code.visualstudio.com/docs/java/java-tutorial" target="_blank" rel="noopener noreferrer">Java Tutorials on Visual Studio Code</a>.

 [1]: https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack
 [2]: https://github.com/pi1024e
 [3]: https://github.com/thccorni