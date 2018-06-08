---

title: API Methods - getMarketingCloudVisitorID
description: getMarketingCloudVisitorID helper method for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Methods - getMarketingCloudVisitorID
seo-description: getMarketingCloudVisitorID helper method for the Adobe Experience Cloud ID Service API
short-title: getMarketingCloudVistorID
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

# getMarketingCloudVisitorID

`getMarketingCloudVisitorID` returns the Experience Cloud visitor ID.

## Syntax
`var variable name = visitor.getMarketingCloudVisitorID()`

This method typically used with custom solutions that require reading the visitor ID. It is not used by a standard implementation. `getMarketingCloudVisitorID` also works with callback functions to read Analytics IDs and bring them in to your system or application.

```javascript
//callback function
var useMarketingCloudID = function(id){
     //whatever your function does with the Experience Cloud ID
};

//get the Experience Cloud ID and pass it to the function
var mcID = visitor.getMarketingCloudVisitorID(useMarketingClouidID)
```

>[!NOTE]
>If you're an Analytics customer, also check for and send the Analytics ID to your function. For example, you would want both identifiers when passing the visitor ID in a hidden form element to a server-side application that uses the data insertion API.
>
>In this case, you should collect and return the Experience Cloud and Analytics visitor IDs. See [getAnalyticsVisitorID](id-service-api-methods-getanalyticsvisitorid.md).
