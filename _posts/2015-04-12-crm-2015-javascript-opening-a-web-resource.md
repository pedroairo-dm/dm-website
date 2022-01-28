---
layout: post
title: Microsoft Dynamics 2015 - Javascript - Opening a Web Resource
date: 2015-04-12 14:25:04.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p><font size="2">Javascript function from the Namespace Xrm.Utility that can be called to open a Web Resource with the possibility of adding parameters. Bare in mind that cannot that t</font><span><span><font size="2">his function will not work with Microsoft Dynamics CRM for tablets. </font><span>  </span> </span> </span></p>

<div>
    <div>
        <div dir="ltr"> </div>

    </div>
    <div>
        <div>
            <div> </div>

        </div>
        <div dir="ltr">
            <div>
<pre /><font face="Arial, Helvetica, sans-serif" size="2">Xrm.Utility.openWebResource(webResourceName,webResourceData,width, height) </font>
            </div>
        </div>
    </div>
</div>
<dl> <dt> <font face="Arial, Helvetica, sans-serif" size="2"><b> <b>Parameters </b> </b> </font> </dt><dd> <h3><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">  </font></h3> <table> <tbody> <tr> <th><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Name </font></th> <th><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Type </font></th> <th><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Required </font></th> <th><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Description </font></th> </tr> <tr> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">webResourceName </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">String </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Yes </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">The name of the HTML web resource to open. </font></p> </td> </tr> <tr> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">webResourceData </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">String </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">No </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Data to be passed into the data parameter. </font></p> </td> </tr> <tr> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">width </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Number </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">No </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">The width of the window to open in pixels. </font></p> </td> </tr> <tr> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">height </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Number </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">No </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">The height of the window to open in pixels. </font></p> </td> </tr> </tbody> </table> </dd></dl>
<dl> <dt> <font face="Arial, Helvetica, sans-serif" size="2"><b> <b>Return Value </b> </b> </font> </dt><dd><font face="Arial, Helvetica, sans-serif" size="2">Window object. </font><p> </p> </dd></dl>
<dl> <dt> <font face="Arial, Helvetica, sans-serif" size="2"><b> <b>Remarks </b> </b> </font> </dt><dd><font face="Arial, Helvetica, sans-serif" size="2">An HTML web resource can accept the parameter values described in <span>  </span> <a href="https://msdn.microsoft.com/en-us/library/bba8645a-a725-4c4d-a393-bab8ca692482#BKMK_PassingParametersToWebResources">Passing Parameters to HTML Web Resources </a>. This function only provides for passing in the optional data parameter. To pass values for the other valid parameters, you must append them to the <b>webResourceName </b> <span>  </span>parameter. </font><p> </p> </dd></dl>
<dl>
    <dt> <font face="Arial, Helvetica, sans-serif" size="2"><b> <b>Examples </b> </b> </font> </dt>
    <dd>
        <font face="Arial, Helvetica, sans-serif" size="2"><b>Open an HTML web resource named “new_webResource.htm” </b> </font><p> </p> <div> <div> <div dir="ltr"> </div> </div> <div> <div> <div> </div> </div> <div dir="ltr"> <div> <pre /><font face="Arial, Helvetica, sans-serif" size="2">Xrm.Utility.openWebResource( <span>&quot;new_webResource.htm&quot; </span>); </font> </div> </div> </div> </div> <font face="Arial, Helvetica, sans-serif" size="2"><b>Open an HTML web resource including a single item of data for the data parameter </b> </font><p> </p> <div> <div> <div dir="ltr"> </div> </div> <div> <div> <div> </div> </div> <div dir="ltr"> <div> <pre /><font face="Arial, Helvetica, sans-serif" size="2">Xrm.Utility.openWebResource( <span>&quot;new_webResource.htm&quot; </span>, <span>&quot;dataItemValue&quot; </span>); </font> </div> </div> </div> </div> <font face="Arial, Helvetica, sans-serif" size="2"><b>Open an HTML web resource passing multiple values through the data parameter </b> </font><p> </p> <div>
            <div> <div dir="ltr"> </div> </div> <div>
                <div> <div> </div> </div> <div dir="ltr">
                    <div>
                        <pre> </pre>
                        <p><font face="Arial, Helvetica, sans-serif" size="2"><span>var </span> customParameters = encodeURIComponent( <span>&quot;first=First Value&amp;second=Second Value&amp;third=Third Value&quot; </span>);Xrm.Utility.openWebResource( <span>&quot;new_webResource.htm&quot; </span>,customParameters); </font>
                    </div>

                </div>

            </div>

        </div>
        <div>
            <table>
                <tbody>
                    <tr>
                        <th align="left"> </th>
                    </tr>
                    <tr>
                        <td>
                            <font color="#000000" face="Arial, Helvetica, sans-serif" size="2">These values have to be extracted from the value of the data parameter in the HTML web resource. For more information, see <span>  </span> <a href="https://msdn.microsoft.com/en-us/library/gg327945.aspx">Sample: Pass multiple values to a web resource through the data parameter </a> </font></p>
                        </td>
                    </tr>
                </tbody>
            </table>

        </div>
        <p> <font face="Arial, Helvetica, sans-serif" size="2"><b>Open an HTML web resource with the parameters expected by HTML web resources </b> </font></p>
        <div>
            <div>
                <div dir="ltr"> </div>

            </div>
            <div>
                <div>
                    <div> </div>

                </div>
                <div dir="ltr">
                    <div>
<pre /><font face="Arial, Helvetica, sans-serif" size="2">Xrm.Utility.openWebResource( <span>&quot;new_webResource.htm?typename=account&amp;userlcid=1033&quot; </span>); </font>
                    </div>
                </div>
            </div>
        </div><font face="Arial, Helvetica, sans-serif" size="2">For more information, see <span>  </span> <a href="https://msdn.microsoft.com/en-us/library/bba8645a-a725-4c4d-a393-bab8ca692482#BKMK_PassingParametersToWebResources">Passing Parameters to HTML Web Resources </a>. </font><p> </p> <font face="Arial, Helvetica, sans-serif" size="2"><b>Open an HTML web resource, setting the height and width </b> </font><p> </p> <div> <div> <div dir="ltr"> </div> </div> <div> <div> <div> </div> </div> <div dir="ltr"> <div> <pre /><font face="Arial, Helvetica, sans-serif" size="2">Xrm.Utility.openWebResource( <span>&quot;new_webResource.htm&quot; </span>, <span>null </span>, 300,300); </font> </div> </div> </div> </div>
    </dd>
    <dd>
        <pre><br /></pre>
    </dd>
    <dd>
<pre /><font face="Verdana, Geneva, sans-serif" size="2">From MSDN: <a href="https://msdn.microsoft.com/en-us/library/jj602956.aspx#BKMK_OpenWebResource" target="_blank" title="https://msdn.microsoft.com/en-us/library/jj602956.aspx#BKMK_OpenWebResource">https://msdn.microsoft.com/en-us/library/jj602956.aspx#BKMK_OpenWebResource</a> </font>
    </dd>
    <dd>

    </dd>
    <dd>
<pre /><font face="Verdana, Geneva, sans-serif" size="2">Hope can help you.</font>
    </dd>
</dl>
<p></p>
