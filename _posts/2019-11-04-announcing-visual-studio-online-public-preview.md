---
ID: 227248
post_title: >
  Announcing Visual Studio Online Public
  Preview
author: Pierre Crutchfield
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/announcing-visual-studio-online-public-preview/
published: true
post_date: 2019-11-04 06:00:38
---
### TL;DR Available beginning at Microsoft's Ignite conference as a public preview, Visual Studio Online provides managed, on-demand development environments that can be used for long-term projects, to quickly prototype a new feature, or for short-term tasks like reviewing pull requests. You can work with environments from anywhere using either Visual Studio Code, Visual Studio IDE (

<a href="https://aka.ms/vsfutures-signup" target="_blank" rel="noopener noreferrer">in private preview</a>), or the included browser-based editor. 😁 <img class="alignnone size-full wp-image-227251" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/vso-anywhere.png" alt="Visual Studio Online - Develop anywhere" width="865" height="512" /> 
### Empowering Modern Development Software developers, and the software development process, live on the bleeding edge of technological trends. We talk to developers every day, and we've heard that expectations for innovation continue to increase across all industries and sectors. We've also noted resounding feedback that the confluence of current trends demands a new breed of development tools and capabilities. These trends include: 

*   More and more teams are distributed remotely, or leveraging freelancers, which magnify the pain of onboarding new team members without the benefit of a local IT presence.
*   Open source and *inner source* are making collaboration more important than ever. As a result, developers are working across boundaries in many codebases, often at the same time.
*   Increasing computational and data workloads (e.g. Machine Learning, Artificial Intelligence, Big Data), powered by cloud computing, are naturally shifting development activities beyond the "standard issue development laptop".
*   The explosion of cloud native development and microservices have enabled developers to use multiple languages and stacks in a single system to take advantage of each technology's particular strengths.
*   Developers facing expectations for decreased time-to-market are seeking techniques and technologies to help them collaborate more quickly and increase productivity. As a result of your feedback, these trends, and 

<a href="https://code.visualstudio.com/blogs/2019/05/02/remote-development" target="_blank" rel="noopener noreferrer">what we have learned with Visual Studio Code Remote Development</a>, we have been working hard on a new service called Visual Studio Online. Visual Studio Online philosophically (and technically) extends Visual Studio Code Remote Development to provide managed development environments that can be created on-demand and accessed from anywhere. These environments can be used for long-term projects, to quickly prototype a new feature, or for short-term tasks like reviewing pull requests. Additionally, since many companies already have existing infrastructure for development, we made sure that Visual Studio Online can take advantage of those as well. You can connect to your environments from anywhere using either Visual Studio Code, Visual Studio IDE (see below), or the included browser-based editor. **We're excited to get your feedback as we launch Visual Studio Online into public preview.** Read on to learn more about the service and the scenarios it enables, or dive right in with <a href="https://aka.ms/vso-docs/quickstart/browser" target="_blank" rel="noopener noreferrer">one of our quickstarts</a>. 
### Rapid Onboarding Development environments are the cornerstone on which Visual Studio Online is based. They're where all of the compute associated with software development happens: compiling, debugging, restoring, etc. Whatever your project or task, you can spin up a Visual Studio Online environment from your development tool of choice or our web portal, and the service will automatically configure everything you need: the source code, runtime, compiler, debugger, editor, personal 

<a href="https://hackernoon.com/learn-how-to-manage-dotfiles-b8b62c6c5491" target="_blank" rel="noopener noreferrer">dotfile configurations</a>, relevant editor extensions and more. Environments are fast to create and disposable, allowing new team members to quickly onboard to a project, or for you to experiment with a new stack, language, or codebase, without worrying about it affecting your local configuration. And since environments share definitions, they are created in a repeatable manner – all but eliminating configuration discrepancies between team members that often lead to “works on my machine” type bugs. Additionally, environments are <a href="https://aka.ms/vso-docs/reference/configuring" target="_blank" rel="noopener noreferrer">completely configurable</a> so they can be precisely tuned as required by your project. Start simple by specifying a few extensions that you want installed, or take full control over the environment by defining your own <a href="https://docs.docker.com/engine/reference/builder/" target="_blank" rel="noopener noreferrer">Dockerfile</a>. 
### Cloud Powered Visual Studio Online's development environments are Azure-hosted and come with all the benefits of the cloud: 

*   They scale to meet your needs: 
    *   Create as many as you want (up to subscription limits) for all your various projects and tasks and throw them away when you're done.
    *   Need a little extra horsepower? Create a premium environment to get all the CPU and RAM you'd need to tackle even the most demanding projects.
*   They have predictable pricing and you only pay for what you use – down to the second. If you create an environment and delete it after 6 minutes and 45 seconds, you'll only pay for 6 minutes and 45 seconds. Environments also auto-suspend to eliminate accidental runoff costs.
*   Moving your development workload to the cloud boosts your overall computing power so your personal machine can edit media assets, email, chat, stream music, or do anything else, more. Already have investments in on-premise development environments, or not quite yet ready to move a workload to the cloud? Visual Studio Online also allows you to register and connect your own self-hosted environments, so you can use that already-perfectly-tuned environment and experience some of the benefits of Visual Studio Online, for free! 

