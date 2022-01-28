---
layout: post
title: CRM 2015 - How to change max number of records per collection
date: 2016-03-09 00:57:56.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p><font size="2">Not the best thing to do in terms of performance probably, but if you need to increase the max number of records per collection, i.e: Rest call to get records and render as a table in a custom page, by default it will bring 50, to increase run the next sql statement in the MSCRM_CONFIG database:</font></p>
<p></p>
<p><span><font size="2"><i>update ServerSettingsProperties<br />set IntColumn = 250 <br />where ServerSettingsProperties.ColumnName = 'MaxResultsPerCollection'</i></font></span></p>
