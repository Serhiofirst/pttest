---
ID: 226422
post_title: Java on Visual Studio Code July Update
author: Xiaokai He
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/java-on-visual-studio-code-july-update/
published: true
post_date: 2019-07-22 10:00:47
---
Welcome to the July update of Java on Visual Studio Code! In this update, we’d like to share a couple new refactoring features, semantic selection as well as some other enhancements we delivered during last few weeks. 
### Refactoring

##### Trigger `rename` after `extract to variable/constant/method` After performing 

`extract to variable/constant/method` refactoring, more often than not, we would like to assign the result with a meaningful name. With this feature, you won't need to perform a separate `rename` action anymore, all are streamlined in the single refactoring step. <img class="alignnone size-full wp-image-225887" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/extract-rename.gif" alt="" width="1024" height="768" /> 
##### Convert a local variable to a field.

`Extract to field` is also a very popular refactor. When selecting an expression, you can now use `extract to field`. <img class="alignnone size-full wp-image-225888" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/extract-field.gif" alt="" width="1024" height="768" /> When selecting a variable declaration, it will`convert the variable to field`. <img class="alignnone size-full wp-image-225889" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/convert-field.gif" alt="" width="1024" height="768" /> 
### Support for semantic selection

[Smart Selection][1] (a.k.a. Semantic Selection) is the new feature added by VS Code and now it understands Java code as well. With that, you are able to expand or shrink the selection range corresponding to the semantic info of the caret position in your code. 
*   To expand the selection, use \`Shift + Alt + →\`  on Windows, and \`Ctrl + Shift + Command + →\` on Mac
*   To shrink the selection, use \`Shift + Alt + ←\` on Windows and \`Ctrl + Shift + Command + ←\` on Mac

<img class="alignnone size-full wp-image-225896" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/java.smart_.selection.gif" alt="" width="1024" height="768" /> 
### Other enhancements

##### Maven

*   Maven projects use the latest Execution Environment when `source/target` is not yet supported.
*   For users who don't have Maven installed locally, `mvn` can not be found to create a Maven project from archetypes. Maven extension now embeds a *global* maven wrapper in the extension, which serves as a fallback if no `mvn` or project-level `mvnw` found.
*   Support to select archetype version during Maven project creation.
*   Refresh explorer when config `maven.pomfile.globPattern` changes.

##### Gradle

*   Added additional Gradle preferences. 
    *   `java.import.gradle.arguments`: arguments to pass to Gradle
    *   `java.import.gradle.jvmArguments`: JVM arguments to pass to Gradle
    *   `java.import.gradle.home`: setting for `GRADLE_HOME`

##### Checkstyle

*   Support loading CheckStyle Configuration via Http URL.

### Sign up {#signup} If you'd like to follow the latest of Java on VS Code, please provide your email with us using the form below. We will send out updates and tips every couple weeks and invite you to test our unreleased feature and provide feedback early on. 

<div data-form-block-id="a98bf458-e066-e911-a96e-000d3a340154">
</div>

<div id="dgCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU">
</div> (function (id, f, t, ws, ms_tr_il_08, ms_tr_il_w_01) { var tr = function (cb) { var count = 0; var callback = function () { if (count == 0) { count++; if (w) { w.w(id, t, cb); } } }; var ts = document.createElement('script'); ts.src = ws; ts.type = 'text/javascript'; ts.onload = callback; ts.onreadystatechange = function () { if (this.readyState == 'complete' || this.readyState == 'loaded') { callback(); } }; var head = document.getElementsByTagName('head')[0]; head.appendChild(ts); }; if (typeof ms_tr_il_08 === 'function') { if (ms_tr_il_w_01 === null) { tr(function() { ms_tr_il_08(id, f, t); }); } else { ms_tr_il_w_01.w(id, t, function(websiteVisitedParams) { ms_tr_il_08(id, f, t, websiteVisitedParams); }); } } else { tr(); }})('gCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/f', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t/w', typeof ms_tr_il_08 === "undefined" ? null : ms_tr_il_08, typeof ms_tr_il_w_01 === "undefined" ? null : ms_tr_il_w_01); 

### Try it out Please don’t hesitate to give it a try! Your feedback and suggestions are very important to us and will help shape our product in future. 

*   Learn more about <a href="https://code.visualstudio.com/docs/languages/java" target="_blank" rel="noopener noreferrer">Java on Visual Studio Code</a>.
*   Explore our step by step <a href="https://code.visualstudio.com/docs/java/java-tutorial" target="_blank" rel="noopener noreferrer">Java Tutorials on Visual Studio Code</a>.

 [1]: https://code.visualstudio.com/updates/v1_33#_smart-select-api