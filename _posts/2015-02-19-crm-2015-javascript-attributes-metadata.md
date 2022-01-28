---
layout: post
title: Microsoft Dynamics 2015 - Attributes Metadata
date: 2015-02-19 09:14:00.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

This can be very helpful, many times we need to know for a specific field type, the default value, min value, max value, all this when applies of course.  
Below we have the examples for doing that.  

Get the type of attribute

```javascript
var attributeType = Xrm.Page.getAttribute(0).getAttributeType();
```

Assigns the string value that represents the type of attribute for the first attribute to the **attributeType** variable.

Get how the attribute is formatted

```javascript
var attributeFormat = Xrm.Page.getAttribute(0).getFormat();
```

Assigns the string value that represents the format of the first attribute to the **attributeFormat** variable.

Get the initial value of a **Boolean** or optionset attribute

```javascript
var attributeInitialValue = Xrm.Page.getAttribute("address1\_addresstypecode").getInitialValue();
```

Assigns the initial number value of the **Address Type** field to the **attributeInitialValue** variable.

Determine whether an attribute value has changed

```javascript
var isNameChanged = Xrm.Page.getAttribute("name").getIsDirty();
```

Assigns a **Boolean** value that indicates whether the **Account Name** field value has changed to the **isNameChanged** variable.

Determines whether a lookup attribute represents a partylist lookup.

```javascript
var isPartyList = Xrm.Page.getAttribute("to").getIsPartyList();
```

Assigns a **Boolean** value that indicates whether the **Email** entity **to** field represents a party list lookup.

This method is only available for [Updated entities](https://msdn.microsoft.com/en-us/library/41462684-3e5d-4858-8be4-1a7c4fcdeff6#BKMK_UpdatedEntties).

Get the maximum allowed value for an attribute that contains a number

```javascript
var newValue = 100000000000001;  
var newValueBelowMax = (newValue < Xrm.Page.getAttribute("creditlimit").getMax());
```

Assigns a **Boolean** value that indicates whether the value of the **newValue** variable exceeds the maximum value allowed for the**Credit Limit** field to the **newValueBelowMax** variable.

Get the maximum allowed length for an attribute that contains a string

```javascript
var newAccountName = "A Store";  
var nameTooLong = (newAccountName.length > Xrm.Page.getAttribute("name").getMaxLength())
```

Assigns a **Boolean** value that indicates whether the value of the **newAccountName** variable exceeds the maximum length allowed for the **Account Name** field to the **nameTooLong** variable.

Get the minimum allowed value for an attribute that contains a number

```javascript
var newValue = -1;  
var newValueBelowMin = (newValue < Xrm.Page.getAttribute("creditlimit").getMin());
```

Assigns a **Boolean** value that indicates whether the value of the **newValue** variable is below the minimum value allowed for the**Credit Limit** field to the **newValueBelowMin** variable.

Gets the logical name of an attribute

```javascript
var attributeName = Xrm.Page.getAttribute(0).getName();
```

Assigns the logical name value of the first attribute on the page to the **attributeName** variable

Get the option object representing a value

```javascript
var addressTypeOption = Xrm.Page.getAttribute("address1\_addresstypecode").getOption(1);  
alert(addressTypeOption.text); //displays 'Bill To'
```

Shows an alert that displays the text of the **Address Type** field option with a value of 1.

Get a number value representing the level of precision for the number attribute

```javascript
var creditLimitPrecision = Xrm.Page.getAttribute("creditlimit").getPrecision();
```

Assigns the precision value of the **Credit Limit** field to the **creditLimitPrecision** variable.

Get a string value representing whether the an attribute is required to have a value

```javascript
var creditLimitRequired = Xrm.Page.getAttribute("creditlimit").getRequiredLevel();
```

The **creditLimitRequired** variable value may be **none**, **required**, or **recommended**.

Change whether data is required in a field in order to save a record

```javascript
Xrm.Page.getAttribute("creditlimit").setRequiredLevel("required");
```

Makes the **Credit Limit** field required.

Determine whether the data in an attribute will be submitted when the record is saved

```javascript
var nameSubmitMode = Xrm.Page.getAttribute("name").getSubmitMode();
```

The **nameSubmitMode** variable value will be either **always**, **never**, or **dirty** to represent the **submitMode** for the **Account Name** field..

Control whether data in an attribute will be saved when the record is saved

```javascript
Xrm.Page.getAttribute("name").setSubmitMode("always");
```

The example will force the **Account Name** field value to always be saved even when it has not changed.

When field level security has been applied to an attribute,  
determine whether a user has privileges to perform create,  
read, or update operations on the attribute. For more information, see  
[How field security can be used to control access to field values in Microsoft Dynamics CRM](https://msdn.microsoft.com/en-us/library/gg309608.aspx)

```javascript
var canUpdateNameAttribute = Xrm.Page.getAttribute("name").getUserPrivilege().canUpdate;
```

Assigns a **Boolean** value that represents the user’s privilege to update the **Account Name** field to the**canUpdateNameAttribute** variable.