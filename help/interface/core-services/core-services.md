---
description: Implement the Experience Cloud and become an administrator. This process modernizes your solutions for core service features like customer attributes and audiences.
keywords: core services;customer attributes
seo-description: Implement the Experience Cloud and become an administrator. This process modernizes your solutions for core service features like customer attributes and audiences.
seo-title: Enable your Experience Cloud solutions for core services
solution: Experience Cloud
title: Enable your solutions for core services
uuid: 5820060f-9b18-4339-81e0-401d964f7a03
---

# Enable your solutions for core services

For existing customers, learn how to modernize your solution implementations and implement the Experience Cloud so that you can use features like customer attributes and audiences.

<!-- <p>https://marketing-beta.adobe.com/resources/help/core/core-services.html </p> 
<p>https://adobe.sharepoint.com/sites/AGSConsulting/CoreServices/PA/_layouts/15/start.aspx#/ </p> -->

<!-- Core services architecture and data flow wiki: https://wiki.corp.adobe.com/pages/viewpage.action?pageId=1004285689 -->

## Step 1. Join the Experience Cloud and become an administrator {#section_2423F0BD3DF642658103310EE5EA6154}

What you need to do to join the Experience Cloud: 

![](assets/step1_icon.png) Ensure that you have the appropriate Adobe Analytics or Adobe Target SKUs. 

* **Adobe Analytics:** Standard or Premium (not the legacy SiteCatalyst SKU).
* **Adobe Target:** Standard or Premium.

>[!NOTE]
>
>For Target, migrate to at.js from mbox.js. See [Upgrading from at.js 1. x to at.js 2. x](https://docs.adobe.com/content/help/en/target/using/implement-target/client-side/upgrading-from-atjs-1x-to-atjs-20.html). 

![](assets/step2_icon.png) Modernize your implementation and get provisioned an administrator. 


1. Follow the steps below in [Deploy the Experience Cloud ID Service](../core-services/core-services.md#section_3C9F6DF37C654D939625BB4D485E4354).
1. Contact your Account Manager and start the provisioning process for the Experience Cloud.

![](assets/step3_icon.png) Manage users and products in the [!UICONTROL Admin Console]. 

**Administrator Access** 

After you are an administrator, you can log in at [experiencecloud.adobe.com](https://experiencecloud.adobe.com). 

You will see the **[!UICONTROL Administration]** link in the Experience Cloud menu navigation. 

See [Experience Cloud user and product administration](../admin-getting-started/admin-getting-started.md#topic_3FCB4099640647E3B2411ADBFCE81909) for help. 

**User Access** 

To log in to the Experience Cloud, your users must: 


1. Have an Adobe ID.
1. Sign in at [experiencecloud.adobe.com](https://experiencecloud.adobe.com).
1. Belong to a solution group that is mapped to an enterprise group.
1. If necessary, link their solution accounts to their Adobe ID (described below).

![](assets/step4_icon.png) Optional: Link existing user accounts. 

Most likely, you have users who are already members of solution groups, such an Analytics group that you previously managed in [!UICONTROL Analytics] > [!UICONTROL Admin Tools]. 

When you map these groups to Experience Cloud enterprise groups, those users must manually link their solution account credentials to their Adobe ID. 

See [Link accounts in the Experience Cloud](../admin-getting-started/organizations.md#topic_C31CB834F109465A82ED57FF0563B3F1) 

> [!NOTE]
> 
> After enterprise and solution groups are mapped, new users are automatically linked. (Solution credentials are automatically created and linked to their Adobe ID.) 

The following sections describe how to modernize your implementation. Modernizing your implementation enables core services in the Experience Cloud. 

## Step 2. Implement the [!UICONTROL Experience Cloud ID service] using [!UICONTROL Experience Platform Launch], or [!UICONTROL Dynamic Tag Management] {#section_3C9F6DF37C654D939625BB4D485E4354}

The [!UICONTROL Experience Cloud ID service] provides a common ID for cross-solution integration. It provides cross-domain visitor identification and a path for cross-device/browser targeting and personalization based on CRM data uploaded via [!UICONTROL Customer Attributes].

The simplest method for enabling Experience Cloud core services is to activate it automatically for Analytics and Target via the [Experience Cloud ID service tool](https://docs.adobe.com/content/help/en/launch/using/implement/solutions/idservice-save.html) in [!UICONTROL Experience Platform Launch], or [!UICONTROL Dynamic Tag Management]. (Experience Platform Launch is strongly recommended.) 

![](assets/menu-activation-shell.png) 

For complete Experience Cloud ID service help (formerly, visitor ID), go [here](https://docs.adobe.com/content/help/en/id-service/using/home.html). 

**Not Using [!UICONTROL Experience Platform Launch] or [!UICONTROL Dynamic Tag Management]?** 

If you are not using [!UICONTROL Experience Platform Launch] or [!UICONTROL Dynamic Tag Management], manually implement the ID service via the JavaScript Deployment ([!DNL VisitorAPI.js]), as follows: 

1. [Implement the Experience Cloud ID Service for Analytics](https://docs.adobe.com/content/help/en/id-service/using/implementation/setup-analytics.html).

   Adobe also recommends setting additional [customer IDs](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html). These IDs are associated with each visitor and enable current and future functionality in Experience Cloud. 

1. Update your existing [!DNL s_code] to version H.27.3 or later, or your existing [!DNL AppMeasurement.js] to version 1.4 or later. 

   These files are available for download in the [Code Manager](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/code-manager-admin.html) in Analytics Admin Tools. 

   (The [JavaScript Implementation](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/javascript-implementation-overview.html) guide is available if you need more information about [!DNL AppMeasurement.js].) 

1. Synchronize the customer ID for Analytics. See [Analytics - synching the customer ID](../core-services/core-services.md#section_AD473A6A21C1446498E700363F9A8437) (below). 

## Analytics & Target - synching the customer ID {#section_AD473A6A21C1446498E700363F9A8437}

As a part of setting up the Experience Cloud ID service, Adobe recommends for Analytics and [!DNL Target] that you synchronize your [customer IDs](https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html) with the Experience Cloud. 

In Adobe Target, the `mbox3rdpartyid` needs to get the customer ID and send it to [!DNL Target]. (See [Working with Customer Attributes](https://docs.adobe.com/content/help/en/target/using/audiences/visitor-profiles/working-with-customer-attributes.html) in [!DNL Target].) 

When a visitor authenticates on your website, or otherwise identifies himself, your implementation must expose that person's CRM customer ID to the page or app. Then you can use the appropriate function call to synchronize your customer ID to the Experience Cloud. This synchronization stores the visitor's CRM customer ID in the Experience Cloud, and activates that customer's attributes for use in the Experience Cloud. 

For example, assume that Bob has Customer ID `52mc210tr42` in your CRM system. When Bob authenticates on your site, you must expose this ID on the page, and use the ID to synchronize it by one of two means: 

* Call `visitor.setCustomerIDs({"crm_id":"52mc210tr42"})` using the Visitor ID service. Or, 
* Populate the *`Customer ID (52mc210tr42)`* in a prop or eVar.

The Customer ID must be set on each [!DNL Analytics] server call where the Customer ID is known. 

### Mobile SDKs 

See the *Experience Cloud ID service* section for syntax examples about how to set additional customer IDs in [Android](https://docs.adobe.com/content/help/en/mobile-services/android/overview.html) and [iOS](https://docs.adobe.com/content/help/en/mobile-services/ios/overview.html) Mobile applications. 

### Enabling Attributes for Historical Data

Customer attribute data is made available after visitors log in. If you have not yet implemented the latest Experience Cloud ID service, and if you have historically been tracking customer IDs in a prop or eVar, you can request a process that sends historical logins to the Experience Cloud. This process lets you begin using customer attributes immediately. 

Contact Customer Care to enable historical data. 

## Step 3. Map Report Suites to an Experience Cloud Organization {#section_7B08516B01BA421681DF03D0E86CE3BA}

Experience Cloud services (such as Experience Cloud ID service and the [!UICONTROL People service]) are associated with an Experience Cloud organization instead of an individual report suite. To ensure that these services operate correctly, each Analytics report suite must be mapped to an Experience Cloud organization. 

See [Map report suites to an organization](report-suite-mapping.md). 

## Step 4. (Adobe Analytics) Modernize your Analytics AppMeasurement code {#section_1798D9D0F05C47E29816AC4EEB9A0913}

Verify that you are on regional data collection (RDC). If your data collection domain is [!DNL omtrdc.net], or if your CNAME is mapped to [!DNL omtrdc.net], you are on RDC. See [Transitioning to RDC](https://docs.adobe.com/content/help/en/analytics/technotes/rdc/regional-data-collection.html) for more information. If you are using first-party cookies, refer to [CNAME and the Experience Cloud ID Service](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/cname.html) for information about data collection CNAMEs and cross-domain tracking. 

It is recommended that you modernize your Analytics implementation by updating your JavaScript libraries, including the Visitor API. The simple way to accomplish this is to add an [!DNL Adobe Analytics] tool in Dynamic Tag Management, specifying *`Automatic`* as the configuration method.

In [!UICONTROL Dynamic Tag Management], click **[!UICONTROL <Web Property Name>]** > **[!UICONTROL Overview]** > **[!UICONTROL Add a Tool]** > **[!UICONTROL Adobe Analytics]**. See [Adobe Analytics Settings](https://docs.adobe.com/content/help/en/dtm/using/tools/analytics-dtm.html) in Dynamic Tag Management for deployment information. 

## Step 5. (Adobe Target) Modernize your Adobe Target implementation {#section_C2F4493C7A36406DAE2266B429A4BD24}

* It is recommended that you add an [Adobe Target extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/targetv2-extension/adobe-target-extension-v2.html) in [!UICONTROL Experience Platform Launch], so that your library retrieval is automatic. You can also set up the [Experience Cloud ID service extension](https://docs.adobe.com/content/help/en/launch/using/extensions-ref/adobe-extension/id-service-extension/overview.html) for Target (and other solutinos) using [!UICONTROL Experience Platform Launch]. The [!UICONTROL Experience Cloud ID service] update **is required** for [!UICONTROL Target] to use core services. (If you use [!UICONTROL Dynamic Tag Management], add an [Adobe Target tool](https://docs.adobe.com/content/help/en/dtm/using/tools/target.html). You can also use [!UICONTROL Dynamic Tag Management] to deploy the Experience Cloud ID service for Target.)
* If you are not using [!UICONTROL Experience Platform Launch] or [!UICONTROL Dynamic Tag Management], [update your mbox library](https://docs.adobe.com/content/help/en/target/using/implement-target/client-side/mbox-implement/target-download-config-mbox.html) manually.
* Request access to use Adobe Analytics as the reporting source for [!DNL Adobe Target]. [!DNL Target] and [!DNL Analytics] data are combined on the same server call during processing so that visitors are connected between the two solutions. See [Analytics for Target Implementation](https://docs.adobe.com/content/help/en/target/using/integrate/a4t/a4t.html).
* 
  >[!IMPORTANT]
  >
  >All Analytics customers are already provisioned for core services like customer attributes. If you are not an Analytics customer, contact Customer Care to request to be provisioned.

## Step 6. Verify the core services implementation {#section_E641782A0F4F44AF8C9C91216BE330D5}

Use the following process to ensure the Experience Cloud ID service is implemented correctly on your site. 

1. Clear cookies for your site so you can see the request to the Experience Cloud ID service (the request happens on the first visit, then approximately once per visitor per week).
1. Using a packet analyzer or the network panel in a web browser debugger, look for a request going to [!DNL dpm.demdex.net].
1. Verify that the response contains `d_mid` and a value, for example: `_setMarketingCloudFields({"d_mid":"4235...`
1. Verify that the Analytics request contains the `mid` parameter (the Experience Cloud ID). During the grace period (if it is enabled), you should also see an `aid` parameter (the Analytics visitor ID).

Expected response containing the Experience Cloud ID:

![](assets/mac_id_response.png)

Analytics image request containing the Experience Cloud ID (also known as `mid` or _visitor ID_):

![](assets/mid.png)

Experience Cloud ID in the mbox request:

![](assets/mbox_request.png)

**What Is the Grace Period?**

After you deploy the Experience Cloud ID service, new visitors no longer receive an Analytics Experience Cloud ID from your data collection server. If sections of your site have not yet implemented the Experience Cloud ID service, when visitors browse to these sections, the Experience Cloud ID is not recognized and visitors are assigned a legacy Analytics visitor ID. This can cause potential problems, including duplicate visits and incorrect attribution. 

For example, if the support section of your site is managed in a separate CMS, you might have a different Analytics JavaScript file for this section. If you deploy the Experience Cloud ID on your main site before you deploy the ID service to the support site, new visitors receive a legacy Analytics ID when they visit the support section, and visits that span both site sections are reported as different visits. 

Deploying the Experience Cloud ID service on sites that are using multiple JavaScript files or other technologies (such as Flash) can cause coordination issues because you need to enable the Experience Cloud ID service on all portions of your site at the same time. By configuring a grace period, new visitors to continue to receive an Analytics visitor ID from the ID service, so visitors can be consistently identified on sections of your site that have not been upgraded to use the visitor ID service. 

## Step 7. Manage users and products {#section_B6E95F4E0E12483CB9DA99CBC0C5A4AF}

Once you are up and running, navigate to the [Admin Console](https://adminconsole.adobe.com/), where you can manage users and product profiles. 

![](assets/menu-administration-shell.png) 

See [Experience Cloud user and product management](../admin-getting-started/admin-getting-started.md#topic_3FCB4099640647E3B2411ADBFCE81909). 

**Customer Attributes** 

<!-- <p> 
 <note type="important">
  To use the Customer Attributes feature, users must belong to the 
  <span class="term"> Adobe Customer Attributes</span> group, and to solution-level groups (Analytics or Target). 
 </note> </p> 
 -->
 
Users that are added to the [!UICONTROL Customer Attributes] group will see the [!UICONTROL Customer Attributes] menu item on the left side of the Experience Cloud interface 

## Step 8. Start using core services {#section_960C06093623462E8EA247B3E97274A1}

Take advantage of the following core service features. 

![](assets/menu-audiences-shell.png) 

**[!UICONTROL People] > [!UICONTROlCustomer Attributes]** 

If you capture enterprise customer data in a customer relationship management (CRM) database, you can upload the data into a customer attribute data source in the Experience Cloud. Once uploaded, leverage the data in [!DNL Adobe Analytics] and [!DNL Adobe Target]. 

See [Customer Attributes](../attributes/attributes.md#concept_ACFEE7C8B8E94875BA0825CDF4913AF1) 

**[!UICONTROL People] > [!UICONTROL Audience Library]** 

Experience Cloud [!UICONTROL Audiences] is the interface that lets you create audiences, combine existing audiences to create composite audiences, and view all shared audiences. 

See [Audiences](../audience-library/audience-library.md#topic_679810123CAA4E0CA4FA3417FB0100C7) 

<!-- aam_mc.xml -->

## Data storage and privacy disclosure 

If you leverage real-time audience profiling and other core services within the Adobe [!DNL Experience Cloud], use of these services might impact which data center (and country) your data resides. Specifically, because the core services of the Adobe [!DNL Experience Cloud] leverage Adobe Audience Manager, data used within the [!UICONTROL People] service must reside within Audience Manager servers in the United States. 

When leveraging core services made available via the [!UICONTROL People] service, the types of data sent from other Adobe products to audience management are: 

* [!DNL Analytics] key/value pairs (props, eVars, list vars, and so on). By default, the log lines include IP address, including the last octet of the IP (assuming that the IP address was not modified by IP obfuscation settings within Adobe [!DNL Analytics]).
* Traits and segments that visitors qualify for based on rules set up in Audience Manager.
* (Optional) One or more of your IDs. Depending on your implementation of the ID service, you might also be sending in one or more of your IDs, such as CRM IDs or hashed email addresses. If this data is sent into Adobe [!DNL Analytics], it is transferred to Adobe audience management. Adobe recommends against providing personal data to Adobe [!DNL Analytics]. Rather, use a one-way hash to pseudonymize the data before it is sent to Adobe. 
* Segments originating in [!DNL Analytics] via the back-end segment sharing capability.
* The demdex.net cookie is set if third-party cookies are not blocked. The `AMCV_###@AdobeOrg` first-party cookie is always set with the Experience Cloud ID service.

All these data elements are delivered to Adobe Audience Manager in the form of log files. Audience Manager processes and stores this data within the United States. Audience Manager does not provide an option to store or process this data outside of the United States. 

**Cookies and Opt-Outs** 

Use of real-time audience profiling leverages the Audience Manager cookie, in addition to the cookies used for [!DNL Analytics] and [!DNL Target]. 

If you want to provide the proper opt-out ability, visitors to your site must add the Audience Manager opt-out to your existing opt-out process. 

See [Adobe Experience Cloud - Implementing Adobe Opt-Outs](https://docs.adobe.com/content/help/en/analytics/implementation/javascript-implementation/data-collection/opt-out.html) for instructions. 

See [Data Collection CNAMEs and Cross-Domain Tracking](https://docs.adobe.com/content/help/en/id-service/using/reference/analytics-reference/cname.html) for enabling cross-domain tracking. 
