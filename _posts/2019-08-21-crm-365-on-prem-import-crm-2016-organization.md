---
layout: post
title: CRM 365 On Prem - Import CRM 2016 Organization (Issues)
date: 2019-08-21 08:07:03.000000000 +00:00
type: post
tag: Microsoft Dynamics 365
---

<div>
    <div>
        <div>
            <p>For the last days working on testing new features of CRM 365 Online, CRM 2016/365 On Prem and few more things.</p>
            <p></p>
            <p>And again, i had another issue, this one is really annoying, but let me explain what happened.</p>
            <p></p>
            <p>I have an environment in CRM 2016 with service pack 1.1 (<span>8.1.1.1005</span>) and we need to upgrade to V9 (365 Onprem).&nbsp;</p>
            <p></p>
            <p>So, what i did? Backup of the database, restore of the database in the new V9 environment and imported the organization, expecting that the process would run smoothly, WRONG, it didn't, and that i should already expect based on my experience.<span><br /></span></p>
            <p></p>
            <p>The error i got was: &quot;<span>09:24:11|Verbose| Error occured in UpdateRollupFieldStoredProceduresInternal: Microsoft.Crm.Metadata.MetadataAttributeMetadataNotFoundException: 'Attribute' metadata entity doesn't contain metadata attribute with Name = 'autonumberformat'.</span>&quot;</p>
            <p></p>
            <p>I googled it, and nothing. So, in these cases what should we do? And again based on my experience, let's try to import into at least a same environment major version, in this case CRM 2016 (8.1) or CRM 2016 (8.2).</p>
            <p></p>
            <p>I imported into a VM with the same version of rollup and it worked. Next deleted the database, upgraded to version (<span>8.2.2.0112),&nbsp;<span>restored again the one from V8.1</span> and imported the organization again. Voila, it worked.&nbsp;</span><span><br /></span></p>
            <p><span><br /></span></p>
            <p><span>After doing this, imported this org into the V9 environment and it worked. Perfect, i could be happy, but not completely, needed more testing.</span></p>
            <p><span><br /></span></p>
            <p><span>Again, deleted the database, upgradeed to version (<span><span style="font-size:15px;">8.2.9.19</span></span>), last update in version 8.2,&nbsp;<span>restored again the one from V8.1&nbsp;and imported the organization again. And guess what, expecting to work, of course it didn't, was expecting a field from the systemuser table.</span></span></p>
            <p><span><br /></span></p>
            <p><span>What can we learn from here, at least Microsoft is consistent, the same happened in CRM 2011, if not mistaken, we couldn't install update rollup 15, without 14, however, having the update rollup 14, we could go to update 21. What this means is, update rollup 14 was a major update release in the product, what it seams happening in here as well.</span></p>
            <p></p>
            <p>Hope it helps.</p></p>
        </div>
    </div>
</div>
