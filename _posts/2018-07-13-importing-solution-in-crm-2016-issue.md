---
layout: post
title: Importing Solution in Microsoft Dynamics 2016 Issue
date: 2018-07-13 00:39:16.000000000 +00:00
type: post
tag: Microsoft Dynamics 2016
---


<p><font size="2">Yesterday i was deploying to another environment a solution and the import was failing.</font></p>
<p><span style="font-size:small;background-color:transparent;"><br /></span></p>
<p><span style="font-size:small;background-color:transparent;">The error in the log file was while importing a Process:</span></p>
<p><span><font size="2">Failure</font></span></p>
<p><span><font size="2">0x80040359</font></span></p>
<p><font size="2"><span>The Microsoft Dynamics CRM record could not be created.</span></font></p>

<p><font size="2"><span>So, i went back to the solution from the other environment and i have checked what could be wrong, apparently nothing was wrong, it was a standard CRM Process with a call to a custom workflow activity, an if condition and 2 Stop Workflows statements (Success &amp; Cancelled). I double checked, yes, i was exporting in the same solution file the Workflow dll, and it has been working since ever.</span></font></p>

<p><font size="2"><span>Next, i removed the custom workflow call, tried again and nothing. What usually i do when i need some extra information, Diagtool, so I enabled the logging, checked the log file on the server and .....</span></font></p>
<p><font size="2"><span>and nothing. No more extra information to help me to see what was the problem.</span></font></p>

<p><font size="2"><span>I went back to the Process and instead of having the check box checked for &quot;Record is deleted&quot; on a Sync Process on a custom entity, i unchecked and checked the &quot;Record is created&quot;.</span></font></p>

<p><font size="2"><span>Tried to import again, and yes, it worked.</span></font></p>
<p><font size="2"><span>Did it happen to any of you? Comments are welcome.</span></font></p>

<p><font size="2"><span>Hope it helps.</span></font></p></p>

