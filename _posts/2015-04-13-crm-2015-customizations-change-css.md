---
layout: post
title: Microsoft Dynamics 2015 - Customizations - Change CSS
date: 2015-04-13 05:47:34.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p>Before staring to tell what was happening to me, i have to say I'm the first to say to avoid this kind of customizations, however and because of a need i had to do this.</p>

<p>I needed to add a border to the fields in a form even if they were not with the focus on them. So, the only way of doing that is applying some kind of CSS to them, i found some articles and i have chosen the below one.</p>

<p> <span>function load_css_file(filename) { </span></p>
<p><span> var fileref = document.createElement(&quot;link&quot;); </span></p>
<p><span> fileref.setAttribute(&quot;rel&quot;, &quot;stylesheet&quot;); </span></p>
<p><span> fileref.setAttribute(&quot;type&quot;, &quot;text/css&quot;); </span></p>
<p><span> fileref.setAttribute(&quot;href&quot;, filename); </span></p>
<p><span> document.getElementsByTagName(&quot;head&quot;)[0].appendChild(fileref);</span></p>
<p><span>}</span></p>

<p><span>function customizeFormsCss() { //inject css file to the header load_css_file(&quot;WebResources/ttt_CRM.CSS.FormCustomization&quot;); </span></p>
<p><span>}</span></p>

<p><span>Now, it comes the funny part that made me waist a lot of time. A colleague just started to do the developments, and it was working in his laptop (IE and Chrome), however it was not working in mine. So, the next thing that i did was, lets import to a new organization, and in my laptop started to work.</span></p>

<p><span>So, after hours and because i deployed as well to a VM, into two different organizations, and it was working perfectly. </span></p>

<p><span >After </span>digging a little bit more, and because with this i taught that only could be something related to a configuration in the Organization, i discovered the reason. :)</p>

<p><span >In the one that it was not working, i have selected the below check box, after not selecting it started to work.</span></p>

<p><span ><img alt="" src="{{ site.baseurl }}/assets/2015/04/high contrast.png" />  <br /></span></p>

<p><span >Hope to help more people with this.</span></p>


