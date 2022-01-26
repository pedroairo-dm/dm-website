---
layout: post
title: CRM 2015 oData Vs CRM 2016 Web API - Part 2 - Setting a Lookup Field with NULL
date: 2016-04-25 06:53:57.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015/2016
---

<p><font size="2">On the subject of <span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">CRM 2015 oData Vs CRM 2016 i will be posting the main </span>differences that i have found when upgrading my client code to CRM 2016 Web API.</font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;"><br /></span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">I could start with the methods (Create, Update, Retrieve,....), however, those things are easier to find in the SDK than this specific one.</span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;"><br /></span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">Previously you could already use a method called Disassociate to set a lookup field to null, but that </span>involves<span style="line-height:1.8;"> an additional call for each one of the fields to update. So, i can imagine that you would be doing something similar to:</span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">var account = {};</span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">account.primarycontactid = null;</span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;"><br /></span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">XRM.Rest.Update(account, &quot;accountSet&quot;, ...,...,...);</span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;"><br /></span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">Don't mind with the (...) on the method call, in my case i have a generic class to expose the Odata Organization Functionalities, <u>the point in here is how easy was to set the field to null</u>.</span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;"><br /></span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">Now with CRM 2016, because we have those lookups as Navigation Properties (please, see my previous post about Navigation Properties on CRM 2016 Web API), to be able to perform the same operation, we need to call the Disassociate method, in my case:</span></font></span></font></p>
<p></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;"><span> Xrm.WebAPI.Disassociate(accountid, &quot;accounts&quot;, &quot;&quot;, &quot;<span>primarycontactid</span>&quot;,<br />                        SuccessCallBack,<br />                        ErrorHandler, false);</span><br /></span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;"><br /></span></font></span></font></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">Where the first parameter is the id of the account, the second is the type &quot;accounts&quot; and the forth one is the field to set up as null (remove the relation between those two entities.)</span></font></span></font></p>
<p></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#383838"><span style="line-height:1.8;">Hope it helps</span></font></span></font></p>
