---

title: API Methods - getAnalyticsVisitorID
description: getAnalyticsVisitorID method for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Methods - getAnalyticsVisitorID
SEO description: getAnalyticsVisitorID method for the Adobe Experience Cloud ID Service API
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: ID Service API
guide subtopic 1: ID Service API Methods
guide subtopic 2:

---

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

[!NOTE]Useful Tip
If you're an Analytics customer, also check for and send the Analytics ID to your function. For example, you would want both identifiers when passing the visitor ID in a hidden form element to a server-side application that uses the data insertion API. In this case, you should collect and return the Experience Cloud and Analytics visitor IDs. See [getMarketingCloudVisitorID](mcvid-getmcvid.html#).

## The "aid" Parameter is a Legacy Value

The `aid` parameter appears in a query string under 2 different sets of conditions.

## Case 1

You will see the `aid` parameter in a query string when:

+ The Experience Cloud ID service is deployed correctly.
+ The user visiting a site has a pre-existing Analytics ID stored in their [s\_vi cookie](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/?f=cookies_analytics.html).

## Case 2

You will see the `aid` parameter in a query string when your organization is using a [grace period](mcvid_grace_period.html#) before fully implementing the ID service. If the user visiting your site is new, and you're not using a grace period, the visitor will get the `mid` \(Experience Cloud ID\) parameter.


[!MORE]
[Analytics Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_analytics.html)

