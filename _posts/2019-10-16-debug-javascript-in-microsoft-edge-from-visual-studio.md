---
ID: 226659
post_title: >
  Debug JavaScript in Microsoft Edge from
  Visual Studio
author: Zoher Ghadyali
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/debug-javascript-in-microsoft-edge-from-visual-studio/
published: true
post_date: 2019-10-16 11:00:34
---
As you may know, the next version of Microsoft Edge will adopt the Chromium open source project to create better web compatibility and less fragmentation of different underlying web platforms. **If you haven’t already, you can try out preview builds of Microsoft Edge from **[**https://www.microsoftedgeinsider.com**][1]** which is now available on Windows 10, 8.1, 8, 7, and macOS!** With Visual Studio today, you can already debug JavaScript running in the current version of Microsoft Edge, built on top of the EdgeHTML web platform. Starting with Visual Studio 2019 version 16.2, we’ve extended support to the preview builds of Microsoft Edge, which leverage Chromium. **Head to [visualstudio.com/downloads/][2] to download the latest Visual Studio now!** [caption id="attachment_226739" align="aligncenter" width="640"]<img class="wp-image-226739 size-large" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/featured_image-1024x310.png" alt="Visual Studio hearts Microsoft Edge" width="640" height="194" /> Visual Studio now supports debugging JavaScript running in Microsoft Edge![/caption]   
# Create a new ASP.NET Core Web Application You can now debug JavaScript in Microsoft Edge for your ASP.NET Framework and ASP.NET Core applications. To try out this feature, let’s start by creating a new ASP.NET Core Web Application. [caption id="attachment_226741" align="aligncenter" width="1792"]

<img class="wp-image-226741 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/0.png" alt="Screenshot of the &quot;Create a new project&quot; dialog in Visual Studio" width="1792" height="1243" /> Create a new project in Visual Studio and select ASP.NET Core Web Application.[/caption]   To show off support for debugging JavaScript, we’ll use the React.js template which shows you how to integrate React.js with an ASP.NET Core application. Once your project has been created, open **ClientApp/src/App.js** which you’ll see is a React component for our app.   
# Using JavaScript to calculate the Fibonacci sequence Let’s assume that as part of this app, a user will input the term in the Fibonacci sequence they want to know and our client-side JavaScript code will be responsible for calculating it and displaying the result to the user. The Fibonacci sequence is a series of numbers where each number is the sum of the two preceding ones, starting with 0 and 1. 

<table style="border-collapse: collapse;width: 100%;height: 54px">
  <tbody>
    <tr style="height: 27px">
      <td style="width: 12.5%;height: 27px;text-align: left">
        <strong>Position</strong>
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        1
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        2
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        3
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        4
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        5
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        6
      </td>
      
      <td style="width: 6.25%;height: 27px;text-align: left">
        7
      </td>
    </tr>
    
    <tr style="height: 27px">
      <td style="width: 12.5%;height: 27px;text-align: left">
        <strong>Value</strong>
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        0
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        1
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        1
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        2
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        3
      </td>
      
      <td style="width: 12.5%;height: 27px;text-align: left">
        5
      </td>
      
      <td style="width: 6.25%;height: 27px;text-align: left">
        8
      </td>
    </tr>
  </tbody>
</table>   To handle this calculation, let’s create a new Fibonacci component and add it to our app. Start by modifying 

**App.js** to import our soon-to-be-created Fibonacci component and route to it: <pre class="lang:js decode:true" title="Modifying app.js">import React, { Component } from 'react';
import { Route } from 'react-router';
import { Layout } from './components/Layout';
import { Home } from './components/Home';
import { FetchData } from './components/FetchData';
import { Counter } from './components/Counter';
import { Fibonacci } from './components/Fibonacci';

export default class App extends Component {
  displayName = App.name

  render() {
    return (
      &lt;Layout&gt;
        &lt;Route exact path='/' component={Home} /&gt;
        &lt;Route path='/counter' component={Counter} /&gt;
        &lt;Route path='/fetchdata' component={FetchData} /&gt;
        &lt;Route path='/fibonacci' component={Fibonacci} /&gt;
      &lt;/Layout&gt;
    );
  }
}
</pre> Now that our app will handle routing the 

`/fibonacci` endpoint, let’s modify the **NavMenu** to navigate to that endpoint. Open **ClientApp/src/components/NavMenu.js **and add this **LinkContainer** component at line 36: <pre class="lang:js decode:true">&lt;LinkContainer to={'/fibonacci'}&gt;
  &lt;NavItem&gt;
    &lt;Glyphicon glyph='alert' /&gt; Fibonacci
  &lt;/NavItem&gt;
&lt;/LinkContainer&gt;</pre> before the 

`</Nav>` tag. Now, you’ll be able to easily test our new `/fibonacci` route from the **NavMenu**. Finally, let’s create our Fibonacci component. Create a new JavaScript file (**Ctrl**+**N**) and save it as **Fibonacci.js** in the **ClientApp/src/components/** folder. Add the code below to your new component: <pre class="lang:js decode:true">import React, { Component } from 'react';

export class Fibonacci extends Component {
  displayName = Fibonacci.name

  constructor(props) {
    super(props);
    this.state = {
      n: 8,
      f_n: null,
    };
    this.calculateFibonacci = this.calculateFibonacci.bind(this);
  }

  calculateFibonacci() {
    var f_0 = 0;
    var f_1 = 1;
    for (var i = 3; i &lt; this.state.n; i++) {
      var f_2 = f_0 + f_1;
      f_0 = f_1;
      f_1 = f_2;
    };
    this.setState({
      f_n: f_2
    })
    console.log("The " + i.toString() + "th Fibonnaci number is:", f_2);
  }
		
  render() {
    return (
      &lt;div&gt;
        &lt;h1&gt;Fibonacci&lt;/h1&gt;
        &lt;p&gt;This is a simple example of a React component.&lt;/p&gt;
        &lt;p&gt;The {this.state.n}th Fibonacci number is: &lt;strong&gt;{this.state.f_n}&lt;/strong&gt;&lt;/p&gt;
        &lt;button onClick={this.calculateFibonacci}&gt;Calculate&lt;/button&gt;
      &lt;/div&gt;
    );
  }
}
</pre> Eventually, we’ll add a form to the render function for the user to supply 

`n`, the variable we’re using to represent the term in the Fibonacci sequence that they want to know. For now, just to test our logic, we’ll assume that the user wants to know what the 8<sup>th</sup> term in the sequence is, which is 13. Let’s build our app in the new Microsoft Edge to see if our code is calculating the right answer. If you don’t have it installed already, head to [https://www.microsoftedgeinsider.com][1] to download the preview builds of Microsoft Edge. In Visual Studio, click the dropdown next to **IIS Express** and select the version of Microsoft Edge (Beta, Dev, or Canary) that you have installed. If you don’t see Microsoft Edge Beta, Dev or Canary in the dropdown, you may need to restart Visual Studio. [caption id="attachment_226745" align="alignnone" width="2256"]<img class="size-full wp-image-226745" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/1-1.png" alt="Screenshot of Visual Studio, selecting the Microsoft Edge Dev browser to launch" width="2256" height="1446" /> Select Microsoft Edge Beta, Dev, or Canary for Visual Studio to launch[/caption] Now click the green **Play** button or press **F5** on your keyboard. Visual Studio will start your web application and Microsoft Edge will automatically launch and navigate to your app. [caption id="attachment_226746" align="alignnone" width="2256"]<img class="wp-image-226746 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/2.png" alt="Screenshot of the app in Microsoft Edge" width="2256" height="1434" /> Your app is successfully running in Microsoft Edge![/caption] You’ll see the entry we added for our Fibonacci component in the **NavMenu** on the left. Click on **Fibonacci**. [caption id="attachment_226747" align="alignnone" width="2256"]<img class="size-full wp-image-226747" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/3.png" alt="A screenshot of the Fibonacci component we added in Microsoft Edge" width="2256" height="1434" /> Microsoft Edge is showing the Fibonacci component we added[/caption] Now click the **Calculate** button. [caption id="attachment_226748" align="alignnone" width="2256"]<img class="size-full wp-image-226748" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/4.png" alt="Screenshot of Microsoft Edge where our Fibonacci component calculated the 8th term in the sequence as 8" width="2256" height="1434" /> Our Fibonacci component is calculating the 8th term in the sequence as 8[/caption] We know that the 8<sup>th</sup> term should be 13 but our code is saying that the 8<sup>th</sup> Fibonacci number is 8! 
# Debugging JavaScript in Visual Studio Switching back to Visual Studio, since our 

**calculateFibonacci()** function prints to the Console, you can actually see that log in the Debug Output. [caption id="attachment_226749" align="alignnone" width="2256"]<img class="size-full wp-image-226749" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/5.png" alt="Screenshot of Visual Studio with our console.log statement shown in the Debug Output" width="2256" height="1446" /> You can see console.log statements from your client-side JavaScript code in Visual Studio's Debug Output[/caption] To figure out where our code is going wrong, let’s set a breakpoint on Line 19 inside the for loop in Visual Studio. We’ll start by checking if our code is calculating the 3<sup>rd</sup> and 4<sup>th</sup> terms in the Fibonacci sequence correctly. Click the **Restart** button next to the Stop button or press **Ctrl**+**Shift**+**F5** to bind the breakpoint and start debugging. **Note**: If you have not enabled JavaScript debugging before, your JavaScript breakpoint will not bind successfully. Visual Studio will ask if you want to enable JavaScript debugging and then restart the debugging process and bind your breakpoint. Click **Enable JavaScript Debugging (Debugging Will Stop and Restart)**. [caption id="attachment_226751" align="alignnone" width="2256"]<img class="size-full wp-image-226751" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/6.png" alt="Screenshot of Visual Studio asking if you want to enable JavaScript debugging" width="2256" height="1446" /> Click "Enable JavaScript Debugging" and Visual Studio will restart debugging[/caption] We know that the first two terms in the Fibonacci sequence are 0 and 1. The third term should also be 1. Switch from the **Output** view to **Watch 1** and add `f_2`, `f_1`, and `f_0` to watch. This is what Visual Studio should look like now: [caption id="attachment_226753" align="alignnone" width="2256"]<img class="size-full wp-image-226753" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/7.png" alt="Screenshot of Visual Studio with a breakpoint set on Line 19 in Fibonacci.js and f_0, f_1, f_2 added to Watch 1" width="2256" height="1446" /> Visual Studio is paused at Line 19 in Fibonacci.js and you can see the values of f_0, f_1, and f_2 in Watch 1[/caption] Click the **Step Over** button or press **F10**. You will now see that our code correctly calculated the third Fibonacci number, 1, as the value of f_2. <table style="border-collapse: collapse;width: 100%;height: 54px">
  <tbody>
    <tr style="height: 27px">
      <td style="width: 12.5%;height: 27px;text-align: left">
        <strong>Position</strong>
      </td>
      
      <td style="width: 7.08545%;height: 27px;text-align: left">
        3
      </td>
      
      <td style="width: 17.9146%;height: 27px;text-align: left">
        4
      </td>
    </tr>
    
    <tr style="height: 27px">
      <td style="width: 12.5%;height: 27px;text-align: left">
        <strong>Value</strong>
      </td>
      
      <td style="width: 7.08545%;height: 27px;text-align: left">
        1
      </td>
      
      <td style="width: 17.9146%;height: 27px;text-align: left">
        2
      </td>
    </tr>
    
    <tr>
      <td style="width: 12.5%;text-align: left">
        <strong>Did our function compute this term correctly?</strong>
      </td>
      
      <td style="width: 7.08545%;text-align: left">
        <img class="wp-image-226704" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/checkmark-5.png" alt="Checkmark" width="87" height="87" />
      </td>
      
      <td style="width: 17.9146%;text-align: left">
      </td>
    </tr>
  </tbody>
</table> Let’s keep stepping to see if there’s a bug somewhere else in the loop. 

**Step Over** two more times and you should see both `f_0` and `f_1` are now equal to 1, which they need to be to calculate the 4<sup>th</sup> term in the sequence. You will now see that our code is paused at Line 18. Let’s add `i` to our watch as it will tell us which term we’re computing in the Fibonacci sequence. **Step Over** one more time and you’ll see that the value of `i` is now 4. Now the code is checking to see if the value of `i` is less than `n`, the variable we’re using to represent which term in the Fibonacci sequence we’re trying to find. In this example, we’ve hardcoded `n` as 8 since we’re trying to calculate the 8<sup>th</sup> term in the sequence. Since 4 < 8, **step over** again and we’ll continue looping. **Step Over** now and you should see that `f_2` is now 2, and since `i` is 4, we know that our code has successfully computed the 4<sup>th</sup> term in the Fibonacci sequence as 2. <table style="border-collapse: collapse;width: 100%;height: 54px">
  <tbody>
    <tr style="height: 27px">
      <td style="width: 12.5%;height: 27px;text-align: left">
        <strong>Position</strong>
      </td>
      
      <td style="width: 7.08545%;height: 27px;text-align: left">
        3
      </td>
      
      <td style="width: 17.9146%;height: 27px;text-align: left">
        4
      </td>
    </tr>
    
    <tr style="height: 27px">
      <td style="width: 12.5%;height: 27px;text-align: left">
        <strong>Value</strong>
      </td>
      
      <td style="width: 7.08545%;height: 27px;text-align: left">
        1
      </td>
      
      <td style="width: 17.9146%;height: 27px;text-align: left">
        2
      </td>
    </tr>
    
    <tr>
      <td style="width: 12.5%;text-align: left">
        <strong>Did our function compute this term correctly?</strong>
      </td>
      
      <td style="width: 7.08545%;text-align: left">
        <img class="wp-image-226704" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/checkmark-5.png" alt="Checkmark" width="87" height="87" />
      </td>
      
      <td style="width: 17.9146%;text-align: left">
        <img class="wp-image-226704" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/checkmark-5.png" alt="Checkmark" width="87" height="87" />
      </td>
    </tr>
  </tbody>
</table> We could keep stepping over and over again until we find the problem but since we’ve already proven that we’re calculating the 3

<sup>rd</sup> and 4<sup>th</sup> terms in the Fibonnaci sequence correctly, let’s jump ahead to the 7<sup>th</sup> term since it’s the last term we calculate before we see the bug. 
# Using a conditional breakpoint to jump ahead in the for loop Stop debugging for now by clicking the 

**Stop** button or pressing **Shift**+**F5**. Right click your breakpoint and select **Conditions…** or press **Alt**+**F9**. This will allow us to set a condition for our breakpoint and we’ll only break when that condition is true. [caption id="attachment_226755" align="alignnone" width="2256"]<img class="wp-image-226755 size-full" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/8.png" alt="Screenshot of Visual Studio, adding a condition to the breakpoint you set on Line 19" width="2256" height="1446" /> You can add a condition to a breakpoint and that means you will only break execution when that condition is true.[/caption] Enter `i == 7` as the condition we want to break on, which means we’ll only break in the last loop before we see the bug. Start your web app again by clicking the green **Play** button or pressing **F5**. This time, we’ll break only when `i` is 7. Here’s what Visual Studio looks like now: [caption id="attachment_226757" align="alignnone" width="2256"]<img class="size-full wp-image-226757" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/9.png" alt="A screenshot of Visual Studio, breaking on line 19 in Fibonacci.js when i is 7" width="2256" height="1446" /> With the conditional breakpoint, we only break when i is 7[/caption] **Step over** once and you will see that we’ve calculated the 7<sup>th</sup> term in the Fibonacci sequence correctly since `f_2` is equal to 8. **Step over** three times and we’ll now be paused at `i < n`. Since `i` is now 8, `i < n` actually evaluates to false which means we’re going to break out of the loop. We’ve found the bug: we aren’t going through the loop to calculate the 8<sup>th</sup> Fibonacci number! We can fix this bug by changing the **calculateFibonacci()** function to: <pre class="lang:js decode:true">calculateFibonacci() {
  var f_0 = 0;
  var f_1 = 1;
  for (var i = 3; i &lt;= this.state.n; i++) {
    var f_2 = f_0 + f_1;
    f_0 = f_1;
    f_1 = f_2;
  };
  this.setState({
    f_n: f_2
  })
  console.log("The " + (i - 1).toString() + "th Fibonnaci number is:", f_2);
}</pre> Now when 

`i` is 8, we’ll actually go through the for loop since since 8 <= 8. Remove the breakpoint, click the **Restart** button next to the Stop button or press **Ctrl**+**Shift**+**F5**. Click on **Fibonacci** in the **NavMenu** and click on the **Calculate** button to see that we’ve correctly calculated the 8<sup>th</sup> term in the Fibonacci sequence as 13! We did it! [caption id="attachment_226758" align="alignnone" width="2256"]<img class="size-full wp-image-226758" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/10.png" alt="A screenshot of your app in Microsoft Edge, correctly calculating the 8th Fibonacci term as 13" width="2256" height="1434" /> Your app in Microsoft Edge correctly calculated the 8th Fibonacci term as 13![/caption]   
# Attaching to Microsoft Edge So far in this post, we’ve been using the green 

**Play** button in Visual Studio to build our web application, launch Microsoft Edge, and automatically have Edge navigate to our app. Starting in Visual Studio 2019 version 16.3 Preview 3, you can now attach the Visual Studio debugger to an already running instance of Microsoft Edge. First, ensure that there are no running instances of Microsoft Edge. Now, from your terminal, run the following command: start msedge --remote-debugging-port=9222 From Visual Studio, open the **Debug** menu and select **Attach to Process** or press **Ctrl**+**Alt**+**P**. <img class="wp-image-226727" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/a-screenshot-of-a-computer-description-automatica-11.png" alt="A screenshot of a computer Description automatically generated" /> From the **Attach to Process** dialog, set **Connection type **to **Chrome devtools protocol websocket (no authentication)**. In the **Connecting target** textbox, type in <http://localhost:9222/> and press **Enter**. You should see the list of open tabs you have in Microsoft Edge listed out in the **Attach to Process** dialog. <img class="wp-image-226730" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/a-screenshot-of-a-computer-screen-description-aut-19.png" alt="A screenshot of a computer screen Description automatically generated" /> Click **Select…** and check **JavaScript (Microsoft Edge - Chromium)**. You can add tabs, navigate to new tabs, and close tabs and see those changes reflected in the **Attach to Process** dialog by clicking the **Refresh** button. Select the tab you want to debug and click **Attach**. The Visual Studio debugger is now attached to Microsoft Edge! You can pause execution of JavaScript, set breakpoints, and see `console.log()` statements directly in the Debug Output window in Visual Studio. 
# Conclusion To recap: 

*   We created an ASP.NET Core web application in Visual Studio 2019 version 16.2 and built it in a preview build of Microsoft Edge
*   We added a new component to our web application that contained a bug
*   We found the bug by setting breakpoints and debugging our web app running in Microsoft Edge from Visual Studio!
*   We showed you how to attach the Visual Studio debugger to an existing instance of Microsoft Edge We’re eager to learn more about how you work with JavaScript in Visual Studio! Please send us feedback by clicking the Feedback icon in Visual Studio or by tweeting 

[@VisualStudio and @EdgeDevTools][3]. <img class="wp-image-226733" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/10/a-close-up-of-a-screen-description-automatically-3.png" alt="A close up of a screen Description automatically generated" />

 [1]: https://www.microsoftedgeinsider.com/
 [2]: http://visualstudio.com/downloads
 [3]: https://twitter.com/intent/tweet?text=@VisualStudio+@EdgeDevTools