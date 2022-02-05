---
layout: post
title: Microsoft Powerflow - Dynamics 365 - Adding email attchments
date: 2022-02-05 11:00:00.000000000 +00:00
type: post
tag: Microsoft Powerflow - Dynamics 365
---

Imagine this scenario, you are using Microsoft Dynamics 365 and you need to create an email from an email template and attach the email attacthment attachments.

It was a little bit tricky to figure out how to do it, the reason of that being the UI itslef induces the developer in error.

See the image below where we will explain what to fill and how to fill the data.

![Screen shot of Adding a new Email Attachment](/images/posts/dataverse-adding-emailattachment.png)

Explaining the fields to fill:

1. **Attachment(Attachments)**, this is the first trick field, the UI tells you that is a required field, than makes you thinking that you need to set a GUID if you read the content of the text box without any data. However, after trying and trying, i set the value to a null trough the Expression set data type, don´t try as Dynamic.

2. **Entity**, this is without any doubts the most weird one, when you try to fill, it only allows to options, 'Email Template' and 'Email Activity'. In this case, we thought we needed the Email Activity because we were creating a Email Attachment to an Email. The error given by the history is the one below:

    **The entity with a name = '4200' with namemapping = 'Logical' was not found in the MetadataCache....**

    After googling and trying, i found the solution to be set the field as **email** as per printscreen. Has to be set as selecting 'Enter custom value', and set as **email**.

3. The other fields are more or less explanatory, as per screenshot.

Any queries or doubts don't hesitante in reaching us by email at <info@dynamicsmonster.com>.

Hope it helps.