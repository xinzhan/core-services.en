---
description: Learn about signing in to the Adobe Admin Console, managing Experience Cloud user permissions and product profiles, and browser support.
keywords: Experience Cloud services
solution: Experience Cloud
title: Learn how to manage users and products 
index: yes
---

# Manage Experience Cloud users and products {#topic_3FCB4099640647E3B2411ADBFCE81909}

Learn about signing in to the Admin Console, managing Experience Cloud user permissions and product profiles, and browser support.

>[!IMPORTANT]
>
>Managing users in the Admin Console introduces new terms, interfaces, and navigation. The following information describes these changes and provides links to additional help resources. This help supplements the information in the [Enterprise Administration User Guide](https://helpx.adobe.com/enterprise/managing/user-guide.html) for all Adobe cloud products.

## What's new in Experience Cloud user management {#concept_06A0A13362F644FB90F947238407637A}

Learn about the latest features in Experience Cloud user management.

<!-- ### Business ID type

Adobe is introducing an identity type called Business ID. This identity type improves the control of user and product management. Adobe is migrating all Adobe IDs (owned by individuals) that are used for business to the new enterprise Business IDs owned by your organization.

If you are an existing Experience Cloud customer, Adobe will migrate all your users with Adobe IDs in the Admin Console to Business IDs. If you are a new enterprise or teams customer, you will add users to the Admin Console using one of the available identity types: Business ID, Enterprise ID, or Federated ID.

What to do

* Your users will need to accept Terms of Use (TOU) changes prior to accounts being migrated to Type2e. 
* Users that belong to multiple organizations might see a Profile Selection screen during the login workflow and need to select the correct one. This ensures that they are logging into the correct organization. (There might be multiple profiles to choose from if a user was a member of multiple organizations before the migration.)

Beginning May 2020, enterprise administrators cannot use the Adobe ID for new organizations created in the Admin Console. Latest: https://wiki.corp.adobe.com/pages/viewpage.action?spaceKey=engage&title=Type2e+DX+GTM-->

### Admin Tool

Administrators can view a sortable and filterable list of all Experience Cloud users and their details in the Admin Tool. See [View Experience Cloud users in the Admin Tool](admin-tool-experience-cloud.md).

## Signing in to the Admin Console {#section_705072FD4EBE4B70BC69EC81F2BB8669}

Administrators no longer manage users in solutions. User and product management for Experience Cloud now occurs in the Admin Console.

To sign in to the Admin Console:

1. Navigate to [https://adminconsole.adobe.com/enterprise/](https://adminconsole.adobe.com/enterprise/#).
1. Type your [Adobe ID or Enterprise ID](https://helpx.adobe.com/enterprise/help/identity.html) and password.

Alternatively, from the Experience Cloud menu ( ![](assets/menu-icon.png)), click **[!UICONTROL Administration]** > **[!UICONTROL Launch Admin Console]**.

**Related help**

[Administration User Guide](https://helpx.adobe.com/enterprise/using/users.html) for the Creative Cloud and Document Cloud. Some information is relevant to Experience Cloud user management, such as [managing identity types](https://helpx.adobe.com/enterprise/help/identity.html).

[Sign in and manage your profile settings](../admin-getting-started/getting-started-experience-cloud.md#topic_AC564B6795334DE39359ADD87F52F2E0) to manage passwords, organizations, and notifications.

## Product profiles and groups {#section_AB50558124D541CF80A0D3D76D35A4BF}

The addition of product profiles marks a shift from how solution products and services were previously managed (by using groups). In the Admin Console, permissions are based on product profiles, which are groups of products and services that you can assign to users.

For example in Analytics, you can configure a collection of reporting tools, such as Analysis Workspace and Report Builder, along with report suites, metrics, dimensions, and so on. You can permission users to a product profile by adding them to the profile. See [Assign Analytics access permissions to a product profile](../admin-getting-started/admin-getting-started.md#task_040673FE3E3E429B9531FBCB8B6A4391).

**Related help** 

[Delegate limited administration privileges](../admin-getting-started/admin-getting-started.md#task_3A072C4AA9734BC59FFA7E015271BC7E)

## Analytics {#section_97DE101F92CD494AB073893680992F1A}

Manage Analytics user and product permissions in the Admin Console. 

[Assign Analytics access permissions to a product profile](../admin-getting-started/admin-getting-started.md#task_040673FE3E3E429B9531FBCB8B6A4391)(on this page).

**User Account Migration**

An Analytics user ID migration tool is available to help Analytics administrators migrate user accounts from Analytics User Management to the [Adobe Admin Console](https://adminconsole.adobe.com/enterprise/).

The account migration is being rolled out to customers in phases. Adobe will notify and assist you when it is your time to migrate existing user accounts from **[!UICONTROL Admin Tools]** > **[!UICONTROL User Management]** to the Admin Console.

After the migration, users sign in using their Adobe ID (or Enterprise ID) and authenticate to their Experience Cloud solutions and services at [experiencecloud.adobe.com](https://experiencecloud.adobe.com). If users attempt to sign in via legacy logins ([!DNL my.omniture.com] and [!DNL sc.omniture.com]) they are redirected to [!DNL experiencecloud.adobe.com].

**Related help** 

[Analytics User ID Migration](https://docs.adobe.com/content/help/en/analytics/admin/user-product-management/user-management/migrate-users/c-migration-tool.html)

## Adobe Target - product profiles vs workspaces {#section_3860AF177C9E4C7E9C390D36A414F353}

In Adobe Target, a workspace is a product profile. It lets an organization assign a specific set of users to a specific set of properties. In many ways, a workspace is similar to a report suite in Adobe Analytics.

See:

* [Enterprise User Permissions](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/property-channel.html)
* [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html)
* Video: [How to Configure Adobe Target Workspaces in Adobe Admin Console](https://helpx.adobe.com/target/kb/how-to-configure-target-workspaces-in-adobe-admin-console0.html)

## Campaign - product profiles, tenants, and security groups {#section_09CDF75366444CF5810CF321B7C712F3}

A *tenant* in Campaign displays as a *product* in the Admin Console Products page.

*Security group* displays as a product profile.

See [Managing groups and users](https://helpx.adobe.com/campaign/standard/administration/using/managing-groups-and-users.html) for information about security groups and assigning users to security groups.

## Experience Platform Launch {#section_F2DA6778DD2D48AA8F794041971EE6B1}

Experience Platform Launch displays on the Products page in the Admin Console. You can include other solutions and services in a Launch product profile.

See [User Management](https://docs.adobelaunch.com/launch-reference/administration/user-permissions) for information about user permissions in the Admin Console and set up Launch-specific options, including assigning rights to profiles.

## Experience Manager as a Cloud Service

Adobe Enterprise customers are represented as IMS Organizations in the Adobe Admin Console. This is the portal used by Adobe customers to manage their product entitlements for their users and groups. AEM customers can use the Adobe Admin Console to manage their product entitlements and IMS authentication to AEM as a Cloud Service.  

See [IMS Support for AEM as a Cloud Service](https://docs.adobe.com/content/help/en/experience-manager-cloud-service/security/ims-support.html#managing-products-and-user-access-in-admin-console).

## Dynamic Tag Manager {#section_3A41CF2BD5994B9891537D063571D4ED}

Invite users to Dynamic Tag Management and assign user roles and add users to groups.

See [Users and Permissions](https://docs.adobe.com/content/help/en/dtm/using/admin/users.html) for information about how to invite users to Dynamic Tag Management and assign user roles and add users to groups.

## Audience Manager {#section_C31E3FA8A1E14463B1B3E07235F1983C}

Create Audience Manager users and assign them to groups. You can also view limits (traits, segments, destinations, and [!DNL AlgoModel]).

See [Administration](https://docs.adobe.com/content/help/en/dtm/using/admin/users.html) in Audience Manager help.

## Manage Experience Cloud products {#task_16335111C52D40E9BAC73D0699584DBF}

Create a product profile and assign it to a permission group.

When you invite a user to an organization, you can give the user access to products and product profiles. You can also delegate limited administrative permissions to a user. Similarly, you can create user groups, then add the group to a product profile to enable access.

1. In the [Admin Console](https://adminconsole.adobe.com/enterprise/), click **[!UICONTROL Products]**.
1. Click **[!UICONTROL New Profile]**.
1. Configure the profile details, then click **[!UICONTROL Next]**.
1. Click **[!UICONTROL Done]**.

More help is available at:

* [Manage products and profiles](https://helpx.adobe.com/enterprise/using/manage-products-and-profiles.html)
* [Enterprise User Permissions](https://docs.adobe.com/content/help/en/target/using/administer/manage-users/enterprise/property-channel.html) in Adobe Target help for more information.
* Video: [How to Configure Adobe Target Workspaces in Adobe Admin Console](https://helpx.adobe.com/target/kb/how-to-configure-target-workspaces-in-adobe-admin-console0.html)

## Assign Analytics access permissions to a product profile {#task_040673FE3E3E429B9531FBCB8B6A4391}

Assign Analytics report access permissions (report suites, metrics, dimensions, and so on) to a product profile.

For example, you can create a product profile that contains multiple Analytics tools ( [!UICONTROL Analysis Workspace], [!UICONTROL Reports & Analytics], and [!UICONTROL Report Builder]), with permission to specific metrics and dimensions (including eVars), and capabilities like segment or calculated metrics creation.

1. Sign in to the [Admin Console](https://adminconsole.adobe.com/enterprise), then click **[!UICONTROL Products]** (or click your product name).
1. In the product profile, then click **[!UICONTROL Permissions]** (available only to administrators).
1. Configure the profile's permissions:

| Element | Description |
|--- |--- |
|Report Suites|Enable permissions to specific report suites.|
|Metrics|Enable permissions for traffic, conversion, custom events, solution events, content aware, and so on.|
|Dimensions|Customize user access at a granular level, including eVars, traffic reports, solution reports, and path reports.|
|Report Suite Tools|Enable user permissions for Web Services, Report Suite Management, Tools and Reports, and Dashboard Items.|
|Analytics Tools|Enable user permissions for General items (billing, logs, etc.), Company Management, Tools, Web Service Access, Report Builder, and Data Connectors integration. Company settings from the Customize Admin Console category have been moved to Analytics Tools.|

## Delegate administrative roles to users {#task_3A072C4AA9734BC59FFA7E015271BC7E}

In the Admin Console, you can delegate limited administrative rights to others in your organization. Delegated roles enable users to administer software access to end users, provide access deployment capabilities, and function as support delegates.

For example, you can:

* Allow your creative director to grant access to Creative Cloud.
* Allow your marketing director to grant access to the Experience Cloud.
* Keep these two roles separate so they cannot overstep each other's roles.

By using these roles, you can simultaneously delegate management to others without providing more capability than they need.

1. In the Admin Console, click **[!UICONTROL Users]**, then click the user's name.
1. Click **[!UICONTROL Edit admin rights]**.
1. Configure the user's admin rights.
1. Click **[!UICONTROL Next]** to review the settings, then click **[!UICONTROL Save]**.

## Supported browsers and system requirements {#concept_CDC4371EB9BF433E9534F8716DC8A088}

Supported browsers in the Experience Cloud.

* [!DNL Microsoft Edge] (Microsoft has [ended support](https://www.microsoft.com/en-us/WindowsForBusiness/End-of-IE-support) for Internet Explorer 8, 9, and 10. As such, Adobe will not fix issues reported against these specific versions of Internet Explorer.)
* [!DNL Google Chrome]
* [!DNL Firefox]
* [!DNL Safari]
* [!DNL Opera]

**Note:** Although the Experience Cloud interface supports these browsers, individual solutions might not support every browser. (For example, [Analytics](https://docs.adobe.com/content/help/en/analytics/admin/sys-reqs.html) does not support [!DNL Opera], and [Adobe Target](https://docs.adobe.com/help/en/target/using/implement-target/before-implement/supported-browsers.html) does not support [!DNL Safari].)

### Solution and product requirements

* [Analytics](https://docs.adobe.com/content/help/en/analytics/admin/sys-reqs.html)
* [Report Builder](https://docs.adobe.com/content/help/en/analytics/analyze/report-builder/report-builder-setup/system-requirements.html)
* [Adobe Target](https://docs.adobe.com/help/en/target/using/implement-target/before-implement/supported-browsers.html)
