---

title: API Configurations - disableThirdPartyCalls
description: disableThirdPartyCalls configurations for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Configurations - disableThirdPartyCalls
seo-description: disableThirdPartyCalls configurations for the Adobe Experience Cloud ID Service API
short-title: disableThirdPartyCalls config
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

# disableThirdPartyCalls

An optional, Boolean flag that prevents the ID service from making calls to other domains.

## Syntax
`disableThirdPartyCalls: true|false` \(default is `false`.\)

When `disableThirdPartyCalls: true`, the ID service will not make calls to other domains.

## Purpose 

This variable is designed for customers who need:

+ To prevent the ID service from making calls from their secure, authenticated pages.
+ Site visitors to have a Experience Cloud ID `MID`.
+ Their other Experience Cloud solutions to work properly.

## Implementation Strategy

Other Experience Cloud solutions rely on the `MID`, so the ID service calls Adobe to return and set this ID. If you need to stop the ID service from making calls from authenticated sections of your website, then let it make these required calls from pages that don't require authentication first.

After your site visitor has a `MID`, then you can set `disableThirdPartyCalls= true` in the ID service code on the authenticated sections of your site.

The assumption here is that most, if not all, of your customers will navigate to an authentication page before they get access to the secure parts of your site.

## Code Sample

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable
   disableThirdPartyCalls: true
});
```