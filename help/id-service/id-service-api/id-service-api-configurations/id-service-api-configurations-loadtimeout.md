---
title: api configurations - loadtimeout
description: loadtimeout configurations for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api configurations - loadtimeout
seo-description: loadtimeout configurations for the adobe experience cloud id service api
short-title: loadtimeout
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-configurations/id-service-api-configurations-loadtimeout.md
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

# loadTimeout

Sets a timeout interval in milliseconds. Used to tell other solutions \(e.g., Analytics, Audience Manager, Target, etc.\) how long to wait for a response from the ID service.

## Syntax

`loadTimeout: interval in milliseconds` 

The default value is 30,000 milliseconds \(30 seconds\). We strongly recommend that you *do not* change the default value.

>[!NOTE]
>Calls to the ID service are asynchronous in relation to other, non-Adobe code on the page. As a result, increasing or decreasing the timeout interval does not change the rate at which your page renders content. However, long timeout intervals may affect page load times as measured by common network monitoring tools, but rendering time is unaffected.

## Code Sample

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable. Example sets the timeout to 10,000 milliseconds (10 seconds).
   loadTimeout:10000
});
```