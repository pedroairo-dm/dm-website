---
layout: post
title: Microsoft Dynamics 2015 - Assembly Versioning and Solutions
date: 2015-03-12 14:45:11.000000000 +00:00
type: post
tag: Microsoft Dynamics 2015
---


<p><span> </span></p>
<p> <font ><span>How many times after importing a solution with Plugins, we have either errors because of versions, missing steps, the system complaining of something, i think the next few lines will help to understand what happens in the back-end when importing a solution with Plugins (changed code or even less or more steps). </span> </font></p>

<p> <font ><span>From MSDN  <span>  </span> <span>  <span>  </span> </span> <a href="https://msdn.microsoft.com/en-us/library/gg309620.aspx" target="_blank" title="https://msdn.microsoft.com/en-us/library/gg309620.aspx">https://msdn.microsoft.com/en-us/library/gg309620.aspx <span>  </span> <span>  <span>  </span> </span> </a>  </span> </font></p>

<p> <font ><span>Plug-in assemblies can be versioned using a number format of major.minor.build.revision defined in the Assembly.info file of the Microsoft Visual Studio project. Depending on what part of the assembly version number is changed in a newer solution, the following behavior applies when an existing solution is updated through import. </span> </font></p>

<p> <font ><span>The build or revision assembly version number is changed. </span> </font></p>
<ul>
    <li><font ><span>This is considered an in-place upgrade. The older version of the assembly is removed when the solution containing the updated assembly is imported. Any pre-existing steps from the older solution are automatically changed to refer to the newer version of the assembly. </span></font></li>
</ul>
<p>
    <font ><span>The major or minor assembly version number, except for the build or revision numbers, is changed. </span></font>
    <ul>
        <li><font ><span>When an updated solution containing the revised assembly is imported, the assembly is considered a completely different assembly than the previous version of that assembly in the existing solution. Plug-in registration steps in the existing solution will continue to refer to the previous version of the assembly. If you want existing plug-in registration steps for the previous assembly to point to the revised assembly, you will need to use the Plug-in Registration tool to manually change the step configuration to refer to the revised assembly type. This should be done before exporting the updated assembly into a solution for later import. </span></font></li>
    </ul>
</p>
<p> <font ><span> </span> <span> </span> </font></p>
<div> </div>
<p> <span><font >Hope it helps. </font></span> </p></p>
