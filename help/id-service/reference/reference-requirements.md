---

title: Requirements for the Experience Cloud ID Service
description: Review this section to make sure you're using the right solutions, services, and code versions required by the Experience Cloud ID service
seo-title: Requirements for the Experience Cloud ID Service
seo-description: Review this section to make sure you're using the right solutions, services, and code versions required by the Experience Cloud ID service
short-title: Requirements
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

# Requirements for the Experience Cloud ID Service

Review this section to make sure you're using the right solutions, services, and code versions required by the Experience Cloud ID service.

## Requirements Ensure Implementation Success and Support

A successful, supported implementation meets (or exceeds) the code requirements and follows the instructions as they appear in the Adobe help. An unsupported implementation will yield unexpected results and prevent Customer Care and our engineering teams from assisting with efforts to troubleshoot or resolve your issues with the ID service.

| Implementation Type | Description                                                                                                                                                                                                                                                                                                                          |
| :------------------ | :----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Standard**        | For a standard implementation with Dynamic Tag Management (DTM), you must: <br><ul><li>Place the embed head code in the `<head>` section of your page.</li><li>Place the embed footer code before the closing `</body>` tag.</li></ul>                                                                                               |
| **Non Standard**    | For non-standard, or manual implementations, you must set up the ID service as described by the procedures this guide. As with the DTM guidelines above, improper code placement and loading will create an unsupported implementation.                                                                                              |
| **Not Supported**   | A standard implementation is not supported when you: <br><ul><li>Place either of these DTM embed codes elsewhere in your markup and/or page code.</li><li>Append, add, or load DTM code with asynchronous methods, calls/callback methods, or wrappers.</li><li>Include multiple instances of embed code on the same page.</li></ul> |

## Experience Cloud Requirements: Organization ID

To use the ID service, your company must be enabled for the Experience Cloud and have an Organization ID. Check the following list if you're unsure of your company's Experience Cloud status and need to find your Organization ID.

>[!IMPORTANT]
>
>The Organization ID is case sensitive and must be used exactly as provided.

| Experience Cloud Status | Description                                                                                                                                                                                                                                                                                                                                                                 |
| :---------------------- | :-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| **Enabled**             | If your company is enabled for the Experience Cloud but you do not have your Organization ID, see the "Administration Page" section in Experience Cloud Administration.                                                                                                                                                                                                     |
| **Not Sure**            | If you don't know your company's Experience Cloud status, ask whoever manages your Adobe account if members of your company can log in at marketing.adobe.com using an Adobe ID. If you can, then you're enabled and an administrator can view your Organization ID. To find the Organization ID, see the "Administration Page" section in Experience Cloud Administration. |
| **Not Enabled**         | If your company is not enabled for Experience Cloud, see Core Services - Enabling Your Solutions to get started.                                                                                                                                                                                                                                                            |

## Analytics Requirements: Regional Data Collection (RDC)

Analytics customers must be using RDC to implement the ID service. RDC improves Analytics data collection processes and ensures that you're ready for integrations with other Experience Cloud solutions. Review the Experience Cloud ID Service Migration Decision Points before getting started.

## Code Libraries and Version Requirements

The following sections list the minimum code versions that are required to use the Experience Cloud ID service.

>[!NOTE] We recommend that you use the latest code versions rather than the required minimums.


| Solution                    | Code Library        | Version Req     | Notes                                                                                                                                                                 |
| :-------------------------- | :------------------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Experience Cloud ID Service | `VisitorAPI.js`     | 2.0 or higher   |                                                                                                                                                                       |
| Analytics                   | `AppMeasurement.js` | 1.6.4 or higher | See [AppMeasurement for JavaScript](https://marketing.adobe.com/resources/help/en_US/sc/implement/?f=appmeasure_mjs.html)                                             |
| Analytics                   | `s_code.js`         | H.27            | Analytics `s_code` version H.27 is no longer supported with the release of the ID service version 1.6.0. Upgrade your code to the latest version of `AppMeasurement`. |
| Analytics                   | Video Heartbeat     | 2.0             | See [Video Heartbeat 2.x for JavaScript](https://marketing.adobe.com/resources/help/en_US/sc/appmeasurement/hbvideo/js_2.0/).                                         |
| Audience Manager            | `dil.js`            | 5.0             | See [DIL - Data Integration Library](https://marketing.adobe.com/resources/help/en_US/aam/?f=c_dil.html)                                                              |
| Target                      | `mbox.js`           | 61              | See [mbox code](https://marketing.adobe.com/resources/help/en_US/target/ov/?f=c_mbox_technical.html)                                                                  |
| Target                      | `at.js`             | 0.9.1           | See [at.js implementation](https://marketing.adobe.com/resources/help/en_US/target/ov2/c_target-atjs-implementation.html)                                             |

## SDK Requirements for Android and iOS

At a minimum, the ID service requires the SDK versions listed below.

+ Android: 4.11.0
+ iOS: 4.11.0

>[!NOTE]
>
>We recommend that you use the latest code versions rather than the required minimums.

Your SDK code must be enabled for the ID service. Enable and download the latest SDK code for each app from your Adobe Mobile Services account. 

More information

+ [Configure SDK Visitor ID Service Options](https://marketing.adobe.com/resources/help/en_US/mobile/t_config_visitor.html)
+ [Android SDK methods](https://marketing.adobe.com/resources/help/en_US/mobile/android/c_marketing_cloud.html)
+ [iOS SKD methods](https://marketing.adobe.com/resources/help/en_US/mobile/ios/marketing_cloud.html)