---
layout: post
title: CRM Transaction Mode operations (Dynamics 365 V9)
date: 2020-09-29 09:58:01.000000000 +00:00
type: post
tag: Microsoft Dynamics 365
---

<p><!-- wp:paragraph --></p>
<p>I hope I'm not late with this post. Who never had to do develop some code where the requirement would be "In Transaction"?</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>I don't think this will apply to all possible scenarios but it is a start.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Let's assume the following scenario: In CRM 365, someone asked you to apply a change to an entity based on a really easy filter. For example, if a customer address is in City "A", set a custom field with value "B", however, if you can't update one of the records for some reason (example, exception thrown), you need to rollback everything.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Here, and we all know that are many ways to achieve this, I'm giving one.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Hypothetically, let's assume we opt for a plugin at first sight, however, after some testing we start to get Timeouts because we need to update to many records and the 2 minutes just pass.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Another option would be with a Console Application, and this is a personal option, not 100% right nor 100% wrong, there is one of many ways. </p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>By not doing with a Plugin, brings me to a problem that needs to be addressed based on the requirements that is the requirement "Transaction". If one of the records fail, I need to undo the others, so, more code to deal with that, however, you can avoid that for this specific case only with CRM SDK, no need to reinvent the wheel.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Found in the SDK the message <em><strong>ExecuteTransactionRequest</strong></em> that do the Transaction I really needed, this allows me to perform multiple requests as one single database transaction. Using this message allows executing two or more organization services requests in a single database transaction. If one of the requests fails the transaction is rolled back.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>For more information visit Microsoft page below:</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p><a rel="noreferrer noopener" href="https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/org-service/use-executetransaction" target="_blank">https://docs.microsoft.com/en-us/powerapps/developer/common-data-service/org-service/use-executetransaction</a></p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Any questions please reply trough this post or contact us.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Hope it helps.</p>
<p><!-- /wp:paragraph --></p>
