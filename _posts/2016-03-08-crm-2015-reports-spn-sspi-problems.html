---
layout: post
title: CRM 2015 - Reports - SPN / SSPI Problems
date: 2016-03-08 01:26:21.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

<p><font size="2">Running a report on CRM and if you fin an error message similar to this:</font></p>
<p><font size="2"><span></span></font></p>
<div><font size="2">If you see an error like this:</font></div>
<div><font size="2"><br /></font></div>
<div><font size="2"><i>Microsoft.ReportingServices.ReportProcessing.ReportProcessingException: Query execution failed for dataset 'DSMain'. ---&gt; Microsoft.Crm.Reporting.DataExtensionShim.Common.ReportExecutionException:<br />Microsoft.Crm.CrmException: An unexpected error occurred.<br />System.ServiceModel.Security.SecurityNegotiationException: A call to SSPI failed, see inner exception.<br />System.Security.Authentication.AuthenticationException: A call to SSPI failed, see inner exception.<br />System.ComponentModel.Win32Exception: The target principal name is incorrect ---&gt; </i></font></div>
<p><font size="2"><br /></font></p>
<p><font size="2">It means the CRM App Pool service account SPN is not configured properly and usually the fix is the one described below:</font></p>
<p><font size="2"><br /></font></p>
<p><font size="2"><span></span></font></p>
<div><font size="2">On the CRM App Server run the following commands:</font></div>
<div><font size="2"><br /></font></div>
<div>
    <font size="2">
        <i>setspn  -a  HTTP/[Crm App Server Name]  [Domain]CRMAPP_Account<br />setspn  -a  HTTP/[Crm App Server FQDN]  [Domain]CRMAPP_Account</i></p>
        <p>
    </font>
</div>
<div>
    <font size="2">
        The Crm App Server FQDN might be something like CrmAppServerName.domain.com or something slightly different, so you'll need to figure this out for your specific environment. For example, if your server name is CrmAppServer and your domain is FooDomain.local you will have something like the following:</p>
        <p><i>setspn  -a  HTTP/CrmAppServer  FooDomainCRMAPP_Account<br />setspn  -a  HTTP/CrmAppServer.FooDomain.local  FooDomainCRMAPP_Account</i></p>
        <p>After, if SQL also runs under a domain account we'll need to log onto the SQL server and run the following commands for the SQL account:
    </font>
</div>
<div><font size="2"><br /></font></div>
<div><font size="2"><i>setspn  -a  MSSQLSvc/[SQL Server Name]:1433 [Domain]SQL_Account<br />setspn  -a  MSSQLSvc/[Sql Server FQDN]:1433 [Domain]SQL_Account</i></font></div>

<p>Hope it helps.</p>
