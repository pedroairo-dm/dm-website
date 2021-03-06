---
layout: post
title: CRM 365 - Business Process Flow - Jump between stages
date: 2018-01-25 08:23:39.000000000 +00:00
type: post
tag: Microsoft Dynamics 365
---

<p>The moment when something stops to work without any changes of any type. </p>
<p>As it happened with me, i know it happened with many developers/customers more.</p>
<p>And as i got really annoyed more people got different feelings as well.</p>
<p></p>
<p>I will explain now what is the issue, in the opportunity entity it seemed the best for the client to use a Business Process Flow to help with a standard process, that is always a good idea, so that was developed against the Opportunity entity.</p>
<p></p>
<p>Everything was going great with the process, and then because of an exception we had to implement something that would allow to Jump from any stage to any stage, so, assuming the Business Process Flow had branches as well, thing could get more complicated. The solution was easy enough, implementing a &quot;On Demand Process&quot; that would change the Stage Id to the one necessary. Until that moment, everything was working with no issues.</p>
<p></p>
<p>However, at some stage, Microsoft just decided that the way the Business Process Flow was implemented was not the best/great, whatever....</p>
<p></p>
<p>What happened, or at least i understood from phone calls with Microsoft was, new tables were created for the purpose and a field &quot;traversedpath&quot; was about to become the Star of that.</p>
<p></p>
<p>Now let me explain what is the traversedpath. Traversedpath is a string field that contains all the guids of every stage until from the first until the current appended with the ',' comma. Trying to be on the brilliant minds that came to that for me it makes sense, so, what's the problem in here? Basically, opportunities created before the Update 9.0 (if i'm not mistaken). </p>
<p></p>
<p>Everything seemed to work apparently at the beginning, people creating new Opportunity records, and playing around the stages, and jumping sometimes from the first stage to the last one, everything seemed to work more or less.</p>
<p></p>
<p>But, when people started to play around old opportunities, things started to become a nightmare, and now, believe in me, when you have a CRM implementation with many opened opportunities and everybody started to complain about that, then you starting to fill mad(here i don't want to put the name of my actual feeling, could be to strong).</p>
<p></p>
<p>What you do next, with no clue at all, you start to try things, to google and when you find that you not alone, you think, at least i'm not the only one, however, not me, i just thought, not again....</p>
<p></p>
<p>So Microsoft was called for that, and after few hours, something was becoming more clear, but even the code provided was not working 100% for the purpose, then i just tried few more things and i saw some improvements in the tests from the Test team and as well from the Client, scenarios were put on the table and tested in the Sandbox environment.</p>
<p></p>
<p>You can guess what happened, finally production environment was upgraded and then, with a full team of users using the system, more scenarios came into and more problems......</p></p>
<p></p>
<p>At that moment, and because is a Show Stopper, Microsoft was called again and few more experiences were tried, but at the end nothing conclusive, again i tried few more things and at the moment i believe that i'm really close to the end of the problems, but not 100% sure.</p>
<p></p>
<p>In the Custom Workflow Activity developed first thing done is getting the full path (all stages from the 1st until the current one) and update the opportunity before doing the actual jump of the stage. Below some code that can be seen as example:</p>
<p></p>
<p><span><font color="#0004ff" size="2">Opportunity _opportunityToUpdate = new Opportunity();<br />_opportunityToUpdate.Id = opportunityId;</font></span></p>
<p><span><font color="#0004ff" size="2"><span> //all the guids should be appended in here from the 1st until the current stage</span><br />_opportunityToUpdate.TraversedPath = traversedPath;<br />_opportunityToUpdate.StageId = currentStageId;<br />_opportunityToUpdate.ProcessId = process.WorkflowId;<br />service.Update(_opportunityToUpdate);</font></span></p>
<p></p>
<p>I have tried to update the opportunity with the newStageId and the traversedpath to the new stage with no luck.</p>
<p></p>
<p>And then my solution, probably not the prettiest one, but it works:&nbsp;</p>
<p>Going one by one from the current until the one we need.</p>

<p>Hope it helps.</p>
