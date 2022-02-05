---
layout: post
title: Microsoft Powerflow - Dynamics 365 - Get Email Template by Title
date: 2022-02-05 18:00:00.000000000 +00:00
type: post
tag: Microsoft Powerflow - Dynamics 365
---

Let's assume that you create a Cloud Flow that you will interact with for example trough a button in the account form ribbon.

When i started to work with Flows was already a couple of years ago, before i was using the Premium artifact for Dynamics 365, now we use the Dataverse artifact to interact with Dynamics 365.

For developers used to Web Api, and Odata, the queries that are needed in the Power Flow are kind of similar with the query string for interacting with CRM.

The example i want to show in this post is how to get an Email Template by Name with Dataverse in the flow. Please see below image regarding this example:

![Screen shot of getting an email template by title with dataverse](/images/posts/dataverse-get-emailtempalte-by-title.png)

In my case my Email Template title is '[Account] - Send Gift to Customers', to do that, we just set the Filter rows text as (title eq '[Account] - Send Gift to Customers').

Assuming that you require only a couple of fields to be returned you can add them separeted by (,) in the 'Select columns' field.

Assuming that you need to use the 'Email Template Id' field returned by the call, there are a couple of ways of doing, for instance, you can add the artifact 'Parse JSON' where you add the body of the return and for the payload, you can copy and paste from the result of this item and collate after clicking on "Generate from Sample".

Actually when working with Logic Apps and Power Flow you start to understand how things work and get used with small tricks to avoid adding unnecessary artifacts when you need only one or two properties.

In here, because i needed only the Email Template Id returned, and i knew it would be only returned 1 row, whenever you need to use it do the following:

1. Start to select the 'Expression' and write first()
2. Position the cursor inside of the brackets, and click on 'Dynamic COntent'
3. From the right artifact, select the property needed, in my case 'Email Template Id' and click 'Update'

The result if you use the 'Peek Code' by clicking on the 3 dots from the artifact (in my case, the one on the screenshot above) will be something like:

**first(outputs('Get_Email_Template_where_title_=_''[Account]_-_Account_send_gift_to_customers''')?['body/value'])?['templateid’]**

So, i didn't need to use the artifact for Parse the Json result returned from the call to after use the property templateid.

Any queries or doubts don't hesitante in reaching me by email at <info@dynamicsmonster.com>.

Hope it helps.
