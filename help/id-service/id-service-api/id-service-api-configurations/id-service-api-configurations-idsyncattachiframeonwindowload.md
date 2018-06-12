---
title: api configurations - idsyncattachiframeonwindowload
description: idsyncattachiframeonwindowload configurations for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api configurations - idsyncattachiframeonwindowload
seo-description: idsyncattachiframeonwindowload configurations for the adobe experience cloud id service api
short-title: idsyncattachiframeonwindowload
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-configurations/id-service-api-configurations-idsyncattachiframeonwindowload.md
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

# idSyncAttachIframeOnWindowLoad

An optional, Boolean flag that controls how the Experience Cloud ID service loads the ID synchronization iFrame.

## Syntax

`idSyncAttachIframeOnWindowLoad= true|false` \(default value is `false`\)

When `idSyncAttachIframeOnWindowLoad: true` the ID service loads the ID synchronization iFrame on window load. By default, the ID service loads the ID synchronization iFrame as fast as possible instead of on window load.

## Code Sample

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable. Example loads ID sync iFrame on window load instad of ASAP.
   idSyncAttachIframeOnWindowLoad: true
});
```