---
layout: post
title: Microsoft Dynamics 2015 - Execution Context
date: 2015-02-27 04:05:09.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

This one can be quite interesting, the possibility of interacting with data from a plugin trough the Javascript, for now, i'm not seeing any example, but definitively is one to have a look, and what i think is quite interesting is regarding with  [getSharedVariable](https://msdn.microsoft.com/en-us/library/279ca720-e304-4e51-b99f-91722431c2c8#BKMK_getSharedVariable) and  [setSharedVariable](https://msdn.microsoft.com/en-us/library/279ca720-e304-4e51-b99f-91722431c2c8#BKMK_SetSharedVariable).

When you associate a function in a JavaScript library to an event handler in Microsoft Dynamics CRM, you can check the **Pass execution context as first parameter** option. The following table lists the execution context object methods.

Method

Description

[getContext](https://msdn.microsoft.com/en-us/library/279ca720-e304-4e51-b99f-91722431c2c8#BKMK_getContext)

Returns the **Xrm.Page.context** object. See [Client-side context (client-side reference)](https://msdn.microsoft.com/en-us/library/gg334511.aspx) for more information.

[getDepth](https://msdn.microsoft.com/en-us/library/279ca720-e304-4e51-b99f-91722431c2c8#BKMK_getDepth)

Returns a value indicating the order in which this handler is executed.

[getEventSource](https://msdn.microsoft.com/en-us/library/279ca720-e304-4e51-b99f-91722431c2c8#BKMK_getEventSource)

Returns a reference to the object that the event occurred on.

[getSharedVariable](https://msdn.microsoft.com/en-us/library/279ca720-e304-4e51-b99f-91722431c2c8#BKMK_getSharedVariable)

Retrieves a variable set using [setSharedVariable](https://msdn.microsoft.com/en-us/library/279ca720-e304-4e51-b99f-91722431c2c8#BKMK_SetSharedVariable) .

[setSharedVariable](https://msdn.microsoft.com/en-us/library/279ca720-e304-4e51-b99f-91722431c2c8#BKMK_SetSharedVariable)

Sets the value of a variable that can be used by a hander after the current handler finishes.

Use the **getEventSource** method in functions to make them more generic. For example, if you have a function that formats a telephone number, you can use the **getEventSource** method to refer to whatever attribute caused the **onChange** event. Your functions do not need to reference a specific attribute.

Hope it gives you new ideas to extend even more CRM.