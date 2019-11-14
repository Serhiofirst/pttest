---
ID: 226425
post_title: >
  Status on Visual Studio feature
  suggestions
author: Mads Kristensen
post_excerpt: ""
layout: post
permalink: >
  https://qadevblogs.wpengine.com/visualstudio/status-on-visual-studio-feature-suggestions/
published: true
post_date: 2019-07-31 08:00:25
---
Visual Studio receives over 500 feature suggestions from customers every month on the [Developer Community][1] website. Handling that amount is a huge effort and we’d like to share with you how we handle this volume and the steps that we take to respond to them all. What happens to suggestion tickets after they’re opened, how many make it into Visual Studio, and what happens to the rest? Let’s find out. <img class="alignnone size-full wp-image-225598" src="https://devblogs.microsoft.com/visualstudio/wp-content/uploads/sites/4/2019/06/word-image.png" alt="" width="1431" height="506" /> Let’s start with the breakdown of incoming suggestion tickets in the past 6 months and what state they are in today. We find that around 15% of the suggestions are challenging to act on, and they typically fall into the following buckets. 11% - Closed as duplicate 3% - Closed due to missing info from customer 1% - Closed because they were not suggestions for Visual Studio We do our best to follow up with customers to get more information where we can and move them into the next stage. For example, when making a suggestion to add a command to a context menu, it is important for us to know which context menu you meant. That leave us with **85%** left which are currently moving their way through the system. Here is the status of those tickets currently in our system: 40% - Closed for a number of reasons (more info below) 20% - New, not yet processed or triaged 28% - Under review and gathering votes and comments 3% - Awaiting more info from customer 3% - On roadmap (under development) 6% - Completed and released Now let’s dig in and see what’s behind those numbers. 
## From *New* to *Under Review* We have a filtering system that automatically routes incoming suggestions to the appropriate team within the Visual Studio organization. Within my team, we have established a weekly process to triage these routed suggestions and review status. The process we follow looks like this: 

1.  Does this bug belong to my team? 
    *   If not, move it to the right team
2.  Is the suggestion a duplicate of an existing suggestion? 
    *   If so, close it and transfers all votes to the original ticket (happens automatically)
3.  Does the suggestion contain all needed information? 
    *   If not, ask customer for more information
4.  Was this suggestion already completed or in active development? 
    *   If so, close it as either *Completed* or *On Roadmap*
5.  If it made it this far, mark it *Under Review* to gather votes and comments for 90 days By following these steps, most suggestions end up 

*Under Review* as we gather more data, refine any repos or requirements. These make up over a quarter of all suggestions. Every time someone adds a new comment to an existing ticket, we receive an email, so we know what’s going on with each ticket along the way, and can respond if needed. 
## Moving on from Under Review Within 90 days, we attempt to address items that are still marked 

*Under Review*. Our options are: 
1.  Mark it as *Completed* because we implemented the suggestion
2.  Mark it as On Roadmap because it’s in active development or will be very soon
3.  Close it because it didn’t get any votes and/or we’re not able to prioritize it When we implement a suggestion, we mark it 

*Completed* or *On Roadmap*. Currently, approximately ~10% of the incoming suggestions go on to be implemented or added to [the roadmap][2]. But what about the ones that don’t? 
## Reasons for closing suggestions Most suggestions are good suggestions and it’s always painful to close them. Especially because a lot of them are some that we personally would like to see implemented. As developers, you know that time and resources are finite, which means we can’t implement all suggestions. The reason we close suggestions is a mix of multiple factors, such as: 

1.  It didn’t receive any votes after 90 days as *Under Review*
2.  It got a few votes, but an implementation will not fit within our available resources
3.  It involves areas in Visual Studio that see little usage by our customers
4.  It has negative side-effects such as degraded performance, accessibility etc. Over a third of all suggestions end up closed due to one or more of the above reasons. On the positive side, even for some 

[suggestions][3] that we close, we do move the capability into an experimental extension for Visual Studio. This allows us to lower the cost of delivering a quality product investment, and where we can draw more interest from the community. 
## Suggestion completed 6% of all actionable suggestion tickets end up marked as 

*Completed*. It may not sound like much, but it is about 1 suggestion per weekday. Let that sink in. **Every single weekday, the Visual Studio engineering team implements a community submitted suggestion**. Before we implement a suggestion, we first write a spec for it if needed. Then we schedule the work item in a sprint for engineering to pick up. The implementation sometimes require work by multiple teams to coordinate, so they can each do their piece of the feature. After automated test and compliance runs have finished, it’s time for code review before the code starts its journey toward the Visual Studio master branch. More automated testing runs and finally manually testing follows. After fixing all identified bugs, the completed suggestion makes its way to a Visual Studio Preview release for user testing and stabilization. So, how do we decide to implement suggestions and how can you optimize the chances of your suggestion making it? We look at several things: 
1.  Suggestions with many votes and continuous votes over time
2.  Suggestions in areas that see lots of usage by our customers
3.  Suggestions that are easier to implement
4.  Suggestions that would improve Visual Studio’s competitive advantage
5.  Well written suggestion with all relevant information in the description A different way to think about it is to turn it around. Imagine someone wanted 

**you** to implement a feature in your product. It’s in the best interest of our product and customers to complete as many suggestions as possible, and we strive to do so. The best times are when we get to [make a lot of people happy][4] with a feature implementation based on a suggestion. 
## We <span style="text-decoration: line-through">can</span> must do better We’ve gotten feedback that this process feels like a black box. Customers feel like they don’t get a response and they don’t know the status of their suggestions. 

*After submitting a suggestion, there is no transparency into the process, and it ends up closed without any good reason 6 months later. I end up feeling frustrated and angry. I don’t want to submit another suggestion just to be ignored. *– Anonymous Visual Studio user This is not acceptable. We must do better. Some ideas that we are working on within the team are as follows. And, we welcome your feedback on what we might do more of to help you understand the process better. **First up**, we want to be much more transparent about the process. That’s exactly what this blog post aims to achieve. **Secondly**, we must be faster at responding to new suggestions. That means triaging them within the first week, so we can bring down the 20% of new untriaged suggestions to a minimum. It also means not leaving any suggestions to linger for months. This will add visibility into what is going on with the suggestions much earlier and throughout its various phases. We’ve made great progress with this in the past 6 months, but still have a bunch of open tickets to go. **Thirdly**, we need to be better at giving reasons for closing tickets. Individually written by the program manager that closed them and not an automated response. As we’re getting better at handling the vast amount of incoming suggestions, this is where we’ll focus next. 
## Feedback I hope this blog post helps shed light on the way we handle suggestion and how we plan to improve. Completing a suggestion every single weekday will hopefully encourage you to continue opening suggestion tickets. In closing, we’d really like to hear your thoughts or questions. What could we do better and what do we do well? Let us know in the comments below.

 [1]: https://developercommunity.visualstudio.com/
 [2]: https://docs.microsoft.com/visualstudio/productinfo/vs-roadmap
 [3]: https://developercommunity.visualstudio.com/comments/653361/view.html
 [4]: https://developercommunity.visualstudio.com/comments/586372/view.html