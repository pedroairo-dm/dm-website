---
layout: post
title: Microsoft Dynamics 365 - Choose your development style for managed code - Create and deploy plug-ins or custom workflow activities
date: 2015-03-24 06:24:58.000000000 +00:00
type: post
tag: Microsoft Dynamics 365
---

<p><span>From MSDN Web Site i took this:</span></p>
<p><span><a href="https://msdn.microsoft.com/en-us/library/jj602917.aspx#create_and_deploy_plugins" target="_blank" title="Choose your development style for managed code">https://msdn.microsoft.com/en-us/library/jj602917.aspx#create_and_deploy_plugins</a> <br /></font></span></p>

<p>The following table lists the choices you have for writing and deploying plug-ins and custom workflow activities. </p>

<table>
    <tbody>
        <tr>
            <th><font color="#000000" >Tool </font></th>
            <th><font color="#000000" >Description and usage </font></th>
            <th><font color="#000000" >More information </font></th>
        </tr>
        <tr>
            <td>
                <p><font color="#000000" >Plug-in and Custom Workflow Activity classes </font></p>
                <p><font color="#000000" >Plug-in Registration Tool </font></p>
            </td>
            <td>
                <p><font color="#000000" >The plug-in and custom workflow activity classes allow you to create event handlers to perform custom business logic that you can integrate with Microsoft Dynamics CRM to modify or augment the standard behavior of the platform. </font></p>
                <p><font color="#000000" >By using these classes directly, your code will not contain any helper code provided in the Developer Toolkit. </font></p>
                <p><font color="#000000" >If you write plug-ins and custom workflow activities from scratch, you must use the Plug-in Registration Tool to register them. This tool provides a graphical user interface and supports registering plug-ins and custom workflow activities with Microsoft Dynamics CRM. </font></p>
                <p><font color="#000000" >Use this method if you: </font></p>
                <p><font color="#000000" >Understand how to use the plug-in and custom activity classes. </font></p>
                <p><font color="#000000" >Don't want extra library code auto-generated and placed in your code files. </font></p>
                <p><font color="#000000" >Don't mind using an external tool and the web application to register and package custom code assemblies. </font></p>
            </td>
            <td>
                <p> <font color="#000000" ><a href="https://msdn.microsoft.com/en-us/library/gg328490.aspx">Plug-in development </a> </font></p>
                <p> <font color="#000000" ><a href="https://msdn.microsoft.com/en-us/library/gg309745.aspx">Custom workflow activities (workflow assemblies) </a> </font></p>
                <p> <font color="#000000" ><a href="https://msdn.microsoft.com/en-us/library/gg309620.aspx">Register and Deploy Plug-Ins </a> </font></p>
                <p> <font color="#000000" ><a href="https://msdn.microsoft.com/en-us/library/gg309580.aspx">Walkthrough: Register a plug-in using the plug-in registration tool </a> </font></p>
            </td>
        </tr>
    </tbody>
</table>
