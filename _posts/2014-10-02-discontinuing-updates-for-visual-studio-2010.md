---
ID: 226021
post_title: >
  Discontinuing Updates for Visual Studio
  2010
author: seroha
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/discontinuing-updates-for-visual-studio-2010/
published: true
post_date: 2014-10-02 00:00:00
---
As we work on some big changes for NuGet 3.x, we're finding that we're at a crossroads: Should we use .NET 4.5 and improve our Visual Studio UI using new features available in Visual Studio 2012, Visual Studio 2013, and Visual Studio "14"; or should we retain support for Visual Studio 2010?

Visual Studio 2010 has been supported since NuGet's introduction. But supporting it prevents us from using .NET 4.5 and since it has different visual styling from the newer versions of Visual Studio, it's holding us back on some of our new UI.

## Visual Studio 2010 Usage

In July 2013, we started capturing what version of Visual Studio was being used when a package was installed. Here's what the data shows us from then vs. now:

<table>
  <thead>
    <tr>
      <th>
        Visual Studio Version
      </th>
      
      <th>
        Usage in July 2013
      </th>
      
      <th>
        Usage in September 2014
      </th>
    </tr>
  </thead>
  
  <tbody>
    <tr>
      <td>
        Visual Studio 2010
      </td>
      
      <td>
        16%
      </td>
      
      <td>
        6%
      </td>
    </tr>
    
    <tr>
      <td>
        Visual Studio 2012
      </td>
      
      <td>
        69%
      </td>
      
      <td>
        28%
      </td>
    </tr>
    
    <tr>
      <td>
        Visual Studio 2013
      </td>
      
      <td>
        11%
      </td>
      
      <td>
        62%
      </td>
    </tr>
    
    <tr>
      <td colspan="3">
        <em>The remaining usage is spread across WebMatrix and Visual Studio "14"</em>
      </td>
    </tr>
  </tbody>
</table>

While 6% of package downloads through Visual Studio 2010 is still notable, the quick adoption of Visual Studio 2013 is impressive. We expect Visual Studio "14" to also have quick adoption.

## Discontinung Updates

If we "drop" Visual Studio 2010, here's what it would mean:

*   NuGet 3.0+ would no longer include updates to the Visual Studio 2010 NuGet extension
*   NuGet 2.8 would remain available for Visual Studio 2010 users
*   New features introduced in NuGet 3.0+ would not be available to those users
*   Packages that require new features of 3.0+ would not be installable through Visual Studio 2010
*   The nuget.org gallery would continue to work for you as it does today

At this point, we plan to move forward with this decision. We would continue updating NuGet for Visual Studio 2012, Visual Studio 2013, and Visual Studio "14".

## Objections?

If you have objections to this plan, please leave us a comment explaining why you're still using Visual Studio 2010 and why continued NuGet updates are important to you. Remember, the existing NuGet 2.8 extension would remain available to you, and nuget.org will continue to work for you, you just wouldn't be getting the latest NuGet features.