---
layout: post
title: Microsoft Dynamics 2015 - Programming models for CRM
date: 2015-03-04 01:50:20.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

This one i couldn't miss.

I took this article from MSDN and every single CRM Developer has to know this. Has to know the programming paradigms Early Bound, Late Bound, Rest and WSDL.

Below the full article:

Microsoft Dynamics CRM offers several programming paradigms designed to give you the flexibility to decide what works best for your needs. An early-bound entity data model has been added that includes an "object services" layer that integrates with the stack and exposes entity values as .NET Framework objects. You can also use the late-bound scenario.

Programmability scenarios

![Programmabilityscenarios]({{ site.baseurl }}/assets/2015/03/IC458448.png "Programmabilityscenarios")

*   **Early-bound** – Microsoft Dynamics CRM uses an entity data model and Windows Communication Foundation (WCF) Data Services technologies to provide a new set of tools that simplify the development of Internet-enabled applications that interact with Microsoft Dynamics CRM. This also enables an additional programming paradigm: an organization service context that tracks changes to objects and supports .NET Language-Integrated Query (LINQ) queries to retrieve data from Microsoft Dynamics CRM. For more information, see [Use the early bound entity classes in code](https://msdn.microsoft.com/en-us/library/gg328210.aspx) .

*   **Late-bound** – This programming paradigm lets you write code that accesses entities that are not yet defined. For example, you may use this to write a custom search utility that will work for any installation of Microsoft Dynamics CRM, regardless of the customizations that you made. For more information, see [Use the late bound entity class in code](https://msdn.microsoft.com/en-us/library/gg309272.aspx) . This paradigm also allows code to be written in a generic manner in such a way that it doesn't require a certain type of entity.

*   **REST** – The REST endpoint for AJAX and Microsoft Silverlight clients provides an alternative interface that you can use to work with Microsoft Dynamics CRM data. Rather than directly invoking the SOAP-based web service, you can execute requests using a service that is based on a URI. For more information, see [Use the OData endpoint with web resources](https://msdn.microsoft.com/en-us/library/gg334279.aspx) .

*   WSDL   – This programming paradigm lets you develop code from non-.NET clients, and does not depend on the use of Microsoft Dynamics CRM assemblies. For example, you can use this programming model to write code for Microsoft Dynamics CRM in Java. For more information, see   Write Java and other non-.NET client applications .

*   Program using early and late binding

![EntityclasshierarchyforCRM2011]({{ site.baseurl }}/assets/2015/03/IC443856.jpg "EntityclasshierarchyforCRM2011")

Account entity = new Account();entity\[ "name" \] = "My Account" ; //loosely typed, late binding entity.AccountNumber = "1234" ; //strongly typed, early binding

The following diagram illustrates the key programmability scenarios for Microsoft Dynamics CRM 2015 and Microsoft Dynamics CRM Online 2015 Update.

Use these Microsoft Dynamics CRM programming paradigms for the following:

In Microsoft Dynamics CRM, you can choose from several programming scenarios to find the model that best suits your needs.

The main development scenario for Microsoft Dynamics CRM for the Microsoft .NET Framework references two assemblies that allow you to connect to any Microsoft Dynamics CRM system for both early and late bound types. This scenario can be described as late binding or loosely typed. To use late bound types, use the [Entity](https://msdn.microsoft.com/en-us/library/microsoft.xrm.sdk.entity.aspx) class. This class defines a collection of attributes that can be used to get and set the values of attributes. To use this model, the exact logical name must be known (and specified) as a string.

Alternatively, you can use early bound classes generated directly from the metadata, which include all customizations. The generated classes provide early binding and IntelliSense to aid you as you write custom code. For more information, see [Create early bound entity classes with the code generation tool (CrmSvcUtil.exe)](https://msdn.microsoft.com/en-us/library/gg327844.aspx) .

The entity class structure is the following:

The **DynamicEntity** class has been replaced by the base class [Entity](https://msdn.microsoft.com/en-us/library/microsoft.xrm.sdk.entity.aspx) . This means that all types are discoverable at both build time and runtime, making all strongly-typed entities now loosely-typed entities. You can use both programming scenarios in the same code as shown in the following example:

The Microsoft Dynamics CRM SDK documentation includes samples that use both programming scenarios. The early bound samples use a file of strongly-typed classes that are generated with the code generation utility from a new, uncustomized installation of Microsoft Dynamics CRM. To run the samples, you must generate a file of strongly-typed classes from your installation. You can decide whether to create a proxy assembly from the generated code file or to include the file in your project directly, as we have done for the samples. For more information about your development style choices, see [Choose your development style for managed code](https://msdn.microsoft.com/en-us/library/jj602917.aspx) .

  

Link to the article in MSDN:

[https://msdn.microsoft.com/en-us/library/gg327971.aspx](https://msdn.microsoft.com/en-us/library/gg327971.aspx "https://msdn.microsoft.com/en-us/library/gg327971.aspx")