---
layout: post
title: Configure Exchange folder-level tracking rules
date: 2015-11-17 08:49:48.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015 & Microsoft Exchange
---


<p>If you need to configure a specific Microsoft Exchange folder to track the emails and run a workflow process configured in crm, it is possible trough few lines of code.</p>

<p>Let's assume that you have configured a folder in the Microsoft Exchange to keep emails sent by a specific (individual contact or company).</p>

<p>The code needed for this is:</p>

<p><u>To create and manage folder-level tracking rules:</u></p>


<div>
    <div><span><// Create a folder-level tracking rule <br />MailboxTrackingFolder newTrackingFolder = new MailboxTrackingFolder(); <br />// Set the required attributes newTrackingFolder.ExchangeFolderId = &quot;123456&quot;; <br />// Sample value. Retrieve this value using Exchange Web Services (EWS) <br />newTrackingFolder.MailboxId = new EntityReference(Mailbox.EntityLogicalName, _mailboxId); <br />// Set the optional attributes <br />newTrackingFolder.RegardingObjectId = new EntityReference(Account.EntityLogicalName, _accountId); newTrackingFolder.RegardingObjectId.Name = _accountName; <br />newTrackingFolder.ExchangeFolderName = &quot;Sample Exchange Folder&quot;; <br />// Execute the request to create the rule <br /> _folderTrackingId = _serviceProxy.Create(newTrackingFolder); Console.WriteLine(&quot;Created folder-level tracking rule for '{0}'.n&quot;, _mailboxName);</span></div>
</div>

<p><span><u>You can create a maximum of 25 folder-level tracking rules per mailbox.></u></span></p>

<p><u>To <span >Retrieve folder-level tracking rules for a mailbox:</span></u></p>

<div>
    <div>
        <div style="overflow:auto;">
            <table style="float:left;width:100%;">
                <tbody>
                    <tr>
                        <td width="100%"> // Retrieve the folder mapping rules for a mailbox <br />RetrieveMailboxTrackingFoldersRequest req = new RetrieveMailboxTrackingFoldersRequest { MailboxId = _mailboxId.ToString() }; <br />RetrieveMailboxTrackingFoldersResponse resp = (RetrieveMailboxTrackingFoldersResponse_serviceProxy.Execute(req); <br />Console.WriteLine(&quot;Retrieved folder-level tracking rules for {0}:&quot;, _mailboxName); <br />int n = 1; <br />foreach (var folderMapping in resp.MailboxTrackingFolderMappings) { <br /> Console.WriteLine(&quot;tRule {0}: '{1}' is mapped to '{2}'.&quot;, n, folderMapping.ExchangeFolderName, folderMapping.RegardingObjectName); <br /> n++;<br /> }</td>
                    </tr>
                </tbody>
            </table>
        </div>
    </div>
</div>
<div>
    <div>
        <p>Code in here from CRM 2015 SDK.</p>
     
        <p>Hope this can be helpful.</p>
    </div>
</div>

