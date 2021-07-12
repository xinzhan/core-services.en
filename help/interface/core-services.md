---
description: Modernize your Adobe Analytics and Adobe Target solutions for cross-solution services. Learn how to start using Experience Cloud services.
keywords: core services;Customer Attributes
solution: Experience Cloud
title: Enable your solutions for cross-solution services
index: yes
feature: Customer Attributes
topic: Administration
role: Admin
level: Experienced
exl-id: 48e79e23-b339-4143-b3b1-969c370efeff
---
# Enable your implementation for Experience Cloud services

If you recently implemented Experience Cloud using Experience Platform Launch, you're already set up for Customer Attributes and Experience Cloud Audiences. You can also manage users and products in the Admin Console.

Existing customers can modernize their solution implementations and implement Experience Cloud. Doing so enables you to use Customer Attributes and audience features across Adobe Analytics, Audience Manager, and Adobe Target. To accomplish this implementation, you will:

1. [Join the Experience Cloud and become an administrator](#section_2423F0BD3DF642658103310EE5EA6154)
1. [Implement the Experience Cloud ID Service](#section_3C9F6DF37C654D939625BB4D485E4354)
1. [Map report suites to an Experience Cloud organization](#section_7B08516B01BA421681DF03D0E86CE3BA)
1. [Update your Analytics AppMeasurement code](#section_1798D9D0F05C47E29816AC4EEB9A0913)
1. [Update your Adobe Target implementation](#section_C2F4493C7A36406DAE2266B429A4BD24)
1. [Verify the implementation](#section_E641782A0F4F44AF8C9C91216BE330D5)
1. [Manage users and products](#section_B6E95F4E0E12483CB9DA99CBC0C5A4AF)
1. [Begin sharing attribute and audience data](#section_960C06093623462E8EA247B3E97274A1)

## Join the Experience Cloud and become an administrator {#section_2423F0BD3DF642658103310EE5EA6154}

What you must do to join the Experience Cloud: 

1. Ensure that you have the appropriate Adobe Analytics or Adobe Target SKUs. 

    * **Adobe Analytics:** Standard or Premium (not the legacy [!DNL SiteCatalyst] SKU).
    * **Adobe Target:** Standard or Premium.

    >[!NOTE]
    >
    >For [!DNL Target], migrate to at.js from [!DNL mbox.js]. See [Upgrading from at.js 1. x to at.js 2. x](https://experienceleague.adobe.com/docs/target/using/implement-target/client-side/at-js-implementation/upgrading-from-atjs-1x-to-atjs-20.html?lang=en).

1. Modernize your implementation and get provisioned an administrator. 

    * Follow the steps below in [Implement the [!UICONTROL Experience Cloud ID Service]](core-services.md#section_3C9F6DF37C654D939625BB4D485E4354).
    * Contact your Account Manager and start the provisioning process for the Experience Cloud.

1. Manage users and products in the [!UICONTROL Admin Console]. 

### Administrator login

After you are an administrator, you can log in at [experience.adobe.com](https://experience.adobe.com).

The **[!UICONTROL Admin Console]** link is available in Experience Cloud menu navigation.

See [Experience Cloud user and product administration](admin-getting-started.md#topic_3FCB4099640647E3B2411ADBFCE81909) for more information.

### User login

To log in to the Experience Cloud, your users must:

* Have an Adobe ID (or Enterprise ID for your company).
* Sign in at [experience.adobe.com](https://experience.adobe.com).
* Belong to a solution group that is mapped to an enterprise group.
* If necessary, link their solution accounts to their Adobe ID (described below).

### Optional: Link existing user accounts. 

Most likely, you have users who are already members of solution groups, such an Analytics group that you previously managed in [!UICONTROL Analytics] > [!UICONTROL Admin Tools].

When you map these groups to Experience Cloud enterprise groups, those users must manually link their solution account credentials to their Adobe ID.

See [Link accounts in the Experience Cloud](organizations.md#topic_C31CB834F109465A82ED57FF0563B3F1)

>[!NOTE]
>
>After enterprise and solution groups are mapped, new users are automatically linked. (Solution credentials are automatically created and linked to their Adobe ID.) 

The following sections describe how to modernize your implementation. Modernizing your implementation enables core services in the Experience Cloud. 

## Implement the [!UICONTROL Experience Cloud ID Service] {#section_3C9F6DF37C654D939625BB4D485E4354}

The [!UICONTROL Experience Cloud ID Service] provides a common ID for cross-solution integration. It provides cross-domain visitor identification and a path for cross-device/browser targeting and personalization based on CRM data uploaded via [!UICONTROL Customer Attributes].

The simplest method for enabling Experience Cloud core services is to activate it automatically for Analytics and Adobe Target via the [Experience Cloud ID Service extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html?lang=en#extensions-ref) in [!UICONTROL Experience Platform Launch].  

For complete Experience Cloud ID Service help (formerly, visitor ID), go [here](https://experienceleague.adobe.com/docs/id-service/using/intro/overview.html?lang=en#intro).

**Not Using [!UICONTROL Experience Platform Launch] or [!UICONTROL Dynamic Tag Management]?**

If you are not using [!UICONTROL Experience Platform Launch] or [!UICONTROL Dynamic Tag Management], manually implement the ID service via the JavaScript Deployment ([!DNL VisitorAPI.js]), as follows:

| Task    | Description  |
| -----------| ---------- |  
| [Implement the Experience Cloud ID Service for Analytics](https://experienceleague.adobe.com/docs/id-service/using/implementation/setup-analytics.html?lang=en)  | Adobe also recommends setting additional [customer IDs](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=en). These IDs are associated with each visitor and enable current and future functionality in Experience Cloud. |  
| Update your existing [!DNL s_code] to version H.27.3 or later, or your existing [!DNL AppMeasurement.js] to version 1.4 or later.  | These files are available for download in the [Code Manager](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=en) in Analytics Admin Tools. (The [JavaScript Implementation](https://experienceleague.adobe.com/docs/analytics/implementation/js/overview.html?lang=en#js) guide is available if you need more information about [!DNL AppMeasurement.js].) |
| Synchronize the customer ID for Analytics  | See [Analytics - synching the customer ID](core-services.md#section_AD473A6A21C1446498E700363F9A8437) (below). |

{style="table-layout:auto"}

### Analytics & Adobe Target - synching the customer ID {#section_AD473A6A21C1446498E700363F9A8437}

As a part of setting up the Experience Cloud ID Service, Adobe recommends for Analytics and [!DNL Target] that you synchronize your [customer IDs](https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=en) with the Experience Cloud. 

In Adobe Target, the `mbox3rdpartyid` must get the customer ID and send it to [!DNL Target]. (See [Working with Customer Attributes](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/working-with-customer-attributes.html?lang=en) in [!DNL Target].) 

When a visitor authenticates on your website, or otherwise identifies themselves, your implementation must expose that person's CRM customer ID to the page or app. Then you can use the appropriate function call to synchronize your customer ID to the Experience Cloud. This synchronization stores the visitor's CRM customer ID in the Experience Cloud, and activates that customer's attributes for use in the Experience Cloud. 

For example, assume that Bob has Customer ID `52mc210tr42` in your CRM system. When Bob authenticates on your site, you must expose this ID on the page, and use the ID to synchronize it by one of two means: 

* Call `visitor.setCustomerIDs({"crm_id":"52mc210tr42"})` using the Visitor ID service. Or, 
* Populate the *`Customer ID (52mc210tr42)`* in a prop or eVar.

The Customer ID must be set on each [!DNL Analytics] server call where the Customer ID is known. 

### Mobile SDKs

See the *Experience Cloud ID Service* section for syntax examples about how to set additional customer IDs in [Android™](https://experienceleague.adobe.com/docs/mobile-services/android/overview.html?lang=en) and [iOS](https://experienceleague.adobe.com/docs/mobile-services/ios/overview.html?lang=en) Mobile applications.

### Enabling Attributes for Historical Data

Customer attribute data is made available after visitors log in. If you have not yet implemented the ID Service, and if you have historically been tracking customer IDs in a prop or eVar, you can request a process that sends historical logins to Experience Cloud. This process lets you begin using Customer Attributes immediately.

Contact Customer Care to enable historical data.

## Map report suites to an Experience Cloud Organization {#section_7B08516B01BA421681DF03D0E86CE3BA}

>[!NOTE]
>
>Report Suite Mapping functionality was deprecated in November 2020. Reach out to Customer Support with any questions.

Experience Cloud services (such as Experience Cloud ID Service and the [!UICONTROL People service]) are associated with an Experience Cloud organization instead of an individual Analytics report suite. To ensure that these services operate correctly, each Analytics report suite must be mapped to an Experience Cloud organization. 

## Update your Analytics AppMeasurement code {#section_1798D9D0F05C47E29816AC4EEB9A0913}

If you're using Analytics, verify that you are on regional data collection (RDC). If your data collection domain is `omtrdc.net`, or if your CNAME is mapped to `omtrdc.net`, you are on RDC. See [Transitioning to RDC](https://experienceleague.adobe.com/docs/analytics/technotes/rdc/regional-data-collection.html?lang=en) for more information. If you are using first-party cookies, refer to [CNAME and the Experience Cloud ID Service](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/cname.html?lang=en) for information about data collection CNAMEs and cross-domain tracking. 

It is recommended that you modernize your Analytics implementation by updating your JavaScript libraries, including the Visitor API. The simple way to accomplish is to add an [Adobe Analytics extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/analytics-extension/overview.html?lang=en) in Experience Platform Data Collection (Launch).

## Update your Adobe Target implementation {#section_C2F4493C7A36406DAE2266B429A4BD24}

* It is recommended that you add an [Adobe Target extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/targetv2-extension/adobe-target-extension-v2.html?lang=en) in [!UICONTROL Experience Platform Launch], so that your library retrieval is automatic. You can also set up the [Experience Cloud ID Service extension](https://experienceleague.adobe.com/docs/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html?lang=en) for Adobe Target (and other solutions) using [!UICONTROL Experience Platform Launch]. The [!UICONTROL Experience Cloud ID Service] update **is required** for Adobe Target to use core services.
* If you are not using [!UICONTROL Experience Platform Launch], [update your mbox library](https://experienceleague.adobe.com/docs/target/using/implement-target/client-side/mbox-implement/target-download-config-mbox.html?lang=en) manually.
* Request access to use Adobe Analytics as the reporting source for [!DNL Adobe Target]. [!DNL Target] and [!DNL Analytics] data are combined on the same server call during processing so that visitors are connected between the two solutions. See [Analytics for Target Implementation](https://experienceleague.adobe.com/docs/target/using/integrate/a4t/a4t.html?lang=en).
 
  >[!IMPORTANT]
  >
  >All Analytics customers are already provisioned for core services like Customer Attributes. If you are not an Analytics customer, contact Customer Care to request to be provisioned.

## Verify the implementation {#section_E641782A0F4F44AF8C9C91216BE330D5}

Use the following process to ensure Experience Cloud ID Service is implemented correctly on your site.

1. Clear cookies for your site so you can see the request to the Experience Cloud ID Service (the request happens on the first visit, then once per visitor per week).
1. Using a packet analyzer or the network panel in a web browser debugger, look for a request going to [!DNL dpm.demdex.net].
1. Verify that the response contains `d_mid` and a value, for example: `_setMarketingCloudFields({"d_mid":"4235...`
1. Verify that the Analytics request contains the `mid` parameter (the Experience Cloud ID). During the grace period (if it is enabled), you should also see an `aid` parameter (the Analytics visitor ID).

Expected response containing the Experience Cloud ID:

![](assets/mac_id_response.png)

Analytics image request containing the Experience Cloud ID (also known as `mid` or _visitor ID_):

![](assets/mid.png)

Experience Cloud ID in the mbox request:

![](assets/mbox_request.png)

### What Is the Grace Period?

After you deploy the Experience Cloud ID Service, new visitors no longer receive an Analytics Experience Cloud ID from your data collection server. If sections of your site have not yet implemented the ID Service, when visitors browse to these sections, the Experience Cloud ID is not recognized and visitors are assigned a legacy Analytics visitor ID. This can cause potential problems, including duplicate visits and incorrect attribution.

For example, if the support section of your site is managed in a separate CMS, you might have a different Analytics JavaScript file for this section. If you deploy the Experience Cloud ID on your main site before you deploy the ID service to the support site, new visitors receive a legacy Analytics ID when they visit the support section. Visits that span both site sections are reported as different visits.

Deploying the Experience Cloud ID Service on sites that are using multiple JavaScript files or other technologies (such as Flash) can cause coordination issues. These issues occur because you must enable the Experience Cloud ID Service on all portions of your site at the same time. By configuring a grace period, new visitors to continue to receive an Analytics visitor ID from the ID service. Visitors can be consistently identified on sections of your site that have not been upgraded to use the visitor ID service. 

## Manage users and products {#section_B6E95F4E0E12483CB9DA99CBC0C5A4AF}

Once you are up and running, navigate to the [Admin Console](https://adminconsole.adobe.com/), where you can manage users and product profiles. 

![](assets/menu-administration-shell.png) 

See [Experience Cloud user and product management](admin-getting-started.md#topic_3FCB4099640647E3B2411ADBFCE81909). 

### Customer Attributes

Users that are added to the [!UICONTROL Customer Attributes] group can see the [!UICONTROL Customer Attributes] menu item on the left side of Experience Cloud.

## Begin sharing attribute and audience data {#section_960C06093623462E8EA247B3E97274A1}

Take advantage of the following features. 

### [!UICONTROL People] > [!UICONTROL Customer Attributes]

If you capture enterprise customer data in a customer relationship management (CRM) database, you can upload the data into a Customer Attribute data source in the Experience Cloud. Once uploaded, use the data in [!DNL Adobe Analytics] and [!DNL Adobe Target].

See [Customer Attributes](attributes.md#concept_ACFEE7C8B8E94875BA0825CDF4913AF1) 

### [!UICONTROL People] > [!UICONTROL Audience Library] 

Experience Cloud [!UICONTROL Audiences] is the interface that lets you create audiences, combine existing audiences to create composite audiences, and view all shared audiences. 

See [Audiences](audience-library.md#topic_679810123CAA4E0CA4FA3417FB0100C7) 

## Data storage and privacy disclosure 

If you use real-time audience profiling and other core services within the Adobe [!DNL Experience Cloud], use of these services might impact which data center (and country) your data resides. Specifically, because [!DNL Experience Cloud] uses Audience Manager, data used within the [!UICONTROL People] service must reside within Audience Manager servers in the United States. 

When using services made available via the [!UICONTROL People] service, the types of data sent from other Adobe products to audience management are: 

* [!DNL Analytics] key/value pairs (props, eVars, list vars, and so on). By default, the log lines include IP address, including the last octet of the IP (assuming that the IP address was not modified by IP obfuscation settings within Adobe [!DNL Analytics]).
* Traits and segments that visitors qualify for based on rules set up in Audience Manager.
* (Optional) One or more of your IDs. Depending on your implementation of the ID service, you might also be sending in one or more of your IDs, such as CRM IDs or hashed email addresses. If this data is sent into Adobe [!DNL Analytics], it is transferred to Adobe audience management. Adobe recommends against providing personal data to Adobe [!DNL Analytics]. Rather, use a one-way hash to mask the data before it is sent to Adobe.
* Segments originating in [!DNL Analytics] via the back-end segment sharing capability
* The demdex.net cookie is set if third-party cookies are not blocked. The `AMCV_###@AdobeOrg` first-party cookie is always set with the Experience Cloud ID Service.

All these data elements are delivered to Adobe Audience Manager in the form of log files. Audience Manager processes and stores this data within the United States. Audience Manager does not provide an option to store or process this data outside of the United States.

### Cookies and Opt-Outs 

Use of real-time audience profiling uses the Audience Manager cookie, in addition to the cookies used for [!DNL Analytics] and [!DNL Target]. 

If you want to provide the proper opt-out ability, visitors to your site must add the Audience Manager opt-out to your existing opt-out process. 

See [Adobe Experience Cloud - Implementing Adobe Opt-Outs](https://experienceleague.adobe.com/docs/analytics/implementation/js/opt-out.html) for instructions. 

See [Data Collection CNAMEs and Cross-Domain Tracking](https://experienceleague.adobe.com/docs/id-service/using/reference/analytics-reference/cname.html?lang=en) for enabling cross-domain tracking.
