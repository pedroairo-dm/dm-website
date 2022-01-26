---
layout: post
title: Configuring Arm Templates (Deploying to different environments)
date: 2020-09-22 12:07:00.000000000 +00:00
type: post
tag: Azure Arm Templates
---
<p><!-- wp:paragraph --></p>
<p>When developing around Azure, more specifically with Azure Logic Apps, Azure Functions, Azure API Management, and with almost no experience or none experience at all a good starting point it is using the browser.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>This allows us to start doing our tasks, practising, testing and then deploying to a different environment.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>I read many articles with different views of how to achieve this. Usually in any IT Company when we are developing we all need to use a source control tool, in this case it only applies to Microsoft Devops, and for some artifacts I think we need to be using Premium account.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>I started the same way, I went to Azure Portal and created few Logic Apps to become proficient with the technology. Not to getting in here with a long story, I will cut things short now and if you need anything, comment in here or contact us.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Using Visual Studio and installing Azure extensions allowed me to start using my Visual Studio in conjunction with my TFS Online (Git in my case).</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>The reason of this post is more to have in mind a way to automate(not the focus of this post, but helps in terms of configuration) the deployment of the Resources to Azure.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p><em>Assumptions here:</em></p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:list --></p>
<ul>
    <li>Use Visual Studio</li>
    <li>A resource group in Azure means an "Environment" </li>
    <li>Full automation of Deployment trough Azure Dev Ops</li>
</ul>
<p><!-- /wp:list --></p>
<p><!-- wp:paragraph --></p>
<p><em><strong>High level steps below</strong></em>:</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:list {"ordered":true} --></p>
<ol>
    <li>
        Created a Visual Studio 'Azure Resource Group' and used a Logic App template
        <ol>
            <li>
                Created 2 files
                <ol>
                    <li>LogicApp.json</li>
                    <li>LogicApp.parameters.json</li>
                </ol>
            </li>
            <li>
                I changed the naming convention of the parameters file and created another file
                <ol>
                    <li>LogicApp.parameters.dev.json</li>
                    <li>LogicApp.parameters.uat.json</li>
                </ol>
            </li>
            <li>
                Opened the LogicApp.json design mode
                <ol>
                    <li>Configured with recurrence trigger</li>
                    <li>Added an artifact 'Initialize variable' and set value to 'Hello World'</li>
                </ol>
            </li>
            <li>Opened the LogicApp.json as json file and configured the following:</li>
            <li>
                Inside the parameters node:
                <ol>
                    <li>"Environment": { "type": "string", "defaultValue": "Dev" }</li>
                    <li>"LogicAppName": { "type": "string",  "defaultValue": "[concat('MyLogicAPp-', parameters('Environment'))]" }</li>
                </ol>
            </li>
            <li>
                In the LogicApp.parameters.dev.json inside the parameters node:
                <ol>
                    <li>"Environment": { "type": "string", "value": "Dev" }</li>
                </ol>
            </li>
            <li>
                In the LogicApp.parameters.uat.json inside the parameters node:
                <ol>
                    <li>"Environment": { "type": "string", "value": "Uat" }</li>
                </ol>
            </li>
        </ol>
    </li>
</ol>
<p><!-- /wp:list --></p>
<p><!-- wp:paragraph --></p>
<p>This is a personal option of deploying to different environments, but as i saw there are many ways of doing the same. Hope it is clear.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>The result in terms of naming convention would be something like:</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:list {"ordered":true} --></p>
<ol>
    <li>
        Azure Resource Groups
        <ol>
            <li>
                Dev
                <ol>
                    <li>
                        Logic Apps
                        <ol>
                            <li>MyLogicApp-Dev</li>
                        </ol>
                    </li>
                </ol>
            </li>
            <li>
                Uat
                <ol>
                    <li>
                        Logic Apps
                        <ol>
                            <li>MyLogicApp-Uat</li>
                        </ol>
                    </li>
                </ol>
            </li>
        </ol>
    </li>
</ol>
<p><!-- /wp:list --></p>
<p><!-- wp:paragraph --></p>
<p>Why this option? Because if you use Azure Dev Ops, you know for instance that navigating for example to Logic Apps area:</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Without doing this naming convention the result would be something like.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:table --></p>
<figure class="wp-block-table">
    <table>
        <tr>
            <td>Name</td>
            <td>Resource Group</td>
        </tr>
        <tr>
            <td>MyLogicApp</td>
            <td>Dev</td>
        </tr>
        <tr>
            <td>MyLogicApp</td>
            <td>Uat</td>
        </tr>
    </table>
</figure>
<p><!-- /wp:table --></p>
<p><!-- wp:paragraph --></p>
<p>Doing this naming convention the result would be something like.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:table --></p>
<figure class="wp-block-table">
    <table>
        <tr>
            <td>Name</td>
            <td>Resource Group</td>
        </tr>
        <tr>
            <td>MyLogicApp-Dev</td>
            <td>Dev</td>
        </tr>
        <tr>
            <td>MyLogicApp-Uat</td>
            <td>Uat</td>
        </tr>
    </table>


</figure>
<p><!-- /wp:table --></p>
<p><!-- wp:paragraph --></p>
<p>If you have one or two logic apps that's probably fine doing without appending the environment to the name, but honestly I found that working in larger projects using Azure this is actually beneficial.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Any additional information or help please don't hesitate in contacting us.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Hope it helps. </p>
<p><!-- /wp:paragraph --></p>
