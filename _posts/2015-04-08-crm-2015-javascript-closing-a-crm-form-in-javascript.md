---
layout: post
title: Microsoft Dynamics 2015 - Javascript - Closing a CRM Form in Javascript
date: 2015-04-08 08:20:16.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

<p>I had the need of adding an additional button to a form &quot;Submit and Close&quot; for business process purposes.</p>

<p>In there doing some code, in the end only needed to call to do whatever i needed:</p>

<p><span>Xrm.Page.data.entity.save(&quot;saveandclose&quot;);</span><br /></p>
<p><span><span>Xrm.Page.ui.close();</span><br /></span></p>

<p><span>However, doing that, and because i was calling the for from a Web Resource, the form was being closed but the originating web resource was appearing, the solution is simple, change the last line by:</span></p>

<p><span><span>if (parent.opener != undefined) { window.parent.close(); } else Xrm.Page.ui.close();</span><br /></span></p>

<p><span>In my perspective, it seems that CRM if has a parent.opener, just redirects to that location, even if we are calling the close of the window trough the Xrm.Page.Ui object.</span></p>

<p><span>Any thoughts, please let me know.</span></p>

<p><span>Hope is useful.</span></p>


