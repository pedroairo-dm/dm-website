---
layout: post
title: Microsoft Dynamics 2015 - Javascript - { Personal Opinion 1 - Considerations on customizing CRM Forms }
date: 2015-04-28 04:10:18.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p>Extending a lookup control for people that have been working with CRM sometimes looks like a nightmare, and why? </p>

<p>The reason for this is related with upgrades, I remember for instance that form CRM 3.0 to CRM 4.0, the way our development team was using this functionality on upgrading it would break the custom filtering.</p>

<p>Honestly, i'm not the kind of guy that likes to extend to much the CRM in terms of Javascript because of many reasons, <i><u>i'm not saying i don't customize</u></i>, but <i><u>i think in very single detail</u></i>, what are the consequences of doing everything, <u><i>before doing it</i></u>.</p>

<p>Usually everything gets clear to me when i think on the word &quot;Upgrade&quot;, if i think:</p>
<p>Ok, i can do this in 2 hours instead of spending 8 hours, however, in the future i will be in trouble because it can break, i prefer to be honest to the customer and say what i think is the best in here.</p>

<p>Sometimes, the last sentence in CRM is more clear for people with years of experience in the product, because we got already so many hours trying to fix things that were Out of The Box that from one minute to the other with no reason just stop to work. </p>

<p>In here i will spend few more hours because it is my work that's on the spotlight.</p>

<p>Now everything is much better in terms of the framework provided from Microsoft to customize the forms, it is possible using that framework to control almost every type of control (field, web  resource, grid,..) that is indeed a big help for us developers.</p>

<p><span style="line-height:23.4px;">I will leave in here the word </span><span style="line-height:23.4px;"> <b><u><i>Encapsulation</i></u></b>, in few words is: &quot;Packing of data and functions into a single component.&quot;, and why? Because if instead of doing methods without thinking of </span>reusing them, is already as headache, if something breaks and you have to fix in every single location you are using that piece of code, so, every time i need to do something i think, am i seeing to use this in more than one place? If yes, ok, lets create a function in a common file. </p>
<p>With this approach, if something needs to be changed in that functionality, you need only to change in one place.<span style="background-color:transparent;line-height:1.8;"> </span></p>

<p>Hope you like, and comments are more than welcome.</p>

