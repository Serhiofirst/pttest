---
ID: 226418
post_title: Java on Visual Studio Code June Update
author: Xiaokai He
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/java-on-visual-studio-code-june-update/
published: true
post_date: 2019-06-24 10:00:17
---
Welcome to the June update of Java on Visual Studio Code! Earlier this month, we shared our new [Java Installer for Visual Studio Code][1], which aims to help new Java developers to get their environment ready and start coding in just a few clicks. In this update, we’d like to share a couple new features and enhancements delivered during last few weeks. 
### More code actions Developers need refactoring and code actions to achieve high productivity, so we're bringing more of those features to you. 

##### Enhanced “Generate getters and setters” In addition to bulk generate getters and setters for all member variables, if the class has more than one field, the source action will also prompt a quick pick box which allows you to select the target fields to generate the accessor methods. 

<img class="alignnone size-full wp-image-225773" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/advancedGetterSetter.gif" alt="" width="1024" height="768" /> The source action is also aware of the *java.codeGeneration.generateComments* preference and will use it to decide whether to generate comments for getter and setter methods. 
##### Generate Delegate Methods This new code action enables generating delegate methods. 

<img class="alignnone size-full wp-image-225774" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/generateDelegateMethods.gif" alt="" width="1024" height="768" /> 
##### Generate Constructor This source action helps adding constructor from super class. 

<img class="alignnone size-full wp-image-225756" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/generate-constructor.gif" alt="" width="1024" height="768" /> 
##### Assign parameter to new field This source action assigns parameter to new field for unused constructor parameter(s). 

#### <img class="alignnone size-full wp-image-225757" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/assign-to-field.gif" alt="" width="638" height="280" />

### Performance improvements A set of changes have been made to further improve performance of Java in Visual Studio Code, including a fix for I/O issue on Windows platform, reducing memory footprint for large projects with deep modules and batch project imports. VS Code is a lightweight editor and we'd like to make sure it still feels just like an editor when despite more and more features being added to it. 

### Debugger updates Debugging is the most frequent used feature second only to code editing. We'd like you to enjoy debugging Java in Visual Studio Code. 

##### Show more meaningful value in variable window and hover tool-tip We're now providing additional detailed information for variables during debug 

*   For the classes that override '*toString*' method, show *toString()* details.
*   For Collection and Map classes, show an additional size=x details.
*   For Entry, show key:value details

<img class="alignnone size-full wp-image-225775" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/tostring-view-for-object-variable.png" alt="" width="1146" height="390" /> 
##### New HCR button To better expose the hot code replace feature and let you control it more explicitly, we've added a new button to the toolbar and provided a new debug setting \`java.debug.settings.hotCodeReplace\` to allow you control how to trigger HCR. Default to \`manual\`. 

*   manual - Click the toolbar to apply the change to running app

<img class="alignnone size-full wp-image-225778" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/hcr-button.png" alt="" width="301" height="40" /> 
*   auto - Automatically apply the changes after compilation. This is the old behavior.
*   never - Never apply the changes See HCR in action 

<img class="alignnone size-full wp-image-225781" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/hcr.gif" alt="" width="1024" height="768" /> 
##### Global setting for selecting debug console While VS Code offers a powerful Debug Console with REPL (Read-Eval-Print Loop) functionality, one major restriction of it is it doesn’t accept input. For those programs which need to take console input, developers need to specify to use integratedTerminal instead of internalConsole in launch.json. 

<pre class="lang:default decode:true">"console": "integratedTerminal"</pre> However, this is not convenient if you need to do it repeatedly. Now we’re introducing a global setting, 

*java.debug.settings.console*. you can use this setting to configure the default debug console so you don’t need to change the launch.json every time. <pre class="lang:default decode:true ">"java.debug.settings.console": "integratedTerminal"</pre>

### Other updates

##### Maven 2 new configs are now available for Maven extension 

1.  *pomfile.globPattern* – specified how the extension search for POM file.
2.  *pomfile.autoUpdateEffectivePOM* – specifies whether to update Effective-POM automatically.

##### Test Runner In recent releases, we’ve added support for a couple additional JUnit5 annotations, such as 

*@Nested* and *@TestFactory*. Test runner will also automatically show the test report after execution now. 
### Sign up {#signup} If you'd like to follow the latest of Java on VS Code, please provide your email with us using the form below. We will send out updates and tips every couple weeks and invite you to test our unreleased feature and provide feedback early on. 

<div data-form-block-id="a98bf458-e066-e911-a96e-000d3a340154">
</div>

<div id="dgCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU">
</div> (function (id, f, t, ws, ms_tr_il_08, ms_tr_il_w_01) { var tr = function (cb) { var count = 0; var callback = function () { if (count == 0) { count++; if (w) { w.w(id, t, cb); } } }; var ts = document.createElement('script'); ts.src = ws; ts.type = 'text/javascript'; ts.onload = callback; ts.onreadystatechange = function () { if (this.readyState == 'complete' || this.readyState == 'loaded') { callback(); } }; var head = document.getElementsByTagName('head')[0]; head.appendChild(ts); }; if (typeof ms_tr_il_08 === 'function') { if (ms_tr_il_w_01 === null) { tr(function() { ms_tr_il_08(id, f, t); }); } else { ms_tr_il_w_01.w(id, t, function(websiteVisitedParams) { ms_tr_il_08(id, f, t, websiteVisitedParams); }); } } else { tr(); }})('gCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/f', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t/w', typeof ms_tr_il_08 === "undefined" ? null : ms_tr_il_08, typeof ms_tr_il_w_01 === "undefined" ? null : ms_tr_il_w_01); 

### Try it out Please don’t hesitate to give it a try! Your feedback and suggestions are very important to us and will help shape our product in future. 

*   Learn more about <a href="https://code.visualstudio.com/docs/languages/java" target="_blank" rel="noopener noreferrer">Java on Visual Studio Code</a>.
*   Explore our step by step <a href="https://code.visualstudio.com/docs/java/java-tutorial" target="_blank" rel="noopener noreferrer">Java Tutorials on Visual Studio Code</a>.

 [1]: https://devblogs.microsoft.com/visualstudio/announcing-visual-studio-code-java-installer/