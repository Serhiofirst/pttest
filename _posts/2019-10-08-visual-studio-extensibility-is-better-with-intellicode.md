---
ID: 226615
post_title: >
  Visual Studio extensibility is better
  with IntelliCode
author: Mads Kristensen
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/visual-studio-extensibility-is-better-with-intellicode/
published: true
post_date: 2019-10-08 08:00:35
---
Installing the *Visual Studio extension development* workload presents you with a choice of optional components. And looking at the component list might leave you rather confused. Because how are various C++ components and the Class Designer especially relevant to writing extension? And where is [IntelliCode][1]? <img class="alignnone size-full wp-image-226616" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/component-list.png" alt="" width="1277" height="734" /> Taking a deeper look at the list we could sensibly remove some components that most extenders are not going to use. We could also add the IntelliCode component which was missing. So, we did in the Visual Studio 2019 v16.3 update, and the result looks like this: <img class="alignnone size-full wp-image-226617" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/component-list-new.png" alt="" width="349" height="275" /> 
## Let's add IntelliCode It’s now a much cleaner list and it includes IntelliCode as an optional, but recommended component. So why is it recommended you ask? Let’s first look at what IntelliCode provides us when working with types from the Visual Studio SDK: 

<img class="alignnone size-full wp-image-226618" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/IntelliCode2.gif" alt="" width="800" height="424" /> Notice how the IntelliSense items starting with a ★ help write the code. That’s IntelliCode providing the guidance when I’m using the Visual Studio SDK. Since the SDK is so huge, it can really make exploring the APIs and choosing the right methods and properties much easier to do by popping the most relevant items to the top of my suggestion list. It has helped me on numerous occasions, so I’m a big fan. To make IntelliCode aware of the usage patterns of Visual Studio SDK, we trained its machine learning model on a lot of GitHub repositories containing extension code. The result is great guidance from types used from MEF such as [IWpfTextView][2], [EnvDTE][3], and many others. So, if you are an extension author, do yourself a favor and give IntelliCode a try and let us know how it went in the comments below.

 [1]: https://visualstudio.microsoft.com/services/intellicode/
 [2]: https://docs.microsoft.com/dotnet/api/microsoft.visualstudio.text.editor.iwpftextview
 [3]: https://docs.microsoft.com/dotnet/api/envdte