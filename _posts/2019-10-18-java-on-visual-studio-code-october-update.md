---
ID: 226761
post_title: >
  Java on Visual Studio Code October
  Update
author: Xiaokai He
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/java-on-visual-studio-code-october-update/
published: true
post_date: 2019-10-18 09:00:47
---
Welcome to the October update of Java on Visual Studio Code! This month, we're bringing some new features for code navigation, code actions and refactoring, code snippet along with Java 13 support. There're also improvements in debugger, maven, checkstyle and Test Runner. Please checkout and let us know what you think! 
### Code Navigation

##### Go to super implementation

<div>
  <div>
    You can now keep track of class implementations and overriding methods by clicking the <code>Go to Super Implementation</code> link when hover.
  </div>
  
  <div>
  </div>
</div>

<img class="alignnone size-full wp-image-226773" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/Go-to-Super-Implementation.png" alt="" width="784" height="275" /> See the code navigation in action. <img class="alignnone size-full wp-image-226811" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/navigateToSuperImplementation.gif" alt="" width="1025" height="768" /> 
### Code Actions A couple new code actions have been added to VS Code for Java recently. 

##### Create non existing package Now when your package name doesn't match the folder name, you have the options to either change the package name in your code, or move the folder in file system (even when the destination folder doesn't exist yet). 

<img class="alignnone size-full wp-image-226815" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/createNonExistingPackage.gif" alt="" width="1024" height="768" /> 
##### Add quick fix for non accessible references This quick fix helps you resolve non accessible reference 

<img class="alignnone size-full wp-image-226810" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/non-access.gif" alt="" width="1024" height="768" /> 
##### Automatically trigger auto-import on paste If you paste blocks of code that contain references to classes or static methods and fields that are not yet imported, VS Code now can automatically add missing imports. The new feature is enabled via the 

`java.actionsOnPaste.organizeImports` preference in VS Code preferences. If `true` (the default value), triggers "Organize imports" when Java code is pasted into an empty file. <img class="alignnone size-full wp-image-226847" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/autoImportOnPaste.gif" alt="" width="1024" height="768" /> 
### Refactoring

##### Inline refactoring The 

<span class="keyword">Inline</span> refactoring lets you reverse the refactoring for a local variable, method, and constant. <img class="alignnone size-full wp-image-226814" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/Inline.gif" alt="" width="1024" height="768" /> 
##### Convert for-loop to for-each loop The enhanced for-loop is a popular feature. Its simple structure allows you to simplify code by presenting for-loops that visit each element of an array/collection without explicitly expressing how one goes from element to element. 

<img class="alignnone size-full wp-image-226805" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/for-loop.gif" alt="" width="1024" height="768" /> 
##### Convert anonymous class to nested class This refactoring allows you to convert an anonymous class into a named inner class. 

<img class="alignnone size-full wp-image-226808" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/annonymous.gif" alt="" width="1024" height="768" /> <h5 id="_deprecation-tags-for-symbols-and-completions" data-needslink="_deprecation-tags-for-symbols-and-completions">
  Deprecation tags for symbols and completions
</h5> Java extension now shows source code that references deprecated types or members with a strike-through line. 

<img class="alignnone size-full wp-image-226816" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/java-deprecated-method.png" alt="" width="969" height="152" /> 
### Code Snippets Now VS Code Java supports server side code snippets, which means it will provide more code snippets options in a context aware way. You can also also see more detailed information during the preview of code snippets during selection. 

<img class="alignnone size-full wp-image-226861" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/WeChat-Screenshot_20191016134421-1.png" alt="" width="1024" height="460" /> 
### Java 13 support

[<span class="pl-e">Java 13</span>][1] is out and VS Code is ready for it. It supports Java 13 through latest [<span class="pl-e">Java Extension</span>][2]. For developers use Java 12 with preview features, you will need to upgrade to JDK 13 to keep working with them. 
### Debugger

##### Show Run/Debug when hover In case you don't like the Run/Debug button on the Code Lens of your 

`main` method, but still want easy access to the functionality, you can now configure to disable the Code Lens but still accessible by hover. <img class="alignnone size-full wp-image-226813" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/runHover.gif" alt="" width="1024" height="768" /> In this release, we've also made a lot of improvements in error handling and message to help user resolve issues during debugging. One example is to add fix suggestions when a build failure occurs when launching the program. <img class="alignnone size-full wp-image-226824" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/debug-fix.png" alt="" width="451" height="86" /> By clicking `Fix...` a list of suggestions would be provided. <img class="alignnone size-full wp-image-226825" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/fix-suggestions.png" alt="" width="603" height="223" /> A more detailed [troubleshooting guide][3] is also provided. 
### Maven Support

