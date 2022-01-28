---
layout: post
title: Microsoft Dynamics 2015 - Web Service Error Codes
date: 2015-02-26 01:14:10.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

Below is a link to the Microsoft page with all the error codes and descriptions that can be thrown by CRM web services. 

[https://msdn.microsoft.com/en-us/library/gg328182.aspx](https://msdn.microsoft.com/en-us/library/gg328182.aspx "https://msdn.microsoft.com/en-us/library/gg328182.aspx") 

Few examples below:

```html
<crmerror>  
  <ErrorId>
    80048531
  </ErrorId>  
  <ManagedErrorName>
    CustomImageAttributeOnlyAllowedOnCustomEntity
    </ManagedErrorName>  
  <ErrorMessage>
    A custom image attribute can only be added to a custom entity.
  </ErrorMessage>  
</crmerror>  

<crmerror>  
  <ErrorId>
    80048530
  </ErrorId>
  <ManagedErrorName>
    SqlEncryptionSymmetricKeyCannotOpenBecauseWrongPassword
  </ManagedErrorName>  
  <ErrorMessage>
    Cannot open encryption Symmetric Key because the password is wrong.
  </ErrorMessage>  
</crmerror>
```
