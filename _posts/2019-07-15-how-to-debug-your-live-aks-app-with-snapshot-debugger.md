---
ID: 226420
post_title: >
  Resolve code issues in live apps running
  in Azure Kubernetes Services with the
  Snapshot Debugger
author: Mark Downie
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/how-to-debug-your-live-aks-app-with-snapshot-debugger/
published: true
post_date: 2019-07-15 10:00:59
---
With ASP.NET core, my life as a Windows-first developer just broadened dramatically. I can now develop apps without being tied to a single platform. Having spent most of my career as a "Windows only" developer, I am now taking on the task of [redesigning a twenty-year-old][1], IIS based service, so that it could be built on a Mac and hosted on Linux in Azure. Given these new hosting possibilities one of my pressing concerns was how little I knew about the Linux world in general and, more specifically, what tools and techniques I could use when debugging complex issues in production. Thankfully for me, Visual Studio 2019 Enterprise has expanded support to include [Azure Kubernetes Services][2] (AKS) managing Linux containers. 
### Debug without interruption in AKS Why Snapshot Debugger? Diagnosing production issues in the cloud can be difficult and time consuming because you may be dealing with issues that only occur at scale or in specific environments, and your favorite debugging tools are often unavailable. Remote debugging your production site is rarely an option because it is serving live traffic, and any action that stops the web process would immediately impact your customers. Snapshot Debugger is built for production and works at cloud scale. If you are familiar with breakpoints and tracepoints in VS for debugging local code, then 

[Snappoints][3] and [Logpoints][4] are similar but for debugging against apps running in production (without stopping execution). You are able to attach to these snapshots within the familiar and intuitive environment of Visual Studio and analyze specific lines of code using your Locals, Watches and Call Stack windows. 
### Prepping your Dockerfiles for Snapshot Debugger Setting up Snapshot Debugger to work with AKS Linux Docker containers requires the following Dockerfile prerequisites: 

*   Install Snapshot Debugger prerequisites (libxml2, libuuid, libunwind, bash, unzip).
*   Install Visual Studio Snapshot Debugger components.
*   Set environment variables to load Visual Studio Snapshot Debugger into your .NET Core applications.
*   Install Visual Studio Debugger components. We have provided 

[a repo containing a set of Dockerfiles][5] that demonstrate the setup on Docker images for several Linux variants. Each file includes the latest supported Snapshot Debugger backend package and sets the environment variables to load the debugger into your .NET Core application. <table style="height: 112px;border-style: solid" border="1">
  <tbody>
    <tr style="height: 28px;background-color: #2d49eb">
      <td style="height: 28px" width="208">
        <span style="color: #ffffff">Linux variant</span>
      </td>
      
      <td style="height: 28px" width="122">
        <span style="color: #ffffff">.NET Core</span>
      </td>
      
      <td style="height: 28px" width="294">
      </td>
    </tr>
    
    <tr style="height: 28px">
      <td style="height: 28px" width="208">
        Debian 9 (Stretch)
      </td>
      
      <td style="height: 28px" width="122">
        2.2
      </td>
      
      <td style="height: 28px" width="294">
        <a href="https://github.com/microsoft/vssnapshotdebugger-docker/tree/master/2.2/stretch-slim/amd64/Dockerfile">Dockerfile (amd64)</a>
      </td>
    </tr>
    
    <tr style="height: 28px">
      <td style="height: 28px" width="208">
        Alpine 3.8
      </td>
      
      <td style="height: 28px" width="122">
        2.2
      </td>
      
      <td style="height: 28px" width="294">
        <a href="https://github.com/microsoft/vssnapshotdebugger-docker/tree/master/2.2/alpine3.8/amd64/Dockerfile">Dockerfile (amd64)</a>
      </td>
    </tr>
    
    <tr style="height: 28px">
      <td style="height: 28px" width="208">
        Ubuntu (Bionic)
      </td>
      
      <td style="height: 28px" width="122">
        2.2
      </td>
      
      <td style="height: 28px" width="294">
        <a href="https://github.com/microsoft/vssnapshotdebugger-docker/tree/master/2.2/bionic/amd64/Dockerfile">Dockerfile (amd64)</a>
      </td>
    </tr>
  </tbody>
</table>   

### Setup Snapshot Debugger for AKS in your ASP.NET Core project You can use the following instructions to provide Snapshot Debugger support your ASP.NET Core web apps: 

*   In Visual Studio 2019, configure your Web application to use Docker

<li style="list-style-type: none">
  <ol style="list-style-type: lower-roman">
    <li>
      Right-click on the web application Add->Docker Support
    </li>
    <li>
      Target OS: Linux
    </li>
  </ol>
</li>

<img class="alignnone size-full wp-image-225850" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/vs2019-docker-support.gif" alt="Add Docker Support to Visual Studio" width="1062" height="796" /> 
*   Select a version of Linux to use from the [Visual Studio Snapshot Debugger Docker image repository][5] and merge it with the Dockerfile created for your web application. An [example of a merged Dockerfile can be found here][6].
*   In Visual Studio, rebuild your web solution to create a new docker image.
*   Tag your local image. In the following example I rename "dasblog-core" to "poppastring/dasblog-core": <ol style="list-style-type: lower-roman">
      <li>
        <em>docker tag dasblog-core poppastring/dasblog-core</em>
      </li>
    </ol>

*   Push the newly tagged image to your image repository (using docker in this example). <ol style="list-style-type: lower-roman">
      <li>
        <em>docker push poppastring/dasblog-core</em>
      </li>
    </ol>

*   Deploy your application to AKS. More details on [deploying to AKS with Cloud Shell and Azure CLI  can be found here][7]. Additionally this [sample YAML file][8] sets up a basic deployment and service scenario.
*   Choose **Debug** > **Attach Snapshot Debugger** and select the Azure Kubernetes Service your project is deployed to along with an Azure storage account and click Attach. You are now in snapshot debugger mode!
*   In the code editor, click the left gutter to create a Snappoint and click **Start Collection** to deploy your Snappoint to Azure.

<img class="alignnone size-full wp-image-225869" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/vs2019-set-snappoint.gif" alt="Set a Snappoint" width="908" height="771" /> 
*   Navigate to your service to execute the code represented by the Snappoint.
*   Once your Snapshot has been collected, in Visual Studio click on **View Snapshot** to view your Locals, Watches and Call Stack windows at that moment in time.

[Check out this video where I use Snapshot Debugger][9] to uncover a flaw in my open source code hosted in Azure. You can also find additional [details on Debugging live Azure Kubernetes Services here][10]. 
### Try it out! We are excited to be able to offer first class production diagnostics support with Visual Studio 2019 Enterprise and Snapshot Debugger. Snapshot Debugging is now supported in Azure Kubernetes Services as well as Azure App Services, Azure Virtual Machines and Azure Virtual Machine scale sets. We encourage you to try out the new capabilities in your solution and 

[we look forward to hearing your feedback and how we can make this feature better][11]. We’re also working towards adding support for ASP.NET Core 3 and additional Linux versions in the near future, so be sure to [follow our Dockerfile repo][5] for updates.    

 [1]: https://github.com/poppastring/dasblog-core
 [2]: https://docs.microsoft.com/en-us/azure/aks/intro-kubernetes
 [3]: https://docs.microsoft.com/en-us/visualstudio/debugger/debug-live-azure-applications?view=vs-2019#set-a-snappoint
 [4]: https://docs.microsoft.com/en-us/visualstudio/debugger/debug-live-azure-applications?view=vs-2019#set-a-logpoint
 [5]: https://github.com/Microsoft/vssnapshotdebugger-docker
 [6]: https://github.com/poppastring/dasblog-core/blob/master/source/DasBlog.Web.UI/Dockerfile
 [7]: https://docs.microsoft.com/en-us/azure/aks/kubernetes-walkthrough
 [8]: https://gist.github.com/poppastring/9527032c49826996579b28a1bbfe11c8
 [9]: https://www.youtube.com/watch?v=G-nr8sA4kEc&feature=youtu.be&t=260
 [10]: https://docs.microsoft.com/en-us/visualstudio/debugger/debug-live-azure-kubernetes
 [11]: https://developercommunity.visualstudio.com/spaces/8/index.html