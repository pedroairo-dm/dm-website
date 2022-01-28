---
layout: post
title:  Execute a CRM(2011/2013) OnPremesis or Online Workflow from Javascript
date: 2014-04-29 14:54:00.000000000 +00:00
type: post
tag: Microsoft CRM 2011 & Microsoft CRM 2013
---
  
The function below can be used to execute a workflow from JavaScript using the Organization.svc service instead of the CrmService.asmx from previous versions (CRM 3.0 and CRM4.0 versions):  
  
The first parameter of the function is the workflowid that it will be called, and the second parameter is only to show or not a window to confirm the action that will be made in next:  

```js
function ExecuteWorkflow(workflowId, confirmQuestion)  
{  
 var _return = true;  
 if(confirmQuestion)  
 _return = window.confirm('Are you want to execute workflow.');  
  
 if (_return) {  
 var url = Xrm.Page.context.getServerUrl();  
 var entityId = Xrm.Page.data.entity.getId();  
 var OrgServicePath = "/XRMServices/2011/Organization.svc/web";  
 url = url + OrgServicePath;  
 var request;  
 request = "<s:Envelope xmlns:s="http://schemas.xmlsoap.org/soap/envelope/">" +  
 "<s:Body>" +  
 "<Execute xmlns="http://schemas.microsoft.com/xrm/2011/Contracts/Services" xmlns:i="http://www.w3.org/2001/XMLSchema-instance">" +  
 "<request i:type="b:ExecuteWorkflowRequest" xmlns:a="http://schemas.microsoft.com/xrm/2011/Contracts" xmlns:b="http://schemas.microsoft.com/crm/2011/Contracts">" +  
 "<a:Parameters xmlns:c="http://schemas.datacontract.org/2004/07/System.Collections.Generic">" +  
 "<a:KeyValuePairOfstringanyType>" +  
 "<c:key>EntityId</c:key>" +  
 "<c:value i:type="d:guid" xmlns:d="http://schemas.microsoft.com/2003/10/Serialization/">" + entityId + "</c:value>" +  
 "</a:KeyValuePairOfstringanyType>" +  
 "<a:KeyValuePairOfstringanyType>" +  
 "<c:key>WorkflowId</c:key>" +  
 "<c:value i:type="d:guid" xmlns:d="http://schemas.microsoft.com/2003/10/Serialization/">" + workflowId + "</c:value>" +  
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
 // Responses will return XML. It isn't possible to return JSON.  
 req.setRequestHeader("Accept", "application/xml, text/xml, \*/\*");  
 req.setRequestHeader("Content-Type", "text/xml; charset=utf-8");  
 req.setRequestHeader("SOAPAction", "http://schemas.microsoft.com/xrm/2011/Contracts/Services/IOrganizationService/Execute");  
 req.onreadystatechange = function () { assignResponse(req); };  
 req.send(request);  
 }  
}  
  
function assignResponse(req) {  
 if (req.readyState == 4) {  
 if (req.status == 200) {  
 alert('Successfully executed the workflow');  
 }  
 }  
}
```
