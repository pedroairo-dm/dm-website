---
layout: post
title: Microsoft CRM 4.0 - Hide a section
date: 2013-05-08 16:39:00.000000000 +00:00
type: post
tag: Microsoft CRM 4
---

function OnCrmPageLoad()  
{  
//Hide the Second Section in the first Tab  
ToggleSection( 0 , 1 , "none" /\* "inline" \*/);  
}

// Tabs and Section Collections are zero based  
function ToggleSection( tabIndex , sectionIndex , displayType )  
{  
var sec = document.getElementById( "tab" + tabIndex );  
sec.childNodes.rows.style.display = displayType;  
}

//Entry Point  
OnCrmPageLoad();