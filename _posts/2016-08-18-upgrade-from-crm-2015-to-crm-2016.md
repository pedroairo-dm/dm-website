---
layout: post
title: Upgrade from CRM 2015 to CRM 2016
date: 2016-08-18 02:39:31.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015/2016
---

<p>Upgrade from CRM 2015 to CRM 2016 <span>On premise</span></p>

<p>Yesterday was one of those days that i really like to have, i know, sometimes can be really frustrating because of some problems you have to go trough when performing an upgrade.</p>

<p>I have performed many upgrades since CRM v1.2 and it is always a challenge, for more tests in other environments, when it is to Production, something new will happen, yesterday was not exception.</p>

<p>In a virtual machine just performed the Upgrade, it was really quick and no trouble.</p>

<p>As planned, after hours we just performed the Upgrade in Production with all the scenarios covered in our checklist, almost in the end of the Upgrade, it was on the same step for almost 1 hour (<span><u>Enabling Read Committed Snapshot Isolation for organization</u></span>).</p>

<p>After some investigation about what could be the cause of that, my colleague just killed the process in the SQL Server. Than it appeared on the CRM Setup screen a message that was more clear to us, &quot;<span><u>The operation cannot be performed on database &quot;XPTO_MSCRM&quot; because it is involved in a database mirroring session or an availability group. Some operations are not allowed on a database that is participating in a database mirroring session or in an availability group.</u></span>&quot;. </p>


<p>At that moment, we understood why the setup didn't go from the same step for that long, my question in here is: Why the setup didn't throw an exception before? It was necessary kill the process that was performing that action in the SQL Server.</p>

<p>So, we just removed the database mirroring, and the setup finished successfully. </p>

<p>Hope it helps.</p>

