---
layout: post
title: Microsoft Dynamics 2015 - Custom view on a lookup field
date: 2015-02-19 09:24:00.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

This is a recurring functionality that often a developer has to write and i will put in here as a reminder, change the view of a lookup field to meet some customer requirements, adding/removing columns or even add filters to a lookup field.  
Don't remember by heart, but from one version of crm, porbably 3.0 to 4.0 or 4.0 to 2011, that changed.  
I took this from the Microsoft Developer Network webbsite.

```js
function ExecuteWorkflow(workflowId, confirmQuestion)
{
    var _return = true;
    if(confirmQuestion)
        _return = window.confirm(‘Are you want to execute workflow.’);

    if (_return) {
        var url = Xrm.Page.context.getServerUrl();
        var entityId = Xrm.Page.data.entity.getId();
        var OrgServicePath = "/XRMServices/2011/Organization.svc/web";
        url = url + OrgServicePath;
        var request;
        request = "<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">&#8221; +
                      "<s:Body>" +
                        "<Execute xmlns="http://schemas.microsoft.com/xrm/2011/Contracts/Services&#8221; xmlns:i="http://www.w3.org/2001/XMLSchema-instance">&#8221; +
                          "<request i:type="b:ExecuteWorkflowRequest" xmlns:a="http://schemas.microsoft.com/xrm/2011/Contracts&#8221; xmlns:b="http://schemas.microsoft.com/crm/2011/Contracts">&#8221; +
                            "<a:Parameters xmlns:c="http://schemas.datacontract.org/2004/07/System.Collections.Generic">&#8221; +
                              "<a:KeyValuePairOfstringanyType>" +
                                "<c:key>EntityId</c:key>" +
                                "<c:value i:type="d:guid" xmlns:d="http://schemas.microsoft.com/2003/10/Serialization/">&#8221; + entityId + "</c:value>" +
                              "</a:KeyValuePairOfstringanyType>" +
                              "<a:KeyValuePairOfstringanyType>" +
                                "<c:key>WorkflowId</c:key>" +
                                "<c:value i:type="d:guid" xmlns:d="http://schemas.microsoft.com/2003/10/Serialization/">&#8221; + workflowId + "</c:value>" +
                              "</a:KeyValuePairOfstringanyType>" +
                            "</a:Parameters>" +
                            "<a:RequestId i:nil="true" />" +
                            "<a:RequestName>ExecuteWorkflow</a:RequestName>" +
                          "</request>" +
                        "</Execute>" +
                      "</s:Body>" +
                    "</s:Envelope>";

        var req = new XMLHttpRequest();
        req.open("POST", url, true)
        // Responses will return XML. It isn’t possible to return JSON.
        req.setRequestHeader("Accept", "application/xml, text/xml, */*");
        req.setRequestHeader("Content-Type", "text/xml; charset=utf-8");
        req.setRequestHeader("SOAPAction", "http://schemas.microsoft.com/xrm/2011/Contracts/Services/IOrganizationService/Execute&#8221;);
        req.onreadystatechange = function () { assignResponse(req); };
        req.send(request);
    }
}
```

Sets the **viewId**, **viewDisplayName**, **fetchXml**, and **layoutXml** variables to pass as arguments so that a custom view is added as the default view to the control for the**Parent Account** lookup field.  
Hope it helps.