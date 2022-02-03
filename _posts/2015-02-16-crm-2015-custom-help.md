---
layout: post
title:  Microsoft Dynamics 2015 - Custom Help
date: 2015-02-16 12:49:00.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---

Sometimes we hear from the users, i want do something but the standard Help does not help, what would be great is if the Help could be customized according to the customer needs.

Found this article on microsoft, hope it can help you.

Microsoft Dynamics CRM has a knowledge base application built in for online help. This help is hosted on the Customer Center, a central location where users can find articles, videos, eBooks, best practices, and tips regarding topical issues.
In addition to the built-in help, Microsoft Dynamics CRM offers customizable help and tooltips to provide contextual information to users filling in forms. You can replace default Help with the custom Help of your choice, at the global (organization) level or entity level. Custom Help makes the content exposed through the Help links more relevant to the user’s day-to-day activities. With a single, global URL you can override the out-of-the-box Help links for all customizable entities. Per entity URLs override the out-of-the-box Help links on grids and forms for a specific customizable entity. You can include additional parameters in the URL, such as language code and entity name. These parameters allow a developer to add functionality to redirect the user to a page that’s relevant to their language or the entity context within the application. The entity level custom Help settings are solution aware, therefore you can package them as a part of the solution and transport them between organizations or distribute them in solutions. Custom tooltips provide the ability to set the text that appears as a tooltip when the field is displayed in a form. Tooltips are also solution aware.

### Set up customizable Help

As an administrator, you can use the settings to override default Help at the global level, in Microsoft Dynamics CRM > Settings > Administration > System settings >General tab, as shown here.
Global custom Help in Dynamics CRM

To override the default Help for an entity, use the settings in Microsoft Dynamics CRM > Settings > Customization > Customize the system > Components > Entity >General tab. You must first enable custom Help at the global level.
Entity level custom Help in Dynamics CRM

To append the parameters to a URL, set Append Parameters to URL in the System settings > General tab to Yes. Specify the parameters that will be attached to the URL:
User Language Code: userlcid
Entity Name: entity
Entry Point: hierarchy chart or form
Form Id: formid
