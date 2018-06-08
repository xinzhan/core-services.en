---

title: API Configurations - idSyncAttachIframeOnWindowLoad
description: idSyncAttachIframeOnWindowLoad configurations for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Configurations - idSyncAttachIframeOnWindowLoad
seo-description: idSyncAttachIframeOnWindowLoad configurations for the Adobe Experience Cloud ID Service API
short-title: idSyncAttachIframeOnWindowLoad
doc-type: reference
audience: admin
index: true
translate: true
version: false
private-feature-pack: false
beta: false
redirect: false

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