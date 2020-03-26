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

    # TestModule.psm1
    

function F1 { } function F2 { } function F3 { }

# TestModule.psd1

@{ ModuleVersion = '1.0'; RootModule = 'TestModule.psm1' }

# All functions (Function1, Function2, Function3) are exported and available

Get-Module -Name TestModule -List | Select -ExpandProperty ExportedFunctions

F1 F2 F3

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
F3</pre>

    New users to Visual Studio for Mac will notice right away that the IDE offers support for many different key mappings. The first time Visual Studio for Mac is launched on a computer, you will receive a prompt directing you to pick your favorite key mapping. Here, you can select from four different key mappings to help you be as productive as possible from the first line of code you write. But what if you want even more customizations? Well, Visual Studio for Mac has you covered there as well!

## Code example inserted when editor was markdown

    @page "/counter"
    
    <h1>Counter</h1>
    
    <p>Current count: @currentCount</p>
    
    <button class="btn btn-primary" @onclick="IncrementCount">Click me</button>
    
    @code {
        int currentCount = 0;
    
        void IncrementCount()
        {
            currentCount++;
        }
    }
    

<img class="size-full wp-image-227143 aligncenter" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/ide-tour-2019-keyboard-shortcut-1.png" alt="" width="1664" height="1106" /> **More Customizing** While setting a default keymap is certainly handy, it doesn’t solve all circumstances. There may be custom mappings that you’ve used in other IDEs, or specific commands that are outside the bounds of the array of preconfigured options. With the Key Bindings selection window, you can map every possible command within the IDE to a specific key. To see the Key Binding options, select **Visual Studio > Preferences > Environment > Key Bindings**. <img class="alignnone size-full wp-image-227439" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/11/settings-kb.png" alt="" width="2144" height="1628" />