##### Resolve unknown type Maven extension now supports searching Maven Central to resolve unknown type in your code. You can achieve this easily by clicking the link in hover. 

<img class="alignnone size-full wp-image-226812" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/resolve-unknown-type.gif" alt="" width="1024" height="768" /> Other improvements in Maven extension includes 
1.  Enable search artifact by groupId and/or artifactId when auto completing dependency.
2.  Add inline action buttons in Maven explorer. <span style="font-size: 1rem">Add icons for Maven explorer items.</span>

### Checkstyle

##### Enhanced setting configuration command

`Checkstyle: Set the Checkstyle Configuration` command will now detect potential `Checkstyle` configuration files and list them. You can also provide a configuration file by directly writing a URL in the input box now. <img class="alignnone size-full wp-image-226770" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/CheckStyle-Configuration.gif" alt="" width="1024" height="768" /> 
##### Setting checkstyle version support A new command 

`Checkstyle: Set the Checkstyle Version` is added to the extension. It supports: 
*   List the latest Checkstyle version from main repo.
*   List all the download versions.
*   List all the supported versions.
*   Mark the currently used version with a check symbol. When the version is too high (with breaking changes) for a user defined checkstyle configuration. 

<img class="alignnone size-full wp-image-226771" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/CheckStyle-Version-High.gif" alt="" width="1024" height="768" /> And when the version is too low (with new features) for `google_check.xml` fetched from checkstyle master branch. <img class="alignnone size-full wp-image-226772" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/CheckStyle-Version-Low.gif" alt="" width="1024" height="768" /> 
### Other improvements

1.  Provide more granularity of progress of loading project. We're working on making the language server more transparent with what it's working on behind the scene.
2.  Test Runner updates

<li style="list-style-type: none">
  <ul>
    <li>
      Add <code>java.test.saveAllBeforeLaunchTest</code> setting to specify whether to automatically save the files before launching the tests.
    </li>
    <li>
      Add <code>java.test.forceBuildBeforeLaunchTest</code> setting to specify whether to automatically build the workspace before launching the tests.
    </li>
  </ul>
</li>

### Sign up {#signup} If you'd like to follow the latest of Java on VS Code, please provide your email with us using the form below. We will send out updates and tips every couple weeks and invite you to test our unreleased feature and provide feedback early on. 

<div data-form-block-id="a98bf458-e066-e911-a96e-000d3a340154">
</div>

<div id="dgCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU">
</div> (function (id, f, t, ws, ms_tr_il_08, ms_tr_il_w_01) { var tr = function (cb) { var count = 0; var callback = function () { if (count == 0) { count++; if (w) { w.w(id, t, cb); } } }; var ts = document.createElement('script'); ts.src = ws; ts.type = 'text/javascript'; ts.onload = callback; ts.onreadystatechange = function () { if (this.readyState == 'complete' || this.readyState == 'loaded') { callback(); } }; var head = document.getElementsByTagName('head')[0]; head.appendChild(ts); }; if (typeof ms_tr_il_08 === 'function') { if (ms_tr_il_w_01 === null) { tr(function() { ms_tr_il_08(id, f, t); }); } else { ms_tr_il_w_01.w(id, t, function(websiteVisitedParams) { ms_tr_il_08(id, f, t, websiteVisitedParams); }); } } else { tr(); }})('gCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/f', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t/w', typeof ms_tr_il_08 === "undefined" ? null : ms_tr_il_08, typeof ms_tr_il_w_01 === "undefined" ? null : ms_tr_il_w_01); 

### Try it out Please don’t hesitate to give it a try! Your feedback and suggestions are very important to us and will help shape our product in future. 

*   Learn more about <a href="https://code.visualstudio.com/docs/languages/java" target="_blank" rel="noopener noreferrer">Java on Visual Studio Code</a>.
*   Explore our step by step <a href="https://code.visualstudio.com/docs/java/java-tutorial" target="_blank" rel="noopener noreferrer">Java Tutorials on Visual Studio Code</a>.

 [1]: http://jdk.java.net/13/
 [2]: https://marketplace.visualstudio.com/items?itemName=redhat.java
 [3]: https://github.com/Microsoft/vscode-java-debug/blob/master/Troubleshooting.md