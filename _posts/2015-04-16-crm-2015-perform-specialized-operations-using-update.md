---
layout: post
title: Microsoft Dynamics 2015 - Perform specialized operations using Update
date: 2015-04-16 15:12:14.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p>Functionality now available on release of new sdk release (7.1.a ,March 2015)</p>

<p>Before this release, some specialized messages should be called to update some entity fields, methods like assign request or set state request.</p>

<p>However, from this release on it would be able to be done from the Update message. </p>

<p>Please see the below table to see what are the deprecated methods.</p>

<table>
    <tbody>
        <tr>
            <th>Deprecated message request </th>
            <th>Attribute to update </th>
        </tr>
        <tr>
            <td>
                <p> <a href="https://msdn.microsoft.com/en-us/library/microsoft.crm.sdk.messages.assignrequest.aspx">AssignRequest </a> </p>
            </td>
            <td>
                <p>&lt;entity&gt;. <b>OwnerId </b>* </p>
            </td>
        </tr>
        <tr>
            <td>
                <p> <a href="https://msdn.microsoft.com/en-us/library/microsoft.crm.sdk.messages.setstaterequest.aspx">SetStateRequest </a> </p>
            </td>
            <td>
                <p>&lt;entity&gt;. <b>StateCode </b>* </p>
                <div>
                    <table>
                        <tbody>
                            <tr>
                                <th align="left"> <img alt="Important" src="{{ site.baseurl }}/assets/2015/04/clear.gif" title="Important" />Important </th>
                            </tr>
                            <tr>
                                <td>
                                    For <span>  </span> <b>SLA </b> <span>  </span>and <span>  </span> <b>RoutingRule </b> <span>  </span>entities, changing the <span>  </span> <b>OwnerId </b> <span>  </span>and <span>  </span> <b>StateCode </b> <span>  </span>in a single <span>  </span> <b>Update </b> <span>  </span>message invocation is not supported and results in an exception. </p>
                                </td>
                            </tr>
                        </tbody>
                    </table>
                    </p>
                </div>
            </td>
        </tr>
        <tr>
            <td>
            </td>
            <td>
            </td>
        </tr>
        <tr>
            <td>
                <p> <a href="https://msdn.microsoft.com/en-us/library/microsoft.crm.sdk.messages.setparentsystemuserrequest.aspx">SetParentSystemUserRequest </a> </p>
            </td>
            <td>
                <p> <b>SystemUser.ParentSystemUserId </b> </p>
            </td>
        </tr>
        <tr>
            <td>
                <p> <a href="https://msdn.microsoft.com/en-us/library/microsoft.crm.sdk.messages.setparentteamrequest.aspx">SetParentTeamRequest </a> </p>
            </td>
            <td>
                <p> <b>Team.BusinessUnitId </b> </p>
            </td>
        </tr>
        <tr>
            <td>
                <p> <a href="https://msdn.microsoft.com/en-us/library/microsoft.crm.sdk.messages.setparentbusinessunitrequest.aspx">SetParentBusinessUnitRequest </a> </p>
            </td>
            <td>
                <p> <b>BusinessUnit.ParentBusinessUnitId </b> </p>
            </td>
        </tr>
        <tr>
            <td>
                <p> <a href="https://msdn.microsoft.com/en-us/library/microsoft.crm.sdk.messages.setbusinessequipmentrequest.aspx">SetBusinessEquipmentRequest </a> </p>
            </td>
            <td>
                <p> <b>Equipment.BusinessUnitId </b> </p>
            </td>
        </tr>
        <tr>
            <td>
            </td>
            <td>
            </td>
        </tr>
        <tr>
            <td>
                <p> <a href="https://msdn.microsoft.com/en-us/library/microsoft.crm.sdk.messages.setbusinesssystemuserrequest.aspx">SetBusinessSystemUserRequest </a> </p>
            </td>
            <td>
                <p> <b>SystemUser.BusinessUnitId </b> </p>
            </td>
        </tr>
    </tbody>
</table>
<p>*&lt;entity&gt; refers to any entity that provides this attribute. </p>
<p> <br /></p>

<p>Source of the information:</p>
<p><a href="https://msdn.microsoft.com/en-us/library/dn932124.aspx" target="_blank" title="https://msdn.microsoft.com/en-us/library/dn932124.aspx">https://msdn.microsoft.com/en-us/library/dn932124.aspx</a> </p>

