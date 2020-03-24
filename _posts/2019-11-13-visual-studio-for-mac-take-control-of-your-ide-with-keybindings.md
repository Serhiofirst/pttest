---
ID: 227433
post_title: 'Visual Studio for Mac: Take Control of Your IDE with Keybindings'
author: Radhika
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/visual-studio-for-mac-take-control-of-your-ide-with-keybindings/
published: true
post_date: 2019-11-13 09:57:53
---
The great debates in computing all have one common theme. Whether it is tabs vs. spaces or Vi vs. Emacs, the thread linking all these debates together is keyboard efficiency. The truth is, we spend tons of hours working in an application, and keyboard shortcuts become automatic to us, the same muscle memory that great pianists or sports players have. If you suddenly give a virtuoso pianist a piano where the keys are half as wide and the sharp/flat keys are below as opposed to above the natural keys, they will struggle to make even the most basic melodies while they learn the new arrangement. Likewise, when it comes to keyboard shortcuts in your favorite IDE, any change can be disorienting quickly. Luckily, Visual Studio for Mac offers a ton of customizations to key bindings that will allow you get configure your key combinations to your liking. 
## Code example - inserted from visual editor

<pre class="prettyprint"># TestModule.psm1
function F1 { }
function F2 { }
function F3 { }

# TestModule.psd1
@{ ModuleVersion = '1.0'; RootModule = 'TestModule.psm1' }

# All functions (Function1, Function2, Function3) are exported and available
Get-Module -Name TestModule -List | Select -ExpandProperty ExportedFunctions

F1
F2
F3

</pre>

## code example inserted from text editor

<pre class="prettyprint"># TestModule.psm1
function F1 { }
function F2 { }
function F3 { }

# TestModule.psd1
@{ ModuleVersion = '1.0'; RootModule = 'TestModule.psm1' }

# All functions (Function1, Function2, Function3) are exported and available
Get-Module -Name TestModule -List | Select -ExpandProperty ExportedFunctions

F1
F2
F3</pre>     New users to Visual Studio for Mac will notice right away that the IDE offers support for many different key mappings. The first time Visual Studio for Mac is launched on a computer, you will receive a prompt directing you to pick your favorite key mapping. Here, you can select from four different key mappings to help you be as productive as possible from the first line of code you write. But what if you want even more customizations? Well, Visual Studio for Mac has you covered there as well! 

<img class="size-full wp-image-227143 aligncenter" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/ide-tour-2019-keyboard-shortcut-1.png" alt="" width="1664" height="1106" /> **More Customizing** While setting a default keymap is certainly handy, it doesn’t solve all circumstances. There may be custom mappings that you’ve used in other IDEs, or specific commands that are outside the bounds of the array of preconfigured options. With the Key Bindings selection window, you can map every possible command within the IDE to a specific key. To see the Key Binding options, select **Visual Studio > Preferences > Environment > Key Bindings**. <img class="alignnone size-full wp-image-227439" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/settings-kb.png" alt="" width="2144" height="1628" /> There are several features that I want to point out in this window, and I will take you through them one by one. The most immediate option you see is that there is a dropdown available for various “Schemes” which map to the options that new users see when they first install the IDE. Here you can select from many different pre-packaged key bindings, such as Visual Studio, VS Code and Xcode. <img class="alignnone size-full wp-image-227440" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/settings-kb-list.png" alt="" width="2144" height="1662" /> But what if you want even more control? What if you really, really want “Find Derived Symbols” to be mapped to **C****ontrol-Option-D**? Setting custom keybindings is super easy in Visual Studio for Mac. To get started, you can either scroll through the list of available commands, or search for the command in the search box. The list of available commands is organized by type of command and can be collapsed for easier navigation. Once you find the command you would like to map, you can select it and then type the desired key binding in “Edit Binding” followed by clicking “Apply”. In the below GIF, I set the binding for “New Breakpoint” to **C****ontrol-Shift-****B**.   <img class="size-full wp-image-227434 aligncenter" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/keybinding-blog-setbp.gif" alt="" width="1280" height="936" />   You can also edit an existing breakpoint in a very similar manner. In the below GIF, you can see how to edit the “New File” command to map to **Control-Shift-N** from the default **C****ommand-N. **You’ll notice that all I need to do is type in the command I prefer and click apply. If you want to add multiple bindings, simply click “Add” instead of “Apply”.   <img class="size-full wp-image-227437 aligncenter" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/keybinding-blog-addnewfile.gif" alt="" width="1280" height="936" />   Finally, with so many commands to remember, it can sometimes be hard to keep track and avoid duplicates. To ensure that each key binding is unique, Visual Studio for Mac checks against all configured commands and warns you of a duplicate if one is detected. It will also check for command duplication, so you can either replace the original or your newly created binding. The GIF below shows what happens when mapping the “New Breakpoint” command to the **“Command-C”** keyboard binding which conflicts with “Copy”.   <img class="size-full wp-image-227438 aligncenter" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/keybinding-blog-dupe.gif" alt="" width="1280" height="936" />   Now that you know how to edit the key mappings in any way you see fit, you can fully customize the IDE and get to writing code the way you love! If you want to see more key binding information, please check out our Toolbox video on the subject on [Channel 9][1] If you have any feedback or suggestions, please leave them in the comments below. You can also reach out to us on Twitter at <a href="https://twitter.com/visualstudiomac" target="_blank" rel="noopener noreferrer">@VisualStudioMac</a>. For any issues that you run into when using Visual Studio for Mac, please <a href="https://docs.microsoft.com/visualstudio/mac/report-a-problem?view=vsmac-2019" target="_blank" rel="noopener noreferrer">Report a Problem</a>.

 [1]: https://channel9.msdn.com/Shows/Visual-Studio-Toolbox/Visual-Studio-for-Mac-Keyboard-Shortcuts