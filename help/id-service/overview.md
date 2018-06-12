---
title: overview of experience cloud id service
description: the role of the experience cloud id service in the adobe experience cloud.
seo-title: experience cloud id service introduction and overview
seo-description: introduction and overview to the adobe experience cloud id service.
short-title: overview
doc-type: reference
audience: admin
index: true
translate: true
version: false
private-feature-pack: false
beta: false
redirect: false
product: core services id service
cloud: experience cloud
archetype: admin
user-guide: id service admin guide
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/overview.md
git-issue: https://git.corp.adobe.com/AdobeDocs/core-services.en/issues/new
git-repo: https://git.corp.adobe.com/adobedocs/core-services.en
---
<!--Meta Data Values

**Required Meta for search optimization and page data**

title: free text string

description: free text string

seo-title: free text string

seo-description: free text string

**Optional Meta for extended capabilities**

audience:
all (default), admin, developer, end-user
 
index: true (default), false
 
translate:
true (default), false
 
doc-type:
reference (default), tutorials

version:
false (default), Classic, Standard, 6.5, 6.4, 6.3, 6.2
 
private-feature-pack:
false (default), true
 
beta:
false (default), true
 
redirect:
false (default), pathname
-->

# Overview of Experience Cloud ID Service
The role of the Experience Cloud ID service in the Adobe Experience Cloud.

## The Experience Cloud ID Service: A Foundational Element of Core Services
The Experience Cloud ID service enables the common identification framework for the Experience Cloud Core Services, solutions, and customer attributes and audiences in the People core service. It works by assigning a unique, persistent ID to a site visitor.

When your organization implements the ID service, this ID lets you identify the same site visitor and their data in different Experience Cloud solutions.

![Identifying a site visitor with the Experience Cloud ID Service](assets/with-without-id-service.png)

The ID service can also replace the different solution-specific IDs (e.g., Analytics `AID`). And, through the Customer IDs and Authentication States functionality, the ID service lets you pass in your own customer IDs to the Experience Cloud.

>[!IMPORTANT]
>Keep in mind, however, that the ID service only works with the solutions you're already subscribed to. It won't provide access to other products if you're not signed up for them.

Going forward, the ID service is an integral component of many current and future Experience Cloud features, enhancements, and services. Currently, the ID service supports Analytics, Audience Manager, and Target. And, it is required if you want to participate in the Adobe Experience Cloud Device Co-op.

If you have not implemented the ID service, now is the time to start considering a migration strategy. For more information about the importance and role of the ID service, see [Why the Experience Cloud ID Service Should be on Your Radar](http://blogs.adobe.com/digitalmarketing/analytics/why-new-adobe-marketing-cloud-id-service-should-be-on-your-radar/).

## Feature Summary
To sum up, the ID service:

+ Creates a common key or ID which can be used to link profiles and identities.
+ Uniquely identifies a device across multiple solutions.
+ Sets a first-party cookie in customer’s domain to ensure tracking on same domain. See Experience Cloud.
+ Receives aliases and ID mappings from Experience Cloud customers and partners.
+ Manages ID synchronization within the Experience Cloud.
+ Supports ID synchronization with different third-parties across the ad tech ecosystem.

## ID Service Requirements
Your solution and other Adobe code libraries [must meet these requirements](reference/reference-requirements.md) before you can use the ID service.

+ [How it works - Cookies and the Experience Cloud ID Service](getting-started/getting-started-cookies-id-service.md)
+ [Cookies and the Experience Cloud ID Service](getting-started/getting-started-cookies.md)
+ [How the Experience Cloud ID Service Requests and Sets IDs](getting-started/getting-started-id-request.md)
+ [Understanding ID Syncronization and Match Rates](getting-started/getting-started-match-rates.md)