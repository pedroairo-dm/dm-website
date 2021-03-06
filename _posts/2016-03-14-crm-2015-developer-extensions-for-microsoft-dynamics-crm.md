---
layout: post
title: CRM 2015 - Developer extensions for Microsoft Dynamics CRM
date: 2016-03-14 04:21:15.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

<p><font size="2">Developer Extensions is a set of tools provided in the SDk that intendes to <span>simplify and accelerate development. Usually to be used in Client apps, something like Portals.</span></font></p>
<p><span><font size="2"> It provide <span>the following capabilities:</span></font></span></p>
<p><font size="2"><span></span></font></p>
<ul>
    <li><font size="2">Simplified connection to CRM servers provided by the <a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.client.crmconnection.aspx">CrmConnection</a> class (<a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.client.aspx">Microsoft.Xrm.Client</a>)<br /></font></li>
    <li><font size="2">Code generation of strong types provided by customizations to the code generation tool (CrmSvcUtil.exe)<br /></font></li>
    <li><font size="2">App.config and Web.config configurability for enabling custom extensions provided by the <a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.client.configuration.crmconfigurationmanager.aspx">CrmConfigurationManager</a> class (<a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.client.aspx">Microsoft.Xrm.Client</a>)<br /></font></li>
    <li><font size="2">Performance enhancements through caching of service results provided by the <a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.client.services.cachedorganizationservice.aspx">CachedOrganizationService</a> class (<a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.client.aspx">Microsoft.Xrm.Client</a>)</font></li>
</ul>
<div><font size="2"><br /></font></div>
<div><font size="2"><br /></font></div>
<div><font size="2"><b><i>Don't forget:</i></b></font></div>
<div><font size="2"><br /></font></div>
<div><font size="2">Developer Extensions for Microsoft Dynamics CRM supports deployment for CRM on-premises and CRM Online. However, <u>plug-ins that run in the sandbox on CRM Online shouldn’t make use of any classes or methods in <a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.client.aspx">Microsoft.Xrm.Client</a> because certain functionality in that assembly isn’t supported in the sandbox</u>.<br /></font></div>
<div><font size="2"><br /></font></div>

