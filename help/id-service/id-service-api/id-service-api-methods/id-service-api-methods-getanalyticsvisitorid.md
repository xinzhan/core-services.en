---

title: API Methods - getAnalyticsVisitorID
description: getAnalyticsVisitorID method for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Methods - getAnalyticsVisitorID
seo-description: getAnalyticsVisitorID method for the Adobe Experience Cloud ID Service API
short-title: getAnalyticsVisitorID
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

# getAnalyticsVisitorID

Returns the legacy Analytics ID \(if any\) that was stored in the `s_vi` cookie before the Experience Cloud ID service was implemented. It returns an empty string if a visitor was never assigned an Analytics ID.

## Syntax

`var analyticsID = visitor.getAnalyticsVisitorID()` 

Typically, this function is used with custom solutions that require reading the visitor ID. It is not used by a standard implementation. `getAnalyticsVisitorID` also works with callback functions to read Analytics IDs and bring them in to your system or application.

## Sample Code

```javascript
//callback function
var useAnalyticsVisitorID = function(id){
     //whatever your function does with the Experience Cloud ID
};

//get Analytics ID and pass it to the function
var analyticsID = visitor.getAnalyticsVisitorID(useAnalyticsVisitorID)
```

>[!NOTE]
>If you're an Analytics customer, also check for and send the Analytics ID to your function. For example, you would want both identifiers when passing the visitor ID in a hidden form element to a server-side application that uses the data insertion API. In this case, you should collect and return the Experience Cloud and Analytics visitor IDs. See [getMarketingCloudVisitorID](id-service-api-methods-getmcvid.md).

## The "aid" Parameter is a Legacy Value

The `aid` parameter appears in a query string under 2 different sets of conditions.

### Case 1
You will see the `aid` parameter in a query string when:

+ The Experience Cloud ID service is deployed correctly.
+ The user visiting a site has a pre-existing Analytics ID stored in their [s\_vi cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/?f=cookies_analytics.html).

### Case 2
You will see the `aid` parameter in a query string when your organization is using a [grace period](../../reference/reference-analytics/reference-analytics-grace.md) before fully implementing the ID service. If the user visiting your site is new, and you're not using a grace period, the visitor will get the `mid` \(Experience Cloud ID\) parameter.

For more see: [Analytics Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html)
