---
layout: post
title: Microsoft Dynamics 2015 - {Javascript Code Example 2} - Save a form asynchronously with call back function
date: 2015-05-05 02:44:36.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p>If for any reason you need to have a call back function in CRM after saving a form <span>asynchronously </span>it is possible to do with this line below:</p>


Xrm.Page.data.refresh(save).then(successCallback, errorCallback);

<p>More detail please see next table:</p>
<p><br /></p>
<p><span> </span></p>
<table>
    <tbody>
        <tr>
            <th>Name </th>
            <th>Type </th>
            <th>Required </th>
            <th>Description </th>
        </tr>
        <tr>
            <td>
                <p>save </p>
            </td>
            <td>
                <p>Boolean </p>
            </td>
            <td>
                <p>No </p>
            </td>
            <td>
                <p> <b>true </b> <span>  </span>if the data should be saved after it is refreshed, otherwise <span>  </span> <b>false </b>. </p>
            </td>
        </tr>
        <tr>
            <td>
                <p>successCallback </p>
            </td>
            <td>
                <p>Function </p>
            </td>
            <td>
                <p>No </p>
            </td>
            <td>
                <p>A function to call when the operation succeeds. </p>
            </td>
        </tr>
        <tr>
            <td>
                <p>errorCallback </p>
            </td>
            <td>
                <p>Function </p>
            </td>
            <td>
                <p>No </p>
            </td>
            <td>
                <p>A function to call when the operation fails. </p>
                <p>An object with the following properties will be passed: </p>
                <ul>
                    <li>

                        <b>errorCode </b>: <span>  </span> <b>Number </b>. The error code. </p>
                        <p>

                    </li>
                    <li> <b>message </b>: <span>  </span> <b>String </b>. A localized error message.  </li>
                </ul>
            </td>
        </tr>
    </tbody>
</table>

<p>Src:</p>
<p><a href="https://msdn.microsoft.com/en-us/library/dn481607.aspx" target="_blank" title="https://msdn.microsoft.com/en-us/library/dn481607.aspx">https://msdn.microsoft.com/en-us/library/dn481607.aspx</a> </p>
