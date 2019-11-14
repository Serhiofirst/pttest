---
ID: 227363
post_title: >
  Getting Started with GitHub Actions in
  Visual Studio
author: Taysser Gherfal
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/getting-started-with-github-actions-in-visual-studio/
published: true
post_date: 2019-08-22 15:36:49
---
GitHub Actions uses a clean new syntax for expressing workflows based on YAML scripts—so you can edit, reuse, share, and fork them like code. By including actions in your repositories, others would be able to easily test and build projects using the same actions used on the original projects. GitHub Actions allows you to build, test, and deploy applications in your language of choice including .NET, C/C++, and Python. Feel free to explore all the [supported languages][1]. This blog will go over the steps needed to add actions to a new Visual Studio project and automate deployment to a Linux environment using Visual Studio. As of the date of this post GitHub Actions is still a beta feature. In order for you to try it out, you will need to [sign up for the beta][2] first. Feel free to jump to step 4 if you already have a project published on GitHub. <p style="padding-left: 40px">
  1- Start by creating any new Visual Studio project. For this blog, I am creating a new Flask Web Project. For more information on how to get started with Flask in Visual Studio take a look at this documentation: <a href="https://docs.microsoft.com/en-us/visualstudio/python/learn-flask-visual-studio-step-01-project-solution?view=vs-2019">Get started with the Flask web framework in Visual Studio</a>
</p> [caption id="attachment_226188" align="aligncenter" width="621"]

<img class=" wp-image-226188" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/2.png" alt="New Flask Project" width="621" height="432" /> New Flask Project[/caption]   <p style="padding-left: 40px">
  2- Let’s make sure that our app runs locally without any issues by selecting <strong>Debug > Start Debugging (F5)</strong> or by using the <strong>Web Server</strong> button on the toolbar.
</p>

<img class=" wp-image-226190 aligncenter" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/6.png" alt="" width="701" height="470" />   <p style="padding-left: 40px">
  3- Use the <strong>Add to Source Control</strong> option on the right-hand side of the status bar to <strong>Publish to GitHub</strong> as shown below.
</p> [caption id="attachment_226191" align="aligncenter" width="255"]

<img class=" wp-image-226191" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/TE.png" alt="Team Explorer" width="255" height="347" /> Team Explorer[/caption]   <p style="padding-left: 40px">
  4- To add an actions script, create a new YAML file for your workflow in a new directory called <strong>.github/workflows</strong> as shown below.
</p> [caption id="attachment_226192" align="aligncenter" width="723"]

<img class=" wp-image-226192" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/yml.png" alt="Actions File" width="723" height="488" /> Actions File[/caption]   <p style="padding-left: 40px">
  For this tutorial I am using the following basic YAML script that allows us to deploy our Flask web app on the latest version of Ubuntu using four different Python versions. To learn more about writing GitHub Actions take a look at the following two links:
</p>

<li style="list-style-type: none">
  <ul>
    <li>
      <a href="https://help.github.com/en/articles/configuring-a-workflow">Writing a GitHub Actions workflow file</a>
    </li>
    <li>
      <a href="https://github.com/actions/starter-workflows/tree/master/ci">https://github.com/actions/starter-workflows/tree/master/ci</a>
    </li>
  </ul>
</li>

`` `` <pre class="lang:yaml decode:true" title="Actions File - pythonpackage.yml">name: Python package

on: [push]

jobs:
  build:

    runs-on: ubuntu-latest
    strategy:
      max-parallel: 4
      matrix:
        python-version: [2.7, 3.5, 3.6, 3.7]

    steps:
    - uses: actions/checkout@v1
    - name: Set up Python ${{ matrix.python-version }}
      uses: actions/setup-python@v1
      with:
        version: ${{ matrix.python-version }}
    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt</pre>

`` ``   <p style="padding-left: 40px">
  5- After saving your YAML script, make sure to <strong>commit</strong> and <strong>push</strong> your changes using Team Explorer’s <u>Changes</u> and <u>Sync.</u> After that visit your GitHub repository by clicking on the URL that shows under the GitHub title as shown below.
</p> [caption id="attachment_226194" align="aligncenter" width="263"]

<img class="wp-image-226194" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/TE2.png" alt="Team Explorer - Home Page" width="263" height="353" /> Team Explorer - Home Page[/caption]   <p style="padding-left: 40px">
  6- On your GitHub repository click on <strong>Actions</strong> and select your <strong>workflow</strong> to see more details about your workflow. As you can see below, our code runs successfully on the four different versions of Python.
</p> [caption id="attachment_226195" align="aligncenter" width="608"]

<img class=" wp-image-226195" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/GH1.png" alt="GitHub Actions" width="608" height="331" /> GitHub Actions[/caption]   [caption id="attachment_226196" align="aligncenter" width="613"]<img class=" wp-image-226196" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/18.png" alt="GitHub Actions Workflows" width="613" height="393" /> GitHub Actions Workflows[/caption]   <p style="padding-left: 40px">
  7- With GitHub Actions you can quickly build, test, and deploy code from GitHub repositories to the cloud with Azure. To do that lets create a new workflow by making an <strong>Azure_Deploy.yml</strong> file under the same directory <strong>.github/workflows</strong> as shown below:
</p>

<pre class="lang:yaml decode:true " title="Azure_Deploy.yml ">on: push

jobs:
  build-and-deploy:
    runs-on: ubuntu-latest
    steps:
    # checkout the repo
    - uses: actions/checkout@v1
    
    # install dependencies, build, and test
    - name: Set up Python ${{ matrix.python-version }}
      uses: actions/setup-python@v1
      with:
        version: ${{ matrix.python-version }}
    - name: Install dependencies
      run: |
        python -m pip install --upgrade pip
        pip install -r requirements.txt
        
    # deploy web app using publish profile credentials
    - uses: azure/appservice-actions/webapp@master
      with: 
        app-name: MyFlaskApp
        publish-profile: ${{ secrets.azureWebAppPublishProfile }}</pre>   

<p style="padding-left: 40px">
  8- Deploying to Azure requires an Azure account. If you don't have one, you can get started today with a <a href="https://azure.com/free/open-source">free Azure account!</a> And follow these steps to configure your deployment credentials:
</p>

<li style="list-style-type: none">
  <ul>
    <li>
      Download the publish profile for the WebApp from the portal. For more information on how to do that take a look at <a href="https://docs.microsoft.com/en-us/visualstudio/deployment/tutorial-import-publish-settings-azure?view=vs-2019#create-the-publish-settings-file-in-azure-app-service">Create the publish settings file in Azure App Service</a>
    </li>
    <li>
      Define a new GitHub secret under your repository settings and paste the contents for the downloaded publish profile file into the secret's value field. Make sure the title of your secret matches the publish-profile value on your YAML script. In my case it is <strong>azureWebAppPublishProfile</strong>
    </li>
  </ul>
</li>   

<p style="padding-left: 40px">
  9- The last step would be to <strong>commit</strong> and <strong>push</strong> your changes using Team Explorer’s <u>Changes</u> and <u>Sync</u> sections as shown on step-5. After that, visit actions on your GitHub repository to make sure that all of your actions are working correctly.
</p> [caption id="attachment_226198" align="alignnone" width="2880"]

<img class="size-full wp-image-226198" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/Azure-Deploy.png" alt="GitHub Deploy Actions Workflows" width="2880" height="1276" /> GitHub Deploy Actions Workflows[/caption]   To learn more about deploying your GitHub code to the cloud take a look at the [GitHub Actions for Azure blog][3] and try out the GitHub Actions for Azure. If you encounter a problem during the preview, please open an issue on the GitHub repository for the specific action.   
### **We Need Your Feedback!** As always, let us know of any issues you run into by using the Report a Problem tool in Visual Studio. You can also head over to 

[Visual Studio Developer Community][4] to track your issues, suggest a feature, ask questions, and find answers from others. We use your feedback to continue to improve Visual Studio 2019, so thank you again on behalf of our entire team.

 [1]: https://help.github.com/en/articles/about-continuous-integration#supported-languages
 [2]: https://github.com/features/actions/signup/?account=
 [3]: https://azure.microsoft.com/en-us/blog/announcing-the-preview-of-azure-actions-for-github/
 [4]: https://developercommunity.visualstudio.com/spaces/8/index.html