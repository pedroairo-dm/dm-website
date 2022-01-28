---
layout: post
title: CRM 2011 Syncronous Plugin
date: 2013-05-08 16:39:00.000000000 +00:00
type: post
tag: Microsoft CRM 2011
---


Retrieving in a Create Syncronous Plugin the count of the records from the same type of entity from a Query Expression gives a timeout.   
The reason is because the CRM locks the record.   
  
To overcome this problem you need to set the property NoLock to "true".
