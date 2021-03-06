---
layout: post
title:  Dynamics 365 -┬áBusiness Process Flow
date: 2017-08-04 05:09:36.000000000 +00:00
type: post
tag: Microsoft Dynamics 365
---
<p>This is a nice to have to guide users in terms of filling information based on stages, for instance:</p>
<p>The information needed to a contact to be a prospect, probably we only need First Name, Last Name and mobile phone. On the other hand, to become an opportunity, we will need some more details.</p>

<p>In this situation i would use this kind of approach, Business Process, because it will be really easy to see by opening the record in which phase of the process the contact is only by looking to the process bar. </p>

<p>However, using this feature of CRM can be sometimes a little bit disappointing because customizing what the fields do (hiding based on rules, setting required based on others is not possible), i mean, configuring only with the CRM default functionality is not possible.</span></p>

<p>My personal opinion and because i've been working with CRM on my last 13 years already, using Javascript for this purposes it can be a nightmare in terms of Upgrades of the product.</p>

<p>But, because sometimes you get to a point where a system is already implemented and you don't have the time to redesign the feature, one thing i have to say, just customize with an approach of having some constants with the name of the field, and not use hard-coded all-around.</p>
<p>With this, if the DOM changes, you will need to change the new name only in one place, instead of in all the places you have been using this.</p>

<p>For this example i will give few lines of Javascript that can be used to Hide the next stage button on the Process flow, set the required level of a field and set the field readonly.</p>

<p>var probabilityHeaderFieldName = &quot;<span>header_process_new_probability_1&quot;;</span></p>
<p><span>//to set required</span></p>
<p><span><span>Xrm.Page.getControl(<span>probabilityHeaderFieldName </span>).getAttribute().setRequiredLevel(&quot;required&quot;);</span><br /></span></p>
<p><span>//to set readonly</span></p>
<p><span><span>Xrm.Page.getControl(<span>probabilityHeaderFieldName&nbsp;</span>).setDisabled(true);</span><br /></span></p>
<p><span>//to hide the next stage button</span></p>
<p><span><span>var nextStageButtonName = &quot;<span>stageAdvanceActionContainer</span>&quot;;</span><br /></span></p>
<p><span><span>document.getElementById(<span>nextStageButtonName&nbsp;</span>).style.visibility = 'hidden';</span><br /></span></p>
<p><span><br /></span></p>
<p>Microsoft URL for the Business Process Flow, <a href="https://www.microsoft.com/en-us/Dynamics/crm-customer-center/create-a-business-process-flow.aspx" rel="nofollow" target="_self" title="click here">click here</a>.</p>

<p><span>Hope it helps.</span></p>
