---
title: setting analytics and experience cloud ids
description: appendsupplementaldataidto helper method for the adobe experience cloud id service api
seo-title: setting adobe analytics and experience cloud id service ids
seo-description: appendsupplementaldataidto helper method for the adobe experience cloud id service api
short-title: setting ids
doc-type: reference
audience: admin
index: true
translate: true
version: false
private-feature-pack: false
beta: false
redirect: false
product: core services id service
cloud: experience cloud
archetype: admin
user-guide: id service admin guide
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/reference/reference-analytics/reference-analytics-ids.md
git-issue: https://git.corp.adobe.com/AdobeDocs/core-services.en/issues/new
git-repo: https://git.corp.adobe.com/adobedocs/core-services.en
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

# Setting Analytics and Experience Cloud IDs

The Experience Cloud ID service replaces the legacy Analytics visitor ID methods.

After the ID service is implemented, this code executes before `AppMeasurement`. The ID service retrieves the Experience Cloud and Analytics IDs so these values are ready when `AppMeasurement` loads.

When `AppMeasurement` loads, the Experience Cloud and Analytics IDs values are requested from the ID service and are sent to data collection with each server call. Since the ID service determines the visitor ID and simply passes it to `AppMeasurement`, the ID service must be included and implemented on each page before your `AppMeasurement` JavaScript file.

## Changes to the Analytics ID process
The primary change when migrating to the Experience Cloud ID service is that the ID cookie is set using JavaScript, instead of in the HTTP header that is returned from the data collection web server. To understand this change, the following sections describe how cookies are set using these two methods.

### HTTP Header

An HTTP response from a web server sets cookies in a browser. This is how the `s_vi` cookie is set. The `s_vi` cookie identifies Analytics visitors. After a cookie is set, it is sent with all subsequent HTTP requests to that server.

When a request is sent to the Adobe data collection server, the header is checked for the `s_vi` cookie. If this cookie is in the request, it is used to identify the visitor. If the cookie is not in the request, the server generates a unique Experience Cloud ID, sets it as a cookie in the HTTP response header, and sends it back with the request. The cookie is stored in the browser and is sent back to the data collection server during subsequent visits the site. This enables the visitor to be identified across visits.

However, some browsers, such as Apple Safari, do not accept third-party cookies. These are cookies set in the browser from domains other than the current website. Additionally, Safari blocks cookies on third-party domains if a visitor has not been to that domain before. For example, if you are on `mysite.com` and your data collection server is `mysite.omtrdc.net`, the cookie that is returned in the HTTP header from `mysite.omtrdc.net` might be rejected by the browser.

To avoid this, many customers have implemented `CNAME` records for their data collection servers. This can be an effective part of a [first-party cookie implementation strategy](https://marketing.adobe.com/resources/help/en_US/whitepapers/first_party_cookies/). If a `CNAME` record is configured to map a hostname on the customer's domain to the data collection server \(e.g., `mapping metrics.mysite.com` to `mysite.omtrdc.net`\), the Experience Cloud ID cookie is stored because the data collection domain now matches the domain of the website. This increases the likelihood that the ID service cookie will be stored. However, this does introduce some overhead because you need to configure `CNAME` records and maintain SSL certificates for the data collection servers.

### JavaScript

JavaScript can read and write cookies set in the first-party domain (the domain of the current website). The Experience Cloud ID service uses this method to set the `AMCV_###@AdobeOrg cookie` that contains all of the visitor IDs, so the domain of the tracking server no longer needs to match the domain of the website in order for the visitor ID cookie to be stored. In most circumstances this is the preferred way to set the ID service cookie because it eliminates the overhead of `CNAME` records and SSL certificates.

However, there are a few situations where setting the cookie in the HTTP header is beneficial for cross-domain tracking, which is described in Data Collection CNAMEs and Cross-Domain Tracking.

### Custom Analytics IDs
Setting a customer ID using `s.visitorID` is a method of identifying users in Analytics. However, integrations in which Analytics data is exported or imported using the ID Service will not function when a visitor is identified using `s.visitorID`.

This includes, but is not limited to, shared audiences, Analytics for Target (A4T), and Customer Attributes. For these integrations, setting a custom Analytics ID is not supported.

### Analytics Visitor ID Order
After you deploy the visitor ID service, there are five ways a visitor can be identified in Analytics (listed in the following table in order of preference):

1.

| Query Parameter     | Present When         |
| :------------------ | :------------------- |
| `vid (s.visitorID)` | `s.visitorID` is set |

2.

| Query Parameter     | Present When                                                                                                                        |
| :------------------ | :---------------------------------------------------------------------------------------------------------------------------------- |
| `aid (s_vi cookie)` | The visitor had an existing s_vi cookie before you deployed the Experience Cloud ID service, or you have a grace period configured. |

3.

| Query Parameter                                                 | Present When                                      |
| :-------------------------------------------------------------- | :------------------------------------------------ |
| `mid` (AMCV_ cookie set by Experience Cloud visitor ID service) | The visitor's browser accepts first-party cookies |

4.

| Query Parameter                                                              | Present When                                                                                                               |
| :--------------------------------------------------------------------------- | :------------------------------------------------------------------------------------------------------------------------- |
| `fid` (fallback cookie on H.25.3 or newer, or AppMeasurement for JavaScript) | A browser doesn't accept third-party cookies and the Analytics tracking server is set up as a third-party tracking server. |

>[!NOTE]
>The `fid` is a legacy identifier and is not used if you've implemented the ID service on your site. In this case, the `fid` is not needed because the first-party, `AMCV` cookie makes it obsolete. It has been retained to support legacy code and for historic reasons.

5.

| Query Parameter                            | Present When                                   |
| :----------------------------------------- | :--------------------------------------------- |
| IP Address, User Agent, Gateway IP Address | The visitor's browser does not accept cookies. |

In many scenarios you might see two or three different IDs on a call, but Analytics will use the first ID present from that list as the official Experience Cloud ID. For example, if you are setting a custom visitor ID (included in the `vid` query parameter), that ID will be used before other IDs that might be present on that same hit.

For more see: [Order of Operations for Analytics IDs](reference-analytics-order-operations.md)