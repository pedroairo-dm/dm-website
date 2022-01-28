---
layout: post
title: Import CRM Dynamics 2015 Managed Solution - Exceeded Content Size
date: 2015-11-24 02:09:15.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p>I was importing a CRM Managed Solution and the import failed with the following error:</p>

<p><span>&quot;The assembly content size '8399872 bytes' has exceeded the maximum value allowed for isolated plug-ins '8388608 bytes'.&quot;</span><br /></p>

<p><span>I know you can argue that even for a dll can be to much and it was something Microsoft was trying to avoid, however sometimes can really happen. To overcome this issue, a key on the [DeploymentProperties] table can be updated to a bigger value.</span></p>

<p><span>With me the problem was the utilization of an external dll that i used for some testing, totally forgot to remove the reference.</span></p>

<p><span>But, if in anytime someone has to use a dll that has more than 8.192 of size, the default of CRM, the following sql query can override that value for a bigger value.</span></p>

<p><span><span>update [MSCRM_CONFIG].[dbo].[DeploymentProperties]<br />SET [IntColumn] = 16384<br />WHERE [ColumnName] = 'SandboxClientMaxAssemblySizeInKByte'</span><br /></span></p>

<p><span>Hope it helps.</span></p>
<p></p>
