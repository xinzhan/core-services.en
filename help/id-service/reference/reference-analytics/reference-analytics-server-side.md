---

title: Server-side Implementation Mixed with JavaScript
description: Implementation of ID Service using both Server-side, mixed with JavaScript
seo-title: Adobe Experience Cloud ID Service Server-side Implementation Mixed with JavaScript
seo-description: Implementation of Adobe Experience Cloud ID Service using both Server-side, mixed with JavaScript
short-title: Test and verify
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

# Server-side Implementation Mixed with JavaScript

In some implementations, visitor IDs are passed from JavaScript to a server so that additional Analytics events \(such as a purchase\) can be sent by the server.

The ID service API provides the methods, [getMarketingCloudVisitorID](../../id-service-api/id-service-api-methods/id-service-api-methods-getmcvid.md) and [getAnalyticsVisitorID](../../id-service-api/id-service-api-methods/id-service-api-methods-getanalyticsvisitorid.md), to retrieve the ID values that can then be passed to the server.

>[!IMPORTANT]
>Make sure you check for both the Experience Cloud visitor ID and the Analytics visitor ID, and send both IDs \(if present\) to make sure any data sent is associated with the existing Analytics visitor profile.
AppMeasurement for Java does not currently support the Experience Cloud ID service.

## Data Insertion API

+ Include the Analytics visitor ID \(if set\) in the `<visitorID>` element.
+ Include the Experience Cloud visitor ID in the `<marketingCloudVisitorID>` element.

See [Supported XML Tags](https://marketing.adobe.com/developer/en_US/documentation/data-insertion/r-supported-tags).

## AppMeasurement for Java

The Experience Cloud ID Service is not currently supported by AppMeasurement for Java.