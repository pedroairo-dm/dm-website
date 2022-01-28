---
layout: post
title: Azure API Management Policies
date: 2020-09-17 12:07:00.000000000 +00:00
type: post
tag: Azure API Management
---

<p><!-- wp:paragraph --></p>
<p>This post is about a scenario I had to overcome when connecting to a third party API trough Azure API Management. </p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Below I just have a small explanation on what are Policies in Azure API Management. that i just copied and pasted from Microsoft.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p> After will tell the issue and the solution i had to implement.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Transcript from Microsoft "<a href="https://docs.microsoft.com/en-us/azure/api-management/api-management-policies">https://docs.microsoft.com/en-us/azure/api-management/api-management-policies</a>":</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>"Policies are a powerful capability of the system that allow the publisher to change the behavior of the API through configuration. Policies are a collection of Statements that are executed sequentially on the request or response of an API. Popular Statements include format conversion from XML to JSON and call rate limiting to restrict the amount of incoming calls from a developer. Many more policies are available out of the box.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Policy expressions can be used as attribute values or text values in any of the API Management policies, unless the policy specifies otherwise. Some policies such as the&nbsp;<a href="https://docs.microsoft.com/en-us/azure/api-management/api-management-advanced-policies#choose">Control flow</a>&nbsp;and&nbsp;<a href="https://docs.microsoft.com/en-us/azure/api-management/api-management-advanced-policies#set-variable">Set variable</a>&nbsp;policies are based on policy expressions. For more information, see&nbsp;<a href="https://docs.microsoft.com/en-us/azure/api-management/api-management-advanced-policies#AdvancedPolicies">Advanced policies</a>&nbsp;and&nbsp;<a href="https://docs.microsoft.com/en-us/azure/api-management/api-management-policy-expressions">Policy expressions</a>."</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p><strong>Scenario</strong></p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>I have 2 API's in my API Management service, one I called AUTH, the other, Services. From the Auth I just get a Token then after I will need to pass in all methods inside the Services API.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Another thing that worth to mention is, all needs to be deployed with Azure Devops Release Pipelines, don't want actually anything that needs to be deployed manually. </p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p><strong>Problem</strong></p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Because of some import restrictions of importing API definitions to Azure API Management from a Swagger file, when importing the Swagger file, the required headers, that were defined in the file were not configured in the API.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p><strong>Solution</strong></p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>I had to add a policy to check if a header was being passed from in my case a Logic App inside the API Management Service, but had to apply to all API's inside, so I could automate the deployment as said in the scenario. </p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>With this, I only had to use 2 artifacts on the release in DEV Ops, the first to create the API Management, and the other one to import an API from a swagger file to the API Management service created with the first artifact.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>The condition inside the policy is important in here because as I said, I have 2 API's inside my API Management Service, however, i only want the policy to be applied in one of the cases. </p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Hope it helps.</p>
<p><!-- /wp:paragraph --></p>
<p><!-- wp:paragraph --></p>
<p>Any trouble contact me.</p>
<p><!-- /wp:paragraph --></p>
