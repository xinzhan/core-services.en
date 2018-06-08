---

title: API Configurations - loadTimeout
description: loadTimeout configurations for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Configurations - loadTimeout
seo-description: loadTimeout configurations for the Adobe Experience Cloud ID Service API
short-title: loadTimeout
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