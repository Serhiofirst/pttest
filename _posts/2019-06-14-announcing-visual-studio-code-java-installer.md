---
ID: 226416
post_title: >
  Announcing the Visual Studio Code
  Installer for Java
author: Xiaokai He
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/announcing-visual-studio-code-java-installer/
published: true
post_date: 2019-06-14 10:02:17
---
It’s been almost 3 years since the first Java language server was developed during a [hackathon][1] in a small conference room at Microsoft’s Zurich office with people from Red Hat, IBM, Codenvy and Microsoft, which later became [one of the most popular extensions][2] for Visual Studio Code with more than 2.7 million installations. Since then, Visual Studio Code has gone through a thrilling journey and become to the most popular development environments according to [Stack Overflow][3]. More and more Java extensions are now available in Visual Studio Code to serve a growing Java community using Visual Studio Code along with their favorite tools and frameworks. During this journey, we've heard many developers ask how to start with Java in Visual Studio Code. As the vibrant Java community expands to include more students and developers from other languages, many new comers struggle with setting up their environment to be able to start coding. To help people get started, we created the Java [extension pack][4] to give you the relevant extensions, and also included [tutorials][5] with detailed steps in our documentation. Back in 2018, Microsoft Azure became a [Platinum Sponsor][6] of the [AdoptOpenJDK][7] project – that just got [renewed until June 2020][8] – and provides a truly vendor neutral, completely free and open source distribution of the JDK (Java Development Kit) based on the OpenJDK project. This was a turning point for us so much we’ve also added a functionality to detect and help developers install a JDK binary in their environments, having AdoptOpenJDK as the recommended distribution. These efforts were encouraging, but got us thinking about more ways we could make it easier to starting coding in Java. 
### Introducing the Visual Studio Code Java Pack Installer So today, we’re releasing a special 

[Installer of Visual Studio Code for Java developers][9]. The package can be used as a clean install or an update for existing environment to add Java or Visual Studio Code to your development environment<span style="font-size: 1rem">. Once <a href="https://aka.ms/vscode-java-installer-win">downloaded</a> and opened, i</span>t automatically detects if you have the fundamental components in your local development environment, including the JDK, Visual Studio Code and essential Java extensions. <img class="alignnone size-full wp-image-225751" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/Components-1.png" alt="" width="596" height="478" /> After clicking Install, it will pull the stable versions of those tools from trusted online sources and install them on your system. Once it’s done, you can open Visual Studio Code and start writing and running Java code directly! Below is a short video showing you how to write and run a *Hello World* program with Java in Visual Studio Code in less than 1 minute. See more detailed functionality in our [tutorial][5]. [video poster="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2018/08/vsfeaturemed.png" width="1022" height="766" mp4="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/JavaHelloWorld.mp4"][/video]   <span style="font-size: 12pt">The installer is available for <a href="https://aka.ms/vscode-java-installer-win">download</a> for Windows now while we're still working on the macOS version. Please have a try and let us know your <a href="https://www.research.net/r/vscodejava-blog?o=[o_value]&m=[m_value]">feedback</a>!</span> If you'd like to follow the latest of Java on Visual Studio Code, please provide your email with us using the form below. We will send out updates and tips every couple weeks. <div data-form-block-id="a98bf458-e066-e911-a96e-000d3a340154">
</div>

<div id="dgCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU">
</div> (function (id, f, t, ws, ms_tr_il_08, ms_tr_il_w_01) { var tr = function (cb) { var count = 0; var callback = function () { if (count == 0) { count++; if (w) { w.w(id, t, cb); } } }; var ts = document.createElement('script'); ts.src = ws; ts.type = 'text/javascript'; ts.onload = callback; ts.onreadystatechange = function () { if (this.readyState == 'complete' || this.readyState == 'loaded') { callback(); } }; var head = document.getElementsByTagName('head')[0]; head.appendChild(ts); }; if (typeof ms_tr_il_08 === 'function') { if (ms_tr_il_w_01 === null) { tr(function() { ms_tr_il_08(id, f, t); }); } else { ms_tr_il_w_01.w(id, t, function(websiteVisitedParams) { ms_tr_il_08(id, f, t, websiteVisitedParams); }); } } else { tr(); }})('gCPdzqBMykwIL6XsCcP3tC9zZGvAAN-t3ma0GiZE0QU', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/f', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t', 'https://5a3318f6fcc34e41bf99d46845944055.svc.dynamics.com/t/w', typeof ms_tr_il_08 === "undefined" ? null : ms_tr_il_08, typeof ms_tr_il_w_01 === "undefined" ? null : ms_tr_il_w_01); Thank you and happy coding.

 [1]: https://developers.redhat.com/blog/2016/08/01/a-week-of-hacking-the-java-language-server/
 [2]: https://marketplace.visualstudio.com/items?itemName=redhat.java
 [3]: https://insights.stackoverflow.com/survey/2019#technology-_-most-popular-development-environments
 [4]: https://marketplace.visualstudio.com/items?itemName=vscjava.vscode-java-pack
 [5]: https://code.visualstudio.com/docs/java/java-tutorial
 [6]: https://adoptopenjdk.net/sponsors.html
 [7]: https://adoptopenjdk.net/
 [8]: https://twitter.com/brunoborges/status/1138230835784503296
 [9]: https://aka.ms/vscode-java-installer-win