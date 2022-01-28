---
layout: post
title: Microsoft Dynamics 2015 - Common Exceptions
date: 2015-02-25 12:06:00.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

Developing around CRM always we have to catch Exceptions (Business Exceptions provoked on purpose by our code, sometimes we have to ), below a few examples for the common exceptions.  

```c#
catch (FaultException ex)  
{  
  Console.WriteLine("The application terminated with an error.");  
  Console.WriteLine("Timestamp: {0}", ex.Detail.Timestamp);  
  Console.WriteLine("Code: {0}", ex.Detail.ErrorCode);  
  Console.WriteLine("Message: {0}", ex.Detail.Message);  
  Console.WriteLine("Inner Fault: {0}",  null == ex.Detail.InnerFault ? "No Inner Fault" : "Has Inner Fault");  
}  
catch (System.TimeoutException ex)  
{  
  Console.WriteLine("The application terminated with an error.");  
  Console.WriteLine("Message: {0}", ex.Message);  
  Console.WriteLine("Stack Trace: {0}", ex.StackTrace);  
  Console.WriteLine("Inner Fault: {0}",  
  null == ex.InnerException.Message ? "No Inner Fault" : ex.InnerException.Message);  
}  
catch (System.Exception ex)  
{  
  Console.WriteLine("The application terminated with an error.");  
  Console.WriteLine(ex.Message);  
  // Display the details of the inner exception.  
  if (ex.InnerException != null)  
  {  
    Console.WriteLine(ex.InnerException.Message);  
    FaultException fe = ex.InnerException  
    as FaultException;  
    if (fe != null)  
    {  
      Console.WriteLine("Timestamp: {0}", fe.Detail.Timestamp);  
      Console.WriteLine("Code: {0}", fe.Detail.ErrorCode);  
      Console.WriteLine("Message: {0}", fe.Detail.Message);  
      Console.WriteLine("Trace: {0}", fe.Detail.TraceText);  
      Console.WriteLine("Inner Fault: {0}",  
      null == fe.Detail.InnerFault ? "No Inner Fault" : "Has Inner Fault");  
    }  
  }  
}
```
