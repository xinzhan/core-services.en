---

title: API Methods - getMarketingCloudVisitorID
description: getMarketingCloudVisitorID helper method for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Methods - getMarketingCloudVisitorID
SEO description: getMarketingCloudVisitorID helper method for the Adobe Experience Cloud ID Service API
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
