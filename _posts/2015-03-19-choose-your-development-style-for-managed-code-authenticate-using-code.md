---
layout: post
title: Microsoft Dynamics 2015 - Choose your development style for managed code - Authenticate using code
date: 2015-03-19 06:45:33.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p><span><font>From MSDN Web Site i took this few examples for authentication against CRM:</font></span></p>

<table border="1" cellpadding="0" cellspacing="0" width="618">
    <tbody>
        <tr>
            <td width="84">
                <p> <font color="#000000"><b> Classes </b> </font></p>
            </td>
            <td width="255">
                <p> <font color="#000000"><b> <span>Description and usage </span> </b> </font></p>
            </td>
            <td width="279">
                <p> <font color="#000000"><b> <span>More information </span> </b> </font></p>
            </td>
        </tr>
        <tr>
            <td valign="top" width="84">
                <p> <font color="#000000"><span>Helper code </span> </font></p>
            </td>
            <td valign="top" width="255">
                <p> <font color="#000000"><span>The classes in the sample code demonstrate how to connect to the web services and authenticate the user. You can use the helper code as a basis of your own custom authentication code. </span> </font></p>
                <p> <font color="#000000"><span>This code is easy to use and supports all Microsoft Dynamics CRM deployment types. It also supports storing users’ passwords in the Windows Credential Manager for later reuse. </span> </font></p>
                <p> <font color="#000000"><span>Full source code is provided so you can copy and customize it for your needs. This is a recommended practice to isolate your programs from changes to this helper code in future releases. </span> </font></p>
            </td>
            <td valign="top" width="279">
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/hh675400.aspx"> <span>Sample: Quick start for Microsoft Dynamics CRM </span> </a> </span> </font></p>
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/gg328228.aspx"> <span>Use the sample and helper code </span> </a> </span> </font></p>
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/gg309393.aspx"> <span>Helper code: ServerConnection class </span> </a> </span> </font></p>
                <p> <font color="#000000"><span>This code can be found in the </span> <span>SampleCodeCSHelperCodeCrmServiceHelpers.cs </span> <span>and </span> <span>SampleCodeVBHelperCodeCrmServiceHelpers.vb </span> <span>files in the SDK.  <a href="http://go.microsoft.com/fwlink/?LinkID=512122"> <span>Download the Microsoft Dynamics CRM SDK package. </span> </a> </span> </font></p>
            </td>
        </tr>
        <tr>
            <td valign="top" width="84">
                <p> <font color="#000000"><span>Developer Extensions </span> </font></p>
            </td>
            <td valign="top" width="255">
                <p> <font color="#000000"><span>These assemblies are provided to simplify and accelerate the development of applications that interact with Microsoft Dynamics CRM. The extensions extend the functionality of the core Microsoft Dynamics CRM SDK specifically around the use of the  <a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.sdk.client.organizationservicecontext.aspx"> <span>OrganizationServiceContext </span> </a>class. </span> </font></p>
                <p> <font color="#000000"><span>For an easy method that does the hard work for you in a few lines of code, use the  <a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.client.crmconnection.aspx"> <span>CrmConnection </span> </a> class. </span> </font></p>
                <p> <font color="#000000"><span>This code is easy to use and supports all Microsoft Dynamics CRM deployment types. </span> </font></p>
            </td>
            <td valign="top" width="279">
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/gg695784.aspx"> <span>Developer extensions for Microsoft Dynamics CRM </span> </a> </span> </font></p>
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/gg695810.aspx"> <span>Simplified connection to Microsoft Dynamics CRM </span> </a> </span> </font></p>
            </td>
        </tr>
        <tr>
            <td valign="top" width="84">
                <p> <font color="#000000"><span>Xrm client </span> </font></p>
            </td>
            <td valign="top" width="255">
                <p> <font color="#000000"><span>For advanced developers who need to customize the Windows Communication Foundation (WCF) service channel management and the authentication process, use the  <a href="https://msdn.microsoft.com/en-us/library/hh547372.aspx"> <span>IServiceManagement </span> </a> and  <a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.sdk.client.organizationserviceproxy.aspx"> <span>OrganizationServiceProxy </span> </a> classes in the  <a href="https://msdn.microsoft.com/en-us/library/microsoft.xrm.sdk.client.aspx"> <span>Microsoft.Xrm.Sdk.Client </span> </a> namespace. </span> </font></p>
                <p> <font color="#000000"><span>Using these classes directly can provide better connection and authentication performance, and more flexibility. However, they require more advanced knowledge of the WCF service channel and server authentication. In addition, you must write more code to handle all Microsoft Dynamics CRM deployment types. </span> </font></p>
            </td>
            <td valign="top" width="279">
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/gg334502.aspx"> <span>Active Directory and claims-based authentication </span> </a> </span> </font></p>
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/hh675404.aspx"> <span>Sample: Authenticate users with Microsoft Dynamics CRM web services </span> </a> </span> </font></p>
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/42dcebf5-a624-45b9-b719-20e5882d5ca2#caching"> <span>Improve Service Channel Allocation Performance </span> </a> </span> </font></p>
            </td>
        </tr>
        <tr>
            <td valign="top" width="84">
                <p> <font color="#000000"><span>XRM tooling </span> </font></p>
            </td>
            <td valign="top" width="255">
                <p> <font color="#000000"><span>These assemblies leverage the CRM APIs to provide easy authentication support with fewer lines of code and through Windows PowerShell cmdlets. All the function calls in these classes provide thread-safety for actions performed in CRM in a multithreaded environment. It provides a common sign-in control with integrated authentication logic and an ability to securely store and reuse the authentication information to provide a consistent and seamless sign-in experience to CRM from your Windows client applications. </span> </font></p>
                <p> <font color="#000000"><span>These classes also provide built-in diagnostic tracing to aid troubleshooting and performance reporting of the action calls from your Windows client applications. </span> </font></p>
                <p> <font color="#000000"><span>These classes support all Microsoft Dynamics CRM deployment types and authentication types, except OAuth. </span> </font></p>
            </td>
            <td valign="top" width="279">
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/dn689057.aspx"> <span>Build Windows client applications using the XRM tools </span> </a> </span> </font></p>
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/dn688177.aspx"> <span>Use XRM tooling to connect to CRM </span> </a> </span> </font></p>
                <p> <font color="#000000"><span> <a href="https://msdn.microsoft.com/en-us/library/dn689040.aspx"> <span>Use PowerShell cmdlets for XRM tooling to connect to CRM </span> </a> </span> </font></p>
                <p> <font color="#000000" size="2"><font face="Arial, Helvetica, sans-serif"> </font><a href="https://msdn.microsoft.com/en-us/library/dn689019.aspx"><font face="Arial, Helvetica, sans-serif"> Sample: Quick start for XRM Tooling API </font> </a> </font></p>
            </td>
        </tr>
    </tbody>
</table>

<p><font size="2">Hope it helps.</font></p>
