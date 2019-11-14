---
ID: 226427
post_title: >
  Theming in Visual Studio just got a lot
  easier
author: Mads Kristensen
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/theming-in-visual-studio-just-got-a-lot-easier/
published: true
post_date: 2019-08-01 08:00:38
---
Sometimes the default themes for Visual Studio just aren’t enough. Lucky for us, we’ve just redesigned the process of creating and importing custom themes. <img class="alignnone size-full wp-image-226005" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/picture1.png" alt="" width="1206" height="682" /> One of the only ways to import themes was to download the older Color Theme Editor extension. If you were brave enough to create your own theme, you had to edit elements one by one from an unorganized list of 3,000+ vaguely named color tokens. This summer, a group of interns has developed a newly released [Color Theme Designer][1] extension, and we’re hoping that making custom themes just got a whole lot simpler for beginner and advanced designers alike. 
## A new theming experience Finding and using a new theme is now as easy as downloading any other extension. Just check out the new 

<a href="https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=vs2019&subCategory=Themes&sortBy=Downloads" rel="noopener noreferrer">Themes</a> category in the Visual Studio Marketplace to download themes that other users have published. For theme designers, the new [Color Theme Designer][1] comes with a more familiar startup workflow and a simplified design. <img class="alignnone size-full wp-image-226007" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/Picture3.png" alt="" width="3240" height="2080" /> We’re introducing ‘Quick start,’ a feature that lets you create a custom theme in minutes by picking three base colors. For more specific customizations, the redesigned ‘Common elements’ and ‘All elements’ tabs allow you to edit all color tokens individually. The new ‘Preview’ mode lets you see edits real-time before fully saving and applying your theme. Your final product will be a Visual Studio extension that puts your theme alongside the default themes under **Tools -> Options**. 
## Let’s create a theme!

### 1\. Set up your theme project If you’re ready to get started making your first theme (or theme pack!), download the 

[Color Theme Designer][1] and create a new ‘VSTheme Project’ in Visual Studio. <img class="alignnone wp-image-226013 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/picture4-1.png" alt="" width="2048" height="1420" /> The new project will contain an empty .vstheme file. Opening the file will prompt you to pick a base theme. <img class="alignnone size-full wp-image-226009" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/picture5.png" alt="" width="961" height="303" /> The base theme you select will fill the theme file with color tokens that you can later customize. 
### 2\. Start customizing

**<u>Only got 15 minutes?</u>** In ‘Quick start,’ you select three colors which will generate a full palette of shades that set the majority of colors in the theme. A miniature preview displays how the colors will generally appear in Visual Studio. **<u>Want to dive in deeper?</u>****:** ‘Common elements’ has roughly 100 of the most commonly edited color tokens organized under five main categories. Next to each row of tokens, a snippet preview will update as you change the colors. <img class="alignnone size-full wp-image-226010" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/picture6.png" alt="" width="1122" height="1112" /> ‘All elements’ shows every editable color token in a list that can be grouped by category or color value. Right-clicking tokens gives you the option to modify the hue, saturation, and lightness of the selection. If you can’t find a token that you are looking for, try filtering by a hex value or key words in the token name. <img class="alignnone size-full wp-image-226011" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/07/picture7.png" alt="" width="2069" height="1252" /> If you’d like to add additional theme files to your project, right-click to **Add -> New Item -> VSTheme File**. 
> Try clicking ‘Preview’ while customizing your theme to see your edits applied temporarily to the entire IDE!
### 3\. Install your theme When you’re finished customizing your theme, click ‘Apply’ if you’d like to start using it immediately. Your theme will appear under Tools -> Options -> General in the Color Themes dropdown alongside the default Visual Studio themes. To remove your theme, go to the Manage Extensions dialog and simply uninstall it like any other extension. Otherwise, build your theme project and locate. the .vsix file in the project’s output directory (‘bin’ folder) to install the theme extension. Use the .vsix file to share your theme with friends or 

[publish it][2] to the Visual Studio Marketplace! 
## In closing What do you think of the new Color Theme Designer? Are there any features you would like to see included in the future? Please let us know your thoughts in the comments below. We hope you feel inspired to download 

[the new extension][1] and begin making your own color themes, but if not, check out the Visual Studio marketplace to download <a href="https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=vs2019&subCategory=Themes&sortBy=Downloads" rel="noopener noreferrer">themes</a> that other users have made!   This blog post was written by: <table style="height: 38px;width: 100%;border-collapse: collapse;margin-bottom: 30px" cellpadding="10">
  <tbody>
    <tr style="vertical-align: top">
      <td style="width: 33.33%;height: 10px">
        <strong><a href="https://www.linkedin.com/in/prasiddhijain/">Prasiddhi Jain</a> </strong>University of North Carolina<strong> </strong>
      </td>
      
      <td style="width: 33.33%;height: 10px">
        <a href="https://www.linkedin.com/in/annapowens/"><strong>Anna Owens</strong></a> North Carolina State University
      </td>
      
      <td style="width: 33.33%;height: 10px">
        <strong>James Fuller</strong> North Carolina A&T
      </td>
    </tr>
    
    <tr style="height: 28px">
      <td style="width: 33.33%;height: 28px">
        <img class="alignnone size-full wp-image-226017" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/headshot.jpg" alt="Prasiddhi Jain" width="3456" height="3456" />
      </td>
      
      <td style="width: 33.33%;height: 28px">
        <img class="alignnone size-full wp-image-226021" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/Anna-Owens.png" alt="" width="817" height="817" />
      </td>
      
      <td style="width: 33.33%;height: 28px">
        <img class="alignnone wp-image-226019 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/avatar-1.png" alt="" width="800" height="800" />
      </td>
    </tr>
  </tbody>
</table>

 [1]: https://marketplace.visualstudio.com/items?itemName=ms-madsk.ColorThemeDesigner
 [2]: https://docs.microsoft.com/visualstudio/extensibility/walkthrough-publishing-a-visual-studio-extension