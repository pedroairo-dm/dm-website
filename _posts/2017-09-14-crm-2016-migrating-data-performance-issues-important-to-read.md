---
layout: post
title: Microsoft Dynamics 2016 - Migrating Data Performance Issues (Important to read)
date: 2017-09-14 09:05:35.000000000 +00:00
type: post
tag: Microsoft Dynamics 2016
---
<p>I'm the kind o person that really likes to do Migration and Integration tasks into and from CRM.</p>

<p>Last time this happened to me i forgot to mention in here, and probably most of you already know, if no, just spend few minutes reading this.</p>

<p>I was importing some data into CRM 2016, the same applies to CRM 2015 and only for creating the Account entity records (few data fields filled) it was giving an average of 1.5 sec for each one. That's really an issue when you need to import thousands or millions of records, if you migrate or integrate only few hundred, you wouldn't loose time trying to understand why.</p>

<p>However, i'm really stubborn, so i had to figure out why.</p>

<p>What would you do at first? First you would question yourself, do i have any PrePlugin or Post-Plugin that would affect the performance? If yes, let's try to deactivate those steps and check if the performance is better.</p>

<p>I have to tell that i didn't have any plugin either Pre or Post Sync that would affect the performance, but then i remembered that CRM 2015 and CRM 2016 usually comes with the <u>Activity Feeds Plugins activated</u>. And that was the real problem, after deactivating them, instead of 1.5 sec in average it gave 80 ms (milliseconds).</p>

<p> My question is why Microsoft ??!!?!??!!? Leave those deactivated and let the partners or developers ask to the customer if they really need that active. </p>

<p>I wouldn't mind at all to leave active if it wouldn't give any kind of performance problems, but it is not the case, it really gives.</p>
