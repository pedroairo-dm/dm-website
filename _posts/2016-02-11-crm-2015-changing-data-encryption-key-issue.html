---
layout: post
title: Microsoft Dynamics 2015 - Changing Data Encryption Key Issue
date: 2016-02-11 06:12:35.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p>Just redeployed an Organization into another server in the same Domain, when I came across with an issue when trying to send emails.</p>

<p>It was easy to discover the problem, in this case related to the Data Encryption after being done the redeployment.</p>

<p>To resolve the issue i have tried the following:</p>

<p>Change the encryption key, but i was having issues saying first i was not in the <span>PrivUserGroup, i added a CRM Admin user to that group for the moment and  performed an IIS Reset, tried again and that time the info around key different from the generated one.<span></span></span></p>

<p><span>- To overcome that i run against that specific organization the following SQL Query:</span></p></p>

<table style="float:left;width:100%;">
    <tbody>
        <tr>
            <td width="100%">
                <p> <span>USE CRMOrg_MSCRM (Use CRM Org Name)<br /></span></p>
                <div>
                    UPDATE EmailServerProfile SET IncomingPassword=null<br />
                    <div>
                        UPDATE EmailServerProfile SET OutgoingPassword=null
                        <div>
                            UPDATE Mailbox SET Password=null
                            <div>
                                UPDATE Queue SET EmailPassword=null
                                <div>UPDATE UserSettings SET EmailPassword=null</div>
                            </div>
                        </div>
                    </div>
                </div>
            </td>
        </tr>
    </tbody>
</table>
