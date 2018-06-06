---

title: API Configurations - idSyncAttachIframeOnWindowLoad
description: idSyncAttachIframeOnWindowLoad configurations for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Configurations - idSyncAttachIframeOnWindowLoad
SEO description: idSyncAttachIframeOnWindowLoad configurations for the Adobe Experience Cloud ID Service API
short-title: free text
doc-type: article
audience: 
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

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