### Your Favorite Tools Visual Studio Online supports three editors: 

<a href="https://code.visualstudio.com/" target="_blank" rel="noopener noreferrer">Visual Studio Code</a>, our no-install browser-based editor, and <a href="https://visualstudio.microsoft.com/vs/" target="_blank" rel="noopener noreferrer">Visual Studio IDE</a> (see below). This allows you to use the tool you're most comfortable with, in any language or framework. By installing the <a href="https://aka.ms/vso-marketplace" target="_blank" rel="noopener noreferrer">Visual Studio Online extension</a> you can use Visual Studio Code, the streamlined code editor with support for operations like debugging, task running, and version control. It aims to provide just the tools a developer needs for a quick code-build-debug cycle. It's free, built on open source and now enhanced with cloud powered development environments. Visual Studio Online's browser-based editor adds the ability to connect and code from literally anywhere, and its fully powered with Visual Studio Code under the hood. Gone are the days of lugging around heavy dev machines on the road or to a coffee shop. Instead, travel light knowing you've got the full computing power of Azure, just a new browser tab away. We're also proud to announce that Visual Studio IDE's support for Visual Studio Online is in private preview at Ignite. Developers will now have the option to use a full-fledged IDE with the entire toolset, from initial design to final deployment, enhanced with the benefits of Visual Studio Online. Along with this private preview, we're also introducing the capability to create Windows based Visual Studio Online environments, expanding the set of workloads the service will support. <a href="https://aka.ms/vsfutures-signup" target="_blank" rel="noopener noreferrer">Sign up now</a> to be added to the wait list. Along the way we've also learned that developers not only want to use the right tool for the job, but they are also highly opinionated about their development environment, and commonly spend countless hours personalizing their editor and terminal. To address this, Visual Studio Online's flexible <a href="https://aka.ms/vso-docs/reference/personalizing" target="_blank" rel="noopener noreferrer">personalization features</a> make any environment you connect to feel familiar, as if you've never left home, whichever editor you decide to use. Even better, you can freely extend these capabilities since Visual Studio Online has support for the rich ecosystem of extensions in <a href="https://marketplace.visualstudio.com/" target="_blank" rel="noopener noreferrer">the Visual Studio Marketplace</a>. 
### Effortless Remote Debugging Once connected to your Visual Studio Online environment, simply run your web app or API as you usually would, and we automatically forward it, so that it's accessible to you – and only you. It behaves just like your traditional, local dev workflow. In addition, we'll soon be introducing support for app casting, that will allow you to remotely interact with and share a running GUI application. 

### Built in Collaboration On top of all of this, Visual Studio Online's environments come with built in collaboration tools like 

<a href="https://aka.ms/ic" target="_blank" rel="noopener noreferrer">IntelliCode</a> and <a href="https://aka.ms/vsls" target="_blank" rel="noopener noreferrer">Live Share</a>. IntelliCode helps enhance individual productivity by instilling AI-assisted intelligence into the editor. It does this by making things like auto-completion smarter with “implicit collaboration” based on an understanding of how APIs are used across thousands of open-source GitHub repositories. Live Share directly facilitates real-time collaboration by enabling developers to edit and debug together, even if they aren't all Visual Studio Online users, or prefer a different editor. 
### And More to Come! Visual Studio Online is in public preview at Ignite. That means that now is a great time to try it out and 

<a href="https://aka.ms/vso-issues" target="_blank" rel="noopener noreferrer">share your feedback</a>. We're eagerly looking forward to working with the community to understand the best ways to make Visual Studio Online even better. I want to thank all the users who have submitted feedback already – you're the ones who have made the service as great as it is today – and I can't wait to hear from so many more of you. 
## Next Steps If you'd like to learn more, head over to 

<a href="https://aka.ms/vso-landing" target="_blank" rel="noopener noreferrer">our product page</a> or “<a href="https://aka.ms/vso-docs/overview" target="_blank" rel="noopener noreferrer">What is Visual Studio Online?</a>” documentation. To try the service, follow along with our <a href="https://aka.ms/vso-docs/quickstart/vscode" target="_blank" rel="noopener noreferrer">Visual Studio Code</a> or <a href="https://aka.ms/vso-docs/quickstart/browser" target="_blank" rel="noopener noreferrer">browser-based experience</a> quickstarts. As mentioned above, if you're interested in Visual Studio IDE support and Windows based environments, <a href="https://aka.ms/vsfutures-signup" target="_blank" rel="noopener noreferrer">sign up for our private preview</a> and we'll do our best to grant you access as soon as possible. Finally, feel free to report any feedback you have in <a href="https://aka.ms/vso-issues" target="_blank" rel="noopener noreferrer">our issue tracker</a> on GitHub. We can't wait to hear what you think! Thanks, Nik Molnar & the entire Visual Studio Online team 👋