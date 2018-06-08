---

title: API Methods - appendVisitorIDsTo
description: appendVisitorIDsTo method for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Methods - appendVisitorIDsTo
seo-description: appendVisitorIDsTo method for the Adobe Experience Cloud ID Service API
short-title: appendVisitorIDsTo
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

# appendVisitorIDsTo \(Cross-Domain Tracking\)

This function lets you share a visitor's Experience Cloud ID across domains when browsers block third-party cookies. To use this function, you must have implemented the ID service and own the source and destination domains. Available in `VisitorAPI.js` version 1.7.0 or higher.

## Track Visitors Across Domains When Browsers Block Third-Party Cookies

ID service writes a first- and third-party cookie to the browser when a person visit your site \(see [Cookies and the Experience Cloud ID Service](../../getting-started-cookies.md) \). The first-party cookie contains the `MID`, a unique ID for that visitor. The third-party cookie contains another ID used by the ID service to generate the `MID`. When a browser blocks this third-party cookie, the ID service cannot:

+ Regenerate the unique ID for that site visitor when they navigate to another domain.
+ Track visitors across different domains owned by your organization.

To help solve this problem, implement `Visitor.appendVisitorIDsTo(url)`. This property lets the ID service track site visitors across multiple domains even when their browsers block third-party cookies. It works like this:

+ As a visitor browses to your other domains, the `Visitor.appendVisitorIDsTo(url)` appends the `MID` as a query parameter in the URL redirect from the original domain to the destination domain.
+ The ID service code on the destination domain extracts the `MID` from the URL instead of sending a request to Adobe for that visitor's ID. This request includes the third-party cookie ID, which is not available in this case.
+ The ID service code on the destination page uses the passed-in `MID` to track the visitor.

See the code sample for details.

## Append Visitor ID Code Sample

The following example can help you get started with `Visitor.appendVisitorIDsTo(url)`. When implemented properly, your JavaScript code could look similar to the following example.

```javascript
//Code on Domain A
var destinationURL = "www.destination.com";

//Call the ID service
var visitor = Visitor.getInstance(...);

//Append visitor IDs to the destination URL
var destinationURLWithVisitorIDs = visitor.appendVisitorIDsTo(destinationURL);
     //Result of appendVisitorIDsTo includes destination URL, Experience Cloud ID (MCMID), and Analytics ID (MCAID)
     "www.destination.com?adobe_mc=MCMID=1234|MCAID=5678"

//Redirect to the destination
```

## Dynamic Tag Management \(DTM\) and SDK Support
| Support for:                | See                                                                                                                                               |
| --------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------- |
| Dynamic Tag Managment (DTM) | [Set the appendVisitorIDTo function in DTM](https://helpx.adobe.com/dtm/kb/how-to-set-marketing-cloud-id-service-helper-function-in-adobe-d.html) |
| SDK                         | [Android ID Service Methods](https://marketing.adobe.com/resources/help/en_US/mobile/android/mc_methods.html)                                     |
| SDK                         | [iOS ID Service Methods](https://marketing.adobe.com/resources/help/en_US/mobile/ios/mc_methods.html)                                             |