---
layout: post
title: Microsoft Dynamics 2015 - Importing an .xlsx file Issue
date: 2016-02-12 01:41:21.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p><font size="2">Trying to import an exported excel file on CRM 2015 Onprem when i came across with an error i found really strange.</font></p>

<p><font size="2"><img alt="" src="{{ site.baseurl }}/assets/2016/02/Capture.JPG" />  <br /></font></p>

<p><font size="2">Googling i found few posts talking about this kind of issue, but it was related to option sets fields used in the file, and in this case it was not the problem.</font></p>

<p><font size="2">I went to other environments and everything was working correctly, what for me was even more strange.</font></p>

<p><font size="2">When things like this happen, i only know one way of checking what is happening (<span style="background-color:transparent;line-height:1.8;">DiagTool), like the A-Team of CRM. If nothing can help you, Event Viewer, Error Messages, ..., we should hire the A-Team (DiagTool).</span></font></p>

<p><span style="background-color:transparent;line-height:1.8;"><font size="2">I just enabled the trace, and i have found this:</font></span></p>

<p><span style="background-color:transparent;line-height:1.8;"><i><font size="2">&quot; The value of 'filetypecode' on record of type 'importfile' is outside the valid range.&quot;<br /></font></i></span></p>

<p><span style="background-color:transparent;"><span style="line-height:1.8;"><font size="2">So, i googled few more hours, and nothing. So, in that case i went to the database, something i don't do often, but i did.</font></span></span></p>

<p><span style="background-color:transparent;"><span style="line-height:1.8;"><font size="2">After 1/2 hour found this in one Organization where the import was not working:</font></span></span></p>

<p><span style="background-color:transparent;"><font color="#0c00ff" size="2"><span style="line-height:1.8;">select * from AttributePicklistValue<br /></span></font></span></p>
<p><font size="2"><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">where AttributePicklistValue.OptionSetId = (<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">SELECT        OptionSetId<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">FROM            MetadataSchema.OptionSet<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">WHERE        (Name LIKE '%importfile_filetypecode%')<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">)</span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;"><br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">select * from LocalizedLabel<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">where objectid =<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">(<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">SELECT        OptionSetId<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">FROM            MetadataSchema.OptionSet<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">WHERE        (Name LIKE '%importfile_filetypecode%')<br /></span></font></span><span style="background-color:transparent;"><font color="#0c00ff"><span style="line-height:1.8;">)</span></font></span></font></p></p>

<p><font size="2">The first query in that Organization was returning only 3 Rows, and for who doesn't know, and i think i can say this: a row value in that table means the file types available for importing (0-csv, 1-xml, 2-zip and 3-xlsx), in my case i didn't have the value 3 in that Organization.</font></p>

<p><font size="2">Then, Eureka, i remembered, importing .xslx files only became available in CRM 2015 with UR 0.2, so, i preformed the uninstall of that UR, restarted the server, installed again and <i>voila</i> it started to work.</font></p>

<p><font size="2">I don't know what really happened before because i didn't have any kind of warning or error when installing the UR 0.2 previously, but got it working.</font></p>

<p><font size="2">Hope it helps.</font></p>