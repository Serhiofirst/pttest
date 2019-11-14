---
ID: 227360
post_title: >
  Code, Recent Items, and Template Search
  In Visual Studio
author: Andrew Cheung
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/code-recent-items-and-template-search-in-visual-studio/
published: true
post_date: 2019-08-15 08:00:42
---
We are introducing the ability to search for code, recent items, and templates through the new search experience in Visual Studio. These features can all be accessed by one single shortcut (Ctrl+Q) and are currently available in our Preview build (<https://visualstudio.microsoft.com/vs/preview/>). They will be available in Visual Studio 2019, version 16.3, targeted for the end of September. 
## Background One of the focus areas in Visual Studio 2019 is to improve search efficiency and effectiveness. Our journey started with the introduction of the new search experience in Visual Studio component (Ctrl+Q), along with improved search accuracy for menus, commands, options, and installable components. 

## <img class="wp-image-226108" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/word-image.jpeg" />

## Code Search Code search has arrived in the search (Ctrl+Q) control. It is now possible to search for types and members with C# and VB, as well as file search for all languages.  Results will show up as you type your search query, as well as in a dedicated ‘Code’ group accessible via keyboard shortcut or mouse click. Keep an eye out for support of additional languages in the near future! 

<img class="wp-image-226109" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/word-image.gif" /> It is also possible to search by camel-case. This allows you to type in an abbreviation of the code search term with just capitalized letters instead of the full name. <img class="wp-image-226110" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/word-image-1.gif" /> 
## Recent Items Search Recently opened items can be searched through search (Ctrl+Q) and in the start window (Alt+F, W). Both entry points will be enabled with fuzzy search (to help automatically rectify typos) and the ability to see highlighted matches to your search query in the results. 

<img class="wp-image-226111" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/word-image-2.gif" /> 
## Template Search Your favorite templates can now be accessed faster when you are starting up Visual Studio, or already in the IDE!  Templates can be accessed through search (Ctrl+Q) and in the “New Project Dialog” (Ctrl+Shift+N). Both entry points will also be enabled with fuzzy search (to help automatically rectify typos), highlighted matches to your search query in the results, and improved ranking to ensure increased accuracy. 

<img class="wp-image-226112" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/08/word-image-3.gif" /> 
# What’s Next? We are continuing to integrate new and easier access to features, commands, and more through our search (Ctrl+Q) component.  These updates will be shared regularly through future blog posts and release notes. Please share any suggestions below, on developer community: https://developercommunity.visualstudio.com/, or use the hashtag #vssearch on Twitter.