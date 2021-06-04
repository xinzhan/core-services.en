---
description: Learn about how support for third-party cookies has become increasingly limited across browsers.
keywords: cookies;privacy
solution: Experience Cloud,Analytics,Target
title: How changes to third-party cookie support impacts customers 
uuid: 27332e0d-6932-4a6e-b97b-0adeced0b050
feature: Cookies
topic: Administration
role: Administrator
level: Experienced
exl-id: 3d12a1b1-c952-4b42-815d-f64b31429cec
---
# How changes to third-party cookie support impact customers{#how-changes-to-third-party-cookie-support-impacts-customers}

Support for third-party cookies has become more limited across browsers. As such, Adobe has been working on new solutions that carefully balance customer requirements with the consumer's right to privacy across Experience Cloud applications.

The following list outlines how third-party cookie support impacts current implementations of Experience Cloud applications:

## Adobe Analytics and Adobe Target

* Analytics and Target are largely unaffected since same site activity relies only on first-party cookies. Third-party cookies are required to understand user activity on across domains. For browsers where third-party cookies are blocked, cross-domain tracking is not possible using cookies.

## Adobe Experience Manager

* Because Adobe Experience Manager operates wholly within the customer's domain, there is minimal interaction with third-party cookies and thus minimal to no impact.

## Adobe Social

* Social would not be impacted as long as the customer has the newest ver­sion of the code.

## Adobe Advertising Cloud

* Search:

  * Where search is optimized based on Adobe Analytics data, search would be impacted in the same way as Adobe Analytics.
  * Collection of conversion data should be unaffected.

* Display:

  * Display remarketing today is entirely dependent upon the usage of third-party cookies.
  * Display is also heavily dependent on the availability of various advertising network cookies for synchronization.
  * Overall impact is unknown. However, per the first point, display is affected more than other services.
  * Adobe is working internally and with our advertising partners to evaluate the full extent to the impact on ad delivery.
