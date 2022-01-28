---
layout: post
title: Microsoft Dynamics 2015 - Javascript - Display Notifications
date: 2015-02-23 08:47:00.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

Below ways to display notifications using the CRM objects.

- Display a message near the control to indicate that data is not valid.

```js
Xrm.Page.getAttribute("name").controls.forEach(  
    function (control, i) {  
      control.setNotification("'Test' is not a valid name.");  
});
```

Sets a validation error message on every control in the form for the **Account Name**attribute.

While this message is displayed the record cannot be saved.

This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).

- Remove a message already displayed for a control.

```js
Xrm.Page.getAttribute("name").controls.forEach(  
  function (control, i) {  
    control.clearNotification();  
});
```

Clears all validation error messages on every control in the form for the **Account Name**attribute.

This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).

- Display form level notifications.

```js
Xrm.Page.ui.setFormNotification(  
  "Hello",  
  "INFO",  
  "helloMsg"  
); 
```

Displays the message “Hello” at the top of the form with a system info icon.

This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).

- Remove form level notifications

```js
Xrm.Page.ui.clearFormNotification("helloMsg"); 
```

Clears the message previously set using “helloMsg” as the **uniqueid** parameter.

This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).

- Display a non-blocking alert dialog with a callback function.

```js
var alertDisplayed = false;  
  Xrm.Utility.alertDialog(  
    "Showing Alert",  
    function () { alertDisplayed = true; }  
    );
```

Display an alert and set the value of the **alertDisplayed** variable when it is closed.

This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).

- Display a non-blocking confirm dialog with different callbacks depending on the button clicked by the user.

```js
var agree = false;  
Xrm.Utility.confirmDialog(  
  "Do you agree?",  
  function () { agree = true;},  
  function () { agree = false; }  
);
```

Display a confirmation message and set the value of the **agree** variable depending on the response.

This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).
