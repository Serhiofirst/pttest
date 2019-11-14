---
ID: 227184
post_title: >
  Re-imagining developer productivity with
  AI-assisted tools
author: Amanda Silver
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/ai-assisted-developer-tools/
published: true
post_date: 2019-11-04 11:00:09
---
<h3 style="text-align: left">
  <strong>TL;DR:</strong>
</h3>

<p style="text-align: left">
  Harnessing the wisdom of the community, Visual Studio IntelliCode is revolutionizing developer productivity. We started with <a href="https://devblogs.microsoft.com/visualstudio/introducing-visual-studio-intellicode/">AI-assisted IntelliSense</a> and are now expanding the application of artificial intelligence to significantly accelerate learning, radically improve development agility, and increase code quality by means of two exciting new capabilities:<strong> whole line completions</strong> and <strong>refactoring</strong>.
</p>

<p style="text-align: left">
  Technology is evolving so fast that every developer is constantly learning, whether you're adopting a new programming language, API, or architecture (e.g. microservices). Amidst this rate of technological change, existing tools are no longer sufficient for achieving agility as development teams are trying to accelerate their time-to-market  and increase code quality. As a result, development tools need to radically evolve to satisfy the productivity demands of modern teams.
</p>

<p style="text-align: left">
  At <a href="https://www.microsoft.com/en-us/ignite">Microsoft Ignite</a>, we showed a vision of how AI can be applied to developer tools. After talking with thousands of developers over the last couple years, we found that the most highly effective assistance can only come from one source: <strong>the collective knowledge of the open source, GitHub community.</strong> This is exactly what IntelliCode provides.
</p>

### **AI-assisted suggestions + whole-line code completions**

<p style="text-align: left">
  IntelliCode now provides whole-line code completion suggestions mined from the collective intelligence of your trusted developer knowledge bases. This is like having an AI-developer pair-programming with you, providing meaningful, suggestions and whole-line code completions without disrupting your flow. To generate accurate suggestions and provide completion assistance as you code, IntelliCode extends the <a href="https://openai.com/blog/better-language-models/">GPT-2</a> transformer language model for our machine-learning models to learn about programming languages and coding patterns.
</p>

<p style="text-align: left">
  The <a href="https://nam06.safelinks.protection.outlook.com/?url=https%3A%2F%2Fs3-us-west-2.amazonaws.com%2Fopenai-assets%2Fresearch-covers%2Flanguage-unsupervised%2Flanguage_understanding_paper.pdf&data=04%7C01%7Cccaldwel%40microsoft.com%7C7d2c996183d24c9d630f08d756579f04%7C72f988bf86f141af91ab2d7cd011db47%7C1%7C0%7C637072806886470829%7CUnknown%7CTWFpbGZsb3d8eyJWIjoiMC4wLjAwMDAiLCJQIjoiV2luMzIiLCJBTiI6Ik1haWwiLCJXVCI6Mn0%3D%7C-1&sdata=iFRdr%2F3NLMJfJyu6q7jjvSFhFavVKFBandOpeCkI6uI%3D&reserved=0">GPT model architecture</a>, originally developed by OpenAI, has demonstrated strong natural language understanding, including the ability to generate conditional synthetic text examples without needing domain-specific training datasets. For our initial language-specific base models, we adopted an unsupervised learning approach that learns from over 3000 top GitHub repositories. Our base model extracts statistical coding patterns and learns the intricacies of programming languages from GitHub repos to assist developers in their coding. Based on code context, as you type, IntelliCode uses that semantic information and sourced patterns to predict the most likely completion in-line with your code.
</p> [caption id="" align="aligncenter" width="625"]

