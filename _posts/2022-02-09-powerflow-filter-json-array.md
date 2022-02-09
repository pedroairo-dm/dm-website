---
layout: post
title: Microsoft Powerflow - Filter Json Array
date: 2022-02-09 07:00:00.000000000 +00:00
type: post
tag: Microsoft Powerflow
---

Recently I had to filter a Json Array of objects in Powerflow.

Let's say we have a list of accounts and we need to filter by city name. In My case I was getting the data trough Dataverse.

In order to achieve this on another array of Cities only, we can use the approach present in the below image.

![Screen shot of getting an email template by title with dataverse](/images/posts/powerflow-filter-json-array.png)

Explaining the image we have the following:

1. Value, in my case is the list of Cities that i have extracted from CRM from a custom entity.
2. ``` @equals(item()?['dm_city'], first(outputs('Get_Cities')?['body/value'])?['dm_cityname'])```
   
   Where item()?['dm_city'] represents the field from the custom City entity
   The second part of the condition is 'first(outputs('Get_Cities')?['body/value'])?['dm_cityname'])' where 'dm_cityname' represents the field from the dataverse query where the accounts were returned.

Any queries or doubts don't hesitante in reaching me by email at <info@dynamicsmonster.com>.

Hope it helps.
