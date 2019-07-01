---
ID: 225902
post_title: Testing upgraded QA
author: qadevblogs
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/testing-upgraded-qa/
published: true
post_date: 2019-06-13 18:46:16
---
edit 1 - visual <img class="alignnone size-full wp-image-225904" src="https://qadevblogs.wpengine.com/visualstudio/wp-content/uploads/sites/4/2019/06/8420.ping_.png" alt="" width="907" height="503" />   <pre class="lang:default mark:3,6 decode:true ">@page "/counter"

&lt;h1&gt;Counter&lt;/h1&gt;

&lt;p&gt;Current count: @currentCount&lt;/p&gt;

&lt;button class="btn btn-primary" onclick="@IncrementCount"&gt;Click me&lt;/button&gt;

@functions {
    int currentCount = 0;

    void IncrementCount()
    {
        currentCount+=1;
    }
}</pre>  