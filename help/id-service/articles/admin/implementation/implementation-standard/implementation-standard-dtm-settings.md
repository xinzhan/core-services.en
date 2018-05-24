---

title: ID Service Settings for DTM
description: Configuration settings for using Dynamic Tag Management to deploy the Experience Cloud ID Service
SEO title: Experience Cloud ID Service Settings for DTM
SEO description: Configuration settings for using Dynamic Tag Management to deploy the Adobe Experience Cloud ID Service
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: Implementation
guide subtopic 1: Standard Implementation
guide subtopic 2:

---

# Experience Cloud ID Service Settings for DTM

Describes the `Organization ID`, `General and Customer Settings` fields and how they're used by the Experience Cloud ID service.

## How Do I Find These Settings

The settings are available after you add and save the ID service as a tool in Dynamic Tag Management \(DTM\). You can also access these settings by clicking the gear icon from the Installed Tools section of your DTM web property.

![](media/implementation-standard-dtm-settings/installedTools.png) 

## Organization ID

This is the ID required by and associated with your provisioned Experience Cloud company. 

An organization is the entity that enables an administrator to configure users, groups, and control single sign-on access in the Experience Cloud. The Organization ID is a 24-character alphanumeric string, followed by \(and must include\) `@AdobeOrg`. 

Experience Cloud administrators can find this ID in [Experience Cloud \> Tools](https://marketing.adobe.com/resources/help/en_US/mcloud/admin_getting_started.html).

![](media/implementation-standard-dtm-settings/orgID.png) 

See also [Cookies and the Experience Cloud ID Service](mcvid_cookies.html#).

## General Settings

These settings let you specify tracking servers, code versions, and add other variables.

![](media/implementation-standard-dtm-settings/generalSettings.png) 

The following table lists and defines the General settings.

| Field                            | Description                                                                                                                                                                                                                   |
|----------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Automatically request Visitor ID | When checked, dynamic tag management to automatically calls the `getMarketingCloudVisitorID()` method before loading any of the Adobe solutions that use the Experience Cloud ID service.   See `getMarketingCloudVisitorID`. |

|Field|Description|
|-----|-----------|
|  **Automatically request Visitor ID** 

 | When checked, dynamic tag management to automatically calls the `getMarketingCloudVisitorID()` method before loading any of the Adobe solutions that use the Experience Cloud ID service.

 See [getMarketingCloudVisitorID](mcvid-getmcvid.html#).

 |
|  **Analytics Tracking Server** 

 | The name of the tracking server used for Analytics data collection. This is the domain at which the image request and cookie is written \(e.g., http://site.omtrdc.net\).

 If you don't know your tracking server URLs, check your `s_code.js` or `AppMeasurement.js` files. You'll want the URL set by the `s.trackingServer` variable.

 See [trackingServer](https://marketing.adobe.com/resources/help/en_US/sc/implement/trackingServer.html) and [Correctly Populate the trackingServer and trackingServerSecure variable](https://helpx.adobe.com/analytics/kb/determining-data-center.html#).

 |
|  **Tracking Server Secure** 

 | The name of the secure tracking server used for Analytics data collection. This is the domain at which the image request and cookie is written \(e.g., https://site.omtrdc.net\).

 If you don't know your tracking server URLs, check your `s_code.js` or `AppMeasurement.js` files. You'll want the URL set by the `s.trackingServerSecure` variable.

 See [trackingServer](https://marketing.adobe.com/resources/help/en_US/sc/implement/trackingServer.html) and [Correctly Populate the trackingServer and trackingServerSecure variable](https://helpx.adobe.com/analytics/kb/determining-data-center.html#).

 |
|  **Experience Cloud Server** 

 | If your company uses first-party data collection \(CNAME\) to utilize first-party cookies in a third-party context, enter the tracking server here \(e.g., http://metrics.company.com.\)

 |
|  **Experience Cloud Server Secure** 

 | If your company uses first-party data collection \(CNAME\) to utilize first-party cookies in a third-party context, enter the tracking server here \(e.g., https://metrics.company.com.\)

 |
|  **Library Version** 

 | Sets the version of the ID service code library \(`VisitorAPI.js`\) that you want to use. You cannot edit these menu options.

 |
|  **Settings** 

 | These fields let you add [function variables](mcvid-function-vars.html#) as key-value pairs. Click **Add** to add one or more variables to your ID service implementation.

  ![](media/implementation-standard-dtm-settings/dtmVars.png) 

[!IMPORTANT]
Set the `cookieDomain` variable here. It is required for multi-part, top-level domains where either of last 2 parts of the URL are \> two characters. See the Configuration Variables documentation linked above.
[!END]

## Customer Settings

Additional fields that let you add an integration code or authenticated state status.

 ![](media/implementation-standard-dtm-settings/customerSettings.png) 

| Field            | Description                                                                                                                                                                                                                               |
| :--------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Integration Code | An integration code is a unique, customer provided ID. The integration code should contain the value you used to [create a data source in Audience Manager](https://marketing.adobe.com/resources/help/en_US/aam/create-datasource.html). |
| Value            | The value should be a data element containing the user id. Data elements are suitable containers for dynamic values like IDs from a client-specific internal system.                                                                      |
| Auth State       | Options that define or identify visitors according to their authentication status (e.g., logged in, logged out). See [Customer IDs and Authentication States](../../faq/faq-authenticated.md).                                            |
