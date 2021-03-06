---
layout: post
title: Microsoft Dynamics 2015 - Javascript - Opening an Entity Form from Javascript
date: 2015-04-10 01:26:06.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---



<p><font size="2">Opening a form where you can say if it will open on the same window or another window it will be possible on the <span>Microsoft Dynamics CRM Online 2015 Update 1.</span></font></p>

<p><font size="2">In old times you would use the window.open, but my Microsoft and say as well as a best practice you should use the <span>Xrm.Utility (client-side reference).</span></font></p>

<p><span><font size="2">Now it will be possible to pass if you want to open on the same window or in a new window as you can see from the below information that i took from the MSDN.</font></span></p>


<p><font face="Arial, Helvetica, sans-serif" size="2">Opens an entity form for a new or existing entity record using the options you set as parameters. </font></p>
<div>
    <div>
        <div dir="ltr"> </div>
        </p>
    </div>
    <div>
        <div>
            <div> </div>
            </p>
        </div>
        <div dir="ltr">
            <div>
<pre /><font face="Arial, Helvetica, sans-serif" size="2">Xrm.Utility.openEntityForm(name,id,parameters,windowOptions) </font>
            </div>
        </div>
    </div>
</div>
<dl> <dt> <font face="Arial, Helvetica, sans-serif" size="2"><b> <b>Parameters </b> </b> </font> </dt><dd> <h3><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">  </font></h3> <table> <tbody> <tr> <th><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Name </font></th> <th><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Type </font></th> <th><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Required </font></th> <th><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Description </font></th> </tr> <tr> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">name </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">String </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Yes </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">The logical name of the entity. </font></p> </td> </tr> <tr> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">id </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">String </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">No </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">The string representation of a unique identifier or the record to open in the form. If not set, a form to create a new record is opened. </font></p> </td> </tr> <tr> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">parameters </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Object </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">No </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">A dictionary object that passes extra query string parameters to the form. Invalid query string parameters will cause an error. </font></p> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Valid extra query string parameters are: </font></p> <ul> <li> <font color="#000000" face="Arial, Helvetica, sans-serif" size="2"><b>Form id </b>: To set the id value of the main form to use when more than one form is available. The parameter is <span>  </span> <b>formid </b>. <br /> <br /> </font> </li><li> <font color="#000000" face="Arial, Helvetica, sans-serif" size="2"><b>Default field ids </b>: To set default values for a new record form. For more information, see <span>  </span> <a href="https://msdn.microsoft.com/en-us/library/gg334375.aspx">Set field values using parameters passed to a form </a>. <br /> <br /> </font> </li><li><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">The <span>  </span> <i>navbar </i> <span>  </span>and <span>  </span> <i>cmdbar </i> <span>  </span>parameters described in <span>  </span> <a href="https://msdn.microsoft.com/en-us/library/a8015117-1aa1-40df-b418-e563424b7558#BKMK_QueryStringParametersForMainForm">Query String Parameters for the Main.aspx Page </a>. <br /> <br /> </font> </li><li> <font color="#000000" face="Arial, Helvetica, sans-serif" size="2"><b>Custom query string parameters </b>: A form can be configured to accept custom query string parameters. For more information, see <span>  </span> <a href="https://msdn.microsoft.com/en-us/library/gg334436.aspx">Configure a form to accept custom querystring parameters </a>. <br /> <br /> </font> </li></ul> </td> </tr> <tr> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">windowOptions </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">Object </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">No </font></p> </td> <td> <p><font color="#000000" face="Arial, Helvetica, sans-serif" size="2">For Microsoft Dynamics CRM Online 2015 Update 1 or later use this optional parameter in the web application to control how the form opens. You can choose to open a form in a new window by passing a dictionary object with a boolean <span>  </span> <b>openInNewWindow </b> <span>  </span>property set to <span>  </span> <b>true </b>. </font></p> </td> </tr> </tbody> </table> </dd></dl>
<dl> <dt> <font face="Arial, Helvetica, sans-serif" size="2"><b> <b>Remarks </b> </b> </font> </dt><dd><font face="Arial, Helvetica, sans-serif" size="2">Using this function helps ensure that users are not prompted to log in again under certain circumstances. </font><p> </p> </dd></dl>
<dl>
    <dt> <font face="Arial, Helvetica, sans-serif" size="2"><b> <b>Examples </b> </b> </font> </dt>
    <dd>
        <font face="Arial, Helvetica, sans-serif" size="2"><b>Open a new account record using the default form </b> </font><p> </p> <div> <div> <div dir="ltr"> </div> </div> <div> <div> <div> </div> </div> <div dir="ltr"> <div> <pre /><font face="Arial, Helvetica, sans-serif" size="2">Xrm.Utility.openEntityForm( <span>&quot;account&quot; </span>); </font> </div> </div> </div> </div> <font face="Arial, Helvetica, sans-serif" size="2"><b>Open an existing account record using the default form </b> </font><p> </p> <div> <div> <div dir="ltr"> </div> </div> <div> <div> <div> </div> </div> <div dir="ltr"> <div> <pre /><font face="Arial, Helvetica, sans-serif" size="2">Xrm.Utility.openEntityForm( <span>&quot;account&quot; </span>, <span>&quot;A85C0252-DF8B-E111-997C-00155D8A8410&quot; </span>); </font> </div> </div> </div> </div> <font face="Arial, Helvetica, sans-serif" size="2"><b>Open a new account record with a specific form and setting default values </b> </font><p> </p> <div>
            <div> <div dir="ltr"> </div> </div> <div>
                <div> <div> </div> </div> <div dir="ltr">
                    <div>
                        <pre> </pre>
                        <p><font face="Arial, Helvetica, sans-serif" size="2"><span>var </span> parameters = {};parameters[ <span>&quot;formid&quot; </span>] = <span>&quot;b053a39a-041a-4356-acef-ddf00182762b&quot; </span>;parameters[ <span>&quot;name&quot; </span>] = <span>&quot;Test&quot; </span>;parameters[ <span>&quot;telephone1&quot; </span>] = <span>&quot;(425) 555-1234&quot; </span>;Xrm.Utility.openEntityForm( <span>&quot;account&quot; </span>, <span>null </span>, parameters); </font>
                    </div>
                    </p>
                </div>
                </p>
            </div>
            </p>
        </div>
        <p> <font face="Arial, Helvetica, sans-serif" size="2"><b>Open a new account record using the default form in a new window </b> </font></p>
        <div>
            <div>
                <div dir="ltr"> </div>
                </p>
            </div>
            <div>
                <div>
                    <div> </div>
                    </p>
                </div>
                <div dir="ltr">
                    <div>
<pre> </pre>
                        <p><font face="Arial, Helvetica, sans-serif" size="2"><span>var </span> windowOptions = { openInNewWindow: <span>true </span>};Xrm.Utility.openEntityForm( <span>&quot;account&quot; </span>, <span>null </span>, <span>null </span>,windowOptions); </font>
                    </div>
                    </p>
                </div>
                </p>
            </div>
            </p>
        </div>
    </dd>
</dl>
<div></div>
<p><font size="2">Hope it helps.</font></p>

