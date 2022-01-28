---
layout: post
title: Microsoft Dynamics 2015 - Javascript - Alert vs Form Notification
date: 2015-02-17 10:57:00.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

For many years i used the old Alert to show error or warning messages in CRM, i was using that from a web resource or form. But Microsoft provides a way of doing that in terms of CRM point of view.

So, inside of a form and for custom validations now we can use the following:  

```javascript
Xrm.Page.ui.setFormNotification("Hello","INFO","helloMsg");
```

Displays the message “Hello” at the top of the form with a system info icon.  
This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).  
What's the problem in here, i was tying to use this inside of a Web Resource that even is not inside of a CRM Form and debugging i discovered that Xrm.Page.ui is 'undefined', so after research i came across with the below way to display a non-blocking alert dialog with a callback function.:  

```javascript
var alertDisplayed = false; 
Xrm.Utility.alertDialog("Showing Alert",function () { alertDisplayed = true; });
```

Display an alert and set the value of the **alertDisplayed** variable when it is closed.  
This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).  
The result is our old Alert:  
  
Probably i will do my own custom dialog. Any ideas?
