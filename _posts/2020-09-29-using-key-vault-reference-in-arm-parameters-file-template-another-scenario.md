---
layout: post
title: Using Key Vault reference in arm parameters file template, another scenario
date: 2020-09-29 09:58:01.000000000 +00:00
type: post
tag: Azure Arm Templates
---


<p>Following the last post, where an example is given on how to use Key Vault in a Arm Parameters File Template. </p>

<p>That's a great idea for using Key Vault when deploying a resource with DevOps. However, that's not the only challenge you have, another question that can be important to ask is. And what about a Service Url that you can be using in a Logic App for example. </p>

<p>First thing that probably comes to mind is: OK, let's create a parameter like [Service URL], set the value to the right URL needed for the purpose. And do that for all parameters files related to each environment.</p>

<p>Now, assume a disaster recover type of issue, where that [Service URL] is no longer available and instead you are provided a new one to configure in your Logic App. (Assuming the next steps are done only after provided the new URL)</p>

<p>Yes, you go back to your source control, change the relevant value in the parameters file, check in the code, most likely, promote the change, and finally with continuos integration it gets deployed to the specific environment. Now, I will ask you, how much time took you to perform that change, from the moment it got to you, until it was deployed? If your team has the coding and deployment well oiled, probably 1h, but as we know, not all companies have that so well implemented. What it means that it can take quite some time. </p>

<p>Depending on how the availability affects the "Customer", most likely someone will be asked questions why it took so long a small change to point to a new URL?</p>

<p>There's where the Key Vault in here can have an important paper. Why not use the Key Vault for this purpose? Probably another interesting idea for using the Key Vault, don't you think? Instead of setting the URL for every environment "hard coded" in the parameters files, just create a Key in the Key Vault for that purpose and reference it.</p>

<p>For this specific scenario, and works really well. Assuming the same disaster scenario. The only thing needed would be ask someone to create a revision on the secret, set the value and that's it. How much time needed? Probably 2 minutes.</p>

<p>Any comments/questions are welcome.</p>

<p>Hope it helps.</p>

