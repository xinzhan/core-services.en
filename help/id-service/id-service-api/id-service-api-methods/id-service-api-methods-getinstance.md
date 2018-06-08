---

title: API Methods - getInstance
description: getInstance method for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Methods - getInstance
seo-description: getInstance method for the Adobe Experience Cloud ID Service API
short-title: getInstance
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

# getInstance

`getInstance` returns a visitor ID object for the specified Experience Cloud organization ID. This is required to initialize the visitor ID object provided to AppMeasurement through `s.visitor`.

## Syntax

### JavaScript

```javascript
var visitor = Visitor.getInstance("INSERT-MARKETING-CLOUD-ORGANIZATION-ID-HERE", {
     trackingServer: "INSERT-TRACKING-SERVER-HERE", // same as s.trackingServer
     trackingServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE", // same as s.trackingServerSecure

     // To enable CNAME support, add the following configuration variables
     // If you are not using CNAME, DO NOT include these variables
     marketingCloudServer: "INSERT-TRACKING-SERVER-HERE",
     marketingCloudServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE" // same as s.trackingServerSecure
});
```

>[!IMPORTANT]
>*Do not* instantiate the Visitor function with `var visitor = new Visitor`. You must use the proper function call noted here. Applies to VisitorAPI.js code library v3.0 or higher.

### ActionScript / Flash

```Javascript
import com.adobe.mc.Visitor;
...
var visitor = Visitor.getInstance("INSERT-MARKETING-CLOUD-ORGANIZATION-ID-HERE", {
     trackingServer: "INSERT-TRACKING-SERVER-HERE", // same as s.trackingServer
     trackingServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE", // same as s.trackingServerSecure

     // To enable CNAME support, add the following configuration variables
     // If you are not using CNAME, DO NOT include these variables
     marketingCloudServer: "INSERT-TRACKING-SERVER-HERE",
     marketingCloudServerSecure: "INSERT-SECURE-TRACKING-SERVER-HERE" // same as s.trackingServerSecure
});
```

If `getInstance` doesn't find an existing instance, an new instance is created and returned. This is similar to the [`s_gi()` function](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=function_s_gi.html) in AppMeasurement.

## Common Use

The Experience Cloud ID service API maintains a list of all instances created for each Adobe Experience Cloud organization ID.

If the application using the ID service API isn't passing around a reference to the instance, it can find that instance by calling `getInstance` instead of creating a new one. This also provides support for multiple instances for different organizations in the same web page or application.

This is useful for applications that don't have a clear `init` phase, but need to call into the ID service API in multiple places. You can call `getInstance` in all of those places and the first to execute will create the instance. The existing instance will be returned by subsequent calls.