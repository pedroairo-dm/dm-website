---
layout: post
title: Issues connecting to CRM 365 from IIS only
date: 2018-11-07 10:50:21.000000000 +00:00
type: post
tag: Microsoft Dynamics 365
---

<p><font size="2">Everything working with no issues with the latest Nuget Packages for CRM trough a console application when connecting to CRM 365.</font></p>
<p><font size="2"><br /></font></p>
<p><font size="2">Now, we had to promote a service that is currently working and has been working already for long time to consume CRM 365 data to work with the new CRM ddls.</font></p>
<p><font size="2"><br /></font></p>
<p><font size="2">We added the dlls trough nuget packages, everything compiling but when this next line was called:</font></p>
<p><font size="2"><span><u>OrganizationServiceProxy serviceProvider = new OrganizationServiceProxy(config.OrganizationUri,<br />&nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp;config.HomeRealmUri, config.Credentials, config.DeviceCredentials);</u></span><br /></font></p>
<p><font size="2"><span><br /></span></font></p>
<p><font size="2">We were having this next exception:</font></p>
<p><font size="2"><u><span>Metadata contains a reference that cannot be resolved: 'https://crm.domain/XRMServices/2011/Organization.svc?wsdl&amp;sdkversion=9.0'.</span><br /></u></font></p>
<p><font size="2"><span><br /></span></font></p>
<p><font size="2"><span>After some research we found that the solution would be before calling this line, call first:</span></font></p>
<p><font size="2"><span><span><u>ServicePointManager.SecurityProtocol = SecurityProtocolType.Tls12;</u></span><br /></span></font></p>
<p><font size="2"><span><br /></span></font></p>
<p><font size="2"><span>I will investigate more when i have some spare time.</span></font></p>
<p><font size="2"><span>Hope it helps.</span></font></p>
