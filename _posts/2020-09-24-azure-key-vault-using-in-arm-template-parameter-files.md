---
layout: post
title: Azure Key Vault - Using in arm template parameter files
date: 2020-09-24 09:58:01.000000000 +00:00
type: post
tag: Azure Arm Templates
---


<p><!-- wp:paragraph --></p>
<p>Let's start from the beginning, Microsoft says:</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>"Azure Key Vault is a tool for securely storing and accessing secrets. A secret is anything that you want to tightly control access to, such as API keys, passwords, or certificates. A vault is a logical group of secrets."</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>A colleague of mine told me about using a key vault reference in an arm template parameters file, the idea would be for accessing data like a password of a user for an SQL Server connection. </p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>The idea was brilliant, first, no passwords referenced in any file, second, deploying to a new environment, only thing that we need to change is the Resurce Group name, and Artifact name (Key Vault Name) from the ID of the resource.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>That part it is easy if you work with some standard naming convention, for Azure purpose, and mentioned already in my previous post. Link: https://dynamicsmonster.wordpress.com/2020/09/22/configuring-arm-templates-deploying-to-different-environments/</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>As an example please see below JSON parameter, this is an example from a parameter file.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph {"fontSize":"small"} --></p>
<p class="has-small-font-size">"sql_1_password": {<br />"reference": {<br />"keyVault": {<br />"id": "/subscriptions/[Dubscription Id]/resourceGroups/[Resource Group]/providers/Microsoft.KeyVault/vaults/[Key Vault Name]"<br />},<br />"secretName": "[Sql Password]"<br />}</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>So, you would have one parameter file per environment, the only thing you would need to change from example above is [Resoure Group] and [Key Vault Name], keeping the same secret name in the other key vaults in the other resource groups will work with no problems at all.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>In next post will tell another scenario where using Key Vault in arm parameters files is useful.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Anything please comment here or contact us.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Hope it helps.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Follow us.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Thank you.</p>
<p><!-- /wp:paragraph --></p>
