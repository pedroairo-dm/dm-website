---
layout: post
title:  Microsoft Dynamics 2015 Online Update 1 - {Javascript Code Example 3} - Sub-grid controls
date: 2015-10-16 05:49:31.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p>With Update 1 for CRM 2015 Online more events and objects are available, before this update, only the refresh was available. </p>

<p>Now it is possible to interact with grid-controls to get the number of total records, getting the object grid so can be worked as an object, it is possible as well to get all rows or even selected rows from the grid only.</p>

<p>I would say that mostly i would use the grid object on the purpose of getting either all rows or selected rows, however it is possible to extend to more functionalities.</p>

<p>As an example i leave below few lines of code to access the grid from javascript:</p>
<p><span style="background-color:transparent;line-height:1.8;"><br /></span></p>
<p><span style="background-color:transparent;line-height:1.8;">Iterating trough the grid as an array:</span></p>
<p><span style="background-color:transparent;line-height:1.8;"> </span><span style="background-color:transparent;line-height:1.8;"><i>var allGridRowData = []; </i></span></p>
<p><span style="background-color:transparent;line-height:1.8;"><i>var rows = Xrm.Page.getControl(&quot;Contacts&quot;).getGrid().getRows();</i></span></p>
<p><span style="background-color:transparent;line-height:1.8;"><i> rows.forEach(function (row, i) { </i></span></p>
<p><span style="background-color:transparent;line-height:1.8;"><i>    allGridRowData.push(row.getData()); </i></span></p>
<p><span style="background-color:transparent;line-height:1.8;"><i>});</i></span><br /></p>
