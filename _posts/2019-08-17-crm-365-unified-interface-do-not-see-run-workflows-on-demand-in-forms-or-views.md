---
layout: post
title: CRM 365 - Unified Interface - do not see Run Workflows On Demand in forms or
date: 2019-08-17 03:01:39.000000000 +00:00
type: post
tag: Microsoft Dynamics 365
---

<div>
    <div>
        <div>
            <p>Ok, again one more time Microsoft strikes again with the new release, in this case Unified Interface.</p>
            <p></p>
            <p>I just enabled the Unified Interface in one of the CRM Organizations I am working in (Sandbox) and saw a couple of strange things happening. Being System Administrator and not being able to create new records or even updating records i am the owner (entity account), already sorted, please see my previous post.</p>
            <p></p>
            <p>So, at the moment i am just uploading the new versions of my Plugins/Workflows with the latest nuget pakages from Microsoft. What was my surprise when just added a process to Run On Demand, and couldn't see the &quot;Process - Run Process&quot; on the form and grid.</p>
            <p></p>
            <p>What i did next, set to run on Create, created a record, and saw that was still working as expected. After some investigation, i have found that as an extra, we have to enable few things in the Platform Admin Center, and we need to be sure that we have as well the&nbsp;<span>Microsoft Flow license is enabled.</span></p>
            <p><span><br /></span></p>
            <p><span>What the hell??!!? The product is not supposed to work as before? At least functionality that was even not said by Microsoft that would be deprecated?</span></p>
            <p><span><br /></span></p>
            <p>The steps to follow are below:</p>
            <p></p>
            <p>1. Check if Licence is enabled</p>
            <p><span>Open https://portal.office.com/adminportal#/users and select the user<br />Click vertical … (skinny burger menu?) and select Manage product licenses<br />Expand Apps and make sure Flow for Dynamics 365 is selected</span></p>
            <p><span><br /></span></p>
            <p><span>2. Enable Microsoft Flow</span></p>
            <p><span>Enable setting to show Microsoft Flow on the forms and in the sitemap<br />Open Power platform admin center (https://aka.ms/ppac)<br />Select Environments<br />Click … (horizontal one, ugh), select Settings<br />Select Behavior<br />Make sure Show Microsoft Flow on forms and in the site map is selected</span></p>
            <p><span><br /></span></p>
            <p><span><br /></span></p>
            <p><span>Hope it helps.</span></p>
        </div>
    </div>
</div>
