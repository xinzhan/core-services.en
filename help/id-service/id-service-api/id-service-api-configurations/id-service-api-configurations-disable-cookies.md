---
title: api configurations - disablethirdpartycookies
description: disablethirdpartycookies configurations for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api configurations - disablethirdpartycookies
seo-description: disablethirdpartycookies configurations for the adobe experience cloud id service api
short-title: disablethirdpartycookies
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-configurations/id-service-api-configurations-disable-cookies.md
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

# disableThirdPartyCookies

An optional, Boolean flag that prevents the Experience Cloud ID service from returning the third-party, demdex.net cookie.

>[!NOTE]
>This configuration was `idSyncDisable3rdPartySyncing` and renamed to `disableThirdPartyCookies` in the January 18, 2018 release of v3.0.

## Syntax 
`disableThirdPartyCookies: true|false` \(default is `false`.\) For `VisitorAPI.js` v1.5.3, or greater.

When `disableThirdPartyCookies: true`, the ID service does not return the third-party, `demdex.net` cookie \(see [Cookies](id-service-api-configurations-disable-cookies.md)\). 

If a site visitor already has this cookie in their browser, the ID service won't use it to create a new Experience Cloud ID \(MID\) or return an existing ID. Instead, the ID service creates a new, random MID in the first-party cookie. Once enabled, you can collect data with the ID service and share it across different Experience Cloud solutions.

## Code Sample 

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable
   disableThirdPartyCookies: true
});
```