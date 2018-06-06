---

title: API Configurations - disableIdSyncs
description: disableIdSyncs configurations for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Configurations - disableIdSyncs
SEO description: disableIdSyncs configurations for the Adobe Experience Cloud ID Service API
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

# disableIdSyncs

An optional, Boolean flag that disables ID synchronization.

>[!NOTE]
>This configuration was `idSyncDisableSyncs` and renamed to `disableIdSyncs` in the January 18, 2018 release of v3.0.

## Syntax
`disableIdSyncs: true|false` \(default is `false`.\)

## Code Sample

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable
   disableIdSyncs: true
});
```