[<img title="AI-assisted whole-line code completion" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/WholeLinePyGif-1.gif" alt="Suggested whole-line completions in Visual Studio Code editor" width="625" height="290" />][1] AI-assisted whole-line completions in Visual Studio Code editor[/caption]   <p style="text-align: left">
  IntelliCode has now extended our machine-learning model training capabilities beyond the initial base model to enable your  teams to train their own team completions. Team completions are useful if your development team uses internal utility and base class libraries or domain-specific libraries that aren’t commonly used in open-source GitHub repositories. If you’re using code that isn’t in that set of GitHub repos, those recommendations aren’t as useful to you. By training on your team’s code, IntelliCode learns patterns from your code to make more accurate suggestions. This enables your  team to accelerate  learning and take advantage of the knowledge of your team and broader community.
</p>

### **AI-assisted Refactoring**

<p style="text-align: left">
  IntelliCode watches code changes as they occur in the IDE and locally synthesizes, on demand, edit scripts from any set of repetitive pattern changes. It uses these edit scripts to produce suggestions, enabling you to apply repetitive changes quickly or create a pull request to apply the suggestion(s) for team review without distracting your current work. IntelliCode refactorings take the time-intensity and error-proneness out of routine tasks, such as introducing a new helper function. To do so, IntelliCode uses an AI technology called <strong>program synthesis</strong>, and more specifically, programming-by-examples <strong>(PBE). </strong>
</p> [caption id="attachment_227212" align="aligncenter" width="946"]

<a style="background-color: #bfe6ff;background-image: none;color: #006f94;font-family: Arimo,Helvetica Neue,Arial,sans-serif;font-size: 16px;font-style: normal;font-variant: normal;font-weight: 400;letter-spacing: normal;text-align: left;text-decoration: underline;text-indent: 0px;text-transform: none;padding: 0px 2px 0px 2px;margin: 0px -2px 0px -2px" href="https://aka.ms/vsic/blog/refactorings"><img class="wp-image-227212 size-full" style="color: #52595e;font-family: Arimo,Helvetica Neue,Arial,sans-serif;font-size: 16px;font-style: normal;font-variant: normal;font-weight: 400;height: auto;letter-spacing: normal;max-width: 100%;text-align: left;text-decoration: none;text-indent: 0px;text-transform: none;vertical-align: middle;border-style: none;margin: 0px auto 0px auto" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/IntelliCodeRefactoring-1.png" alt="Quick action menu in Visual Studio IDE showing available actions for IntelliCode refactorings. Available actions are take the repeated edit, ignore the suggestion, or submit a new PR with the suggestion." width="946" height="136" /></a> IntelliCode refactorings based on repetitive code edits in Visual Studio IDE[/caption]   <p style="text-align: left">
  PBE technology has been developed at Microsoft by the <a href="https://microsoft.github.io/prose/">PROSE team</a> and has been applied to various products to enable users to streamline repetitive tasks after providing a few examples. You’ve seen PBE in action in <a href="https://support.office.com/en-us/article/using-flash-fill-in-excel-3f9bcf1e-db93-4890-94a0-1578341f73f7">Flash Fill in Excel</a> and <a href="https://docs.microsoft.com/en-us/power-bi/desktop-connect-to-web-by-example">webpage table extraction in PowerBI</a>. IntelliCode <a href="https://www.microsoft.com/en-us/research/publication/on-the-fly-synthesis-of-edit-suggestions/">advances the state-of-the-art</a> in PBE by allowing patterns to be learned from noisy traces as opposed to explicitly provided examples, without any additional steps on your part. You can read more about this in <a href="https://aka.ms/vsic/blog/refactorings">this earlier post</a>. We’re planning to broaden this capability to more languages, as well as enabling your team easily benefit from the patterns that you find.
</p>   [caption id="attachment_227231" align="aligncenter" width="682"]

<img class="wp-image-227231" style="color: #52595e;font-family: Arimo,Helvetica Neue,Arial,sans-serif;font-size: 16px;font-style: normal;font-variant: normal;font-weight: 400;height: auto;letter-spacing: normal;max-width: 100%;text-align: left;text-decoration: none;text-indent: 0px;text-transform: none;vertical-align: middle;border-style: none;margin: 0px auto 0px auto" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/RefactoringGif.gif" alt="Display of IntelliCode refactoring suggestions in Visual Studio IDE" width="682" height="478" /> IntelliCode refactorings in Visual Studio IDE[/caption]   
### **What about privacy and code security?** We know that your code is a vital business asset, so we are committed to a simple principle across our developer tools and services: your code remains your code, your models are your models, and remain your models unless you choose to share them with others. You control when to utilize AI-assistance and who has access to your data. As examples of this principle in action, when we train a team model for IntelliCode completions on your codebase, we don’t share that model with anyone but you unless you choose to share it, and we locally extract only those elements of the code that are needed to create a model for recommending completion values. We also make it easy for you to ensure that access to your model follows the same security access rules as your code repo when shared, with no extra configuration. You can read more about this in the 

[documentation][2]. Our PROSE-based models work entirely locally, so your code never leaves your machine. When it is necessary for us to use a service-based model to deliver a feature, we ensure all appropriate security is in place to secure any information (including code) that is transmitted over the network – the [documentation][3] has more information. <h3 style="text-align: left">
  <strong>What’s next? </strong>
</h3>

<p style="text-align: left">
  Our ambition is to contribute to developer-assistance across the whole developer lifecycle. We’re particularly interested in making learning and retrieving typical code snippets whilst learning a new API or re-learning an old one, a lot easier. We continue to listen hard to our developer community about where we can best contribute to assist with your daily development challenges.
</p>

<p style="text-align: left">
  Get the latest <a href="https://visualstudio.microsoft.com/vs/preview/">Visual Studio 2019 previews</a>; there, you can try much of this out for C# already. Watch the Visual Studio blog for more announcements as we make progress.
</p>

<p style="text-align: left">
  You can also <a href="https://aka.ms/vsicsignup">sign up</a> for regular updates and invitations to future private previews.
</p>

### **Try it now** You can try out IntelliCode team models and refactorings in Visual Studio for C# by downloading our latest 

[Visual Studio Preview][4]. We also support a variety of languages in Visual Studio and [Visual Studio Code][5]: 
*   **Visual Studio**: C#, C++, JS/TS, XAML
*   **Visual Studio Code**: Python, JS/TS, Java, SQL   

<p style="text-align: center">
  Happy coding!
</p>

 [1]: https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/WholeLinePyGif-1.gif
 [2]: https://docs.microsoft.com/en-us/visualstudio/intellicode/custom-models#data-and-privacy
 [3]: https://docs.microsoft.com/en-us/visualstudio/intellicode/custom-models#how-we-secure-your-data
 [4]: https://visualstudio.microsoft.com/vs/preview/
 [5]: https://marketplace.visualstudio.com/items?itemName=VisualStudioExptTeam.VSIntelliCode