---

title: cookieLifetime for ID Service
description: This variable lets you override the default lifetime interval for the AMCV cookie
seo-title: cookieLifetime for Adobe Experience Cloud ID Service
seo-description: This variable lets you override the default lifetime interval for the AMCV cookie
short-title: cookieLifetime
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

# cookieLifetime

This variable lets you override the default lifetime interval for the AMCV cookie. By default, Experience Cloud ID service cookies expire after 24-months. Set the time interval in seconds.

## Syntax

*cookieLifetime:lifetime in seconds*

## Code Sample

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   trackingServer: "Insert tracking server here here",  //Same as s.trackingServer
   trackingServerSecure: "Insert secure tracking server here",  //Same as s.trackingServerSecure

   //For CNAME support only. Exclude these variables if you're not using CNAME
   marketingCloudServer: "Insert tracking server here",
   marketingCloudServerSecure: "Insert secure tracking server here",

   //Function variable. Example changes expiration period to 12-months.
   cookieLifetime:31536000
});
```