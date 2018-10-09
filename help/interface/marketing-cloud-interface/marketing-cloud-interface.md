---
description: An overview of new features and updates in the Experience Cloud.
keywords: core services
seo-description: An overview of new features and updates in the Experience Cloud.
seo-title: What's new in the Experience Cloud
solution: Experience Cloud
title: What's new in the Experience Cloud
uuid: bc1b1542-1a37-4da1-bcfd-fc86af881642
index: y
internal: n
snippet: y
translate: y
---

# What's new in the Experience Cloud

An overview of new features and updates in the Experience Cloud.


<!-- <p>Nate's Links: </p> 
<p> Here are links to the new CI decks: </p> 
<p> Retail: <a href="https://files.acrobat.com/a/preview/e00cf164-75ba-4467-abe5-a58a0bcc198c" format="https" scope="external"> https://files.acrobat.com/a/preview/e00cf164-75ba-4467-abe5-a58a0bcc198c</a> </p> 
<p> Finserve: <a href="https://files.acrobat.com/a/preview/bbb1fdb5-999e-41b4-b697-98f3abbb24b9" format="https" scope="external"> https://files.acrobat.com/a/preview/bbb1fdb5-999e-41b4-b697-98f3abbb24b9</a> </p> 
<p> B2B/Tech: <a href="https://files.acrobat.com/a/preview/3f18a517-a672-46a0-92f0-83f30572dfa7" format="https" scope="external"> https://files.acrobat.com/a/preview/3f18a517-a672-46a0-92f0-83f30572dfa7</a> </p> 
<p> Travel & Hospitality: <a href="https://files.acrobat.com/a/preview/dfacc9db-f2f6-40ae-8895-ecf8de947f60" format="https" scope="external"> https://files.acrobat.com/a/preview/dfacc9db-f2f6-40ae-8895-ecf8de947f60</a> </p> -->

## August 2018 {#section_7388CDAB723B49809AABEFEE85CF6378}

Fixes and improvements for August, 2018. 

* Made improvements on assets comment sync across Creative Cloud and Experience Cloud. (CORE-15971)
* Added feature flag to control Experience Cloud-Creative Cloud asset sync. (CORE-15938)
* Made improvements to Audience segments creation, including better search and listing experience. (CORE-5833, CORE-14278)
* Fixed a high priority issue that blocked folder sharing from MAC to Creative Cloud. (CORE-16677)



## July 19, 2018 {#section_EBB549EBABB7480884A180237ADCCD02}

Fixes and improvements for July, 2018. 

* Deployed a back-end capability to control asset sharing between Marketing Cloud-to-AEM and Marketing Cloud-to-Creative Cloud. (CORE-14386)
* Fixed an issue that blocked provisioning of new tenants on some environments. (CORE-15509)
* Fixed an issue that redirected users to [!DNL marketing.adobe.com] while accessing [!DNL experiencecloud.adobe.com] via [!DNL http] instead of [!DNL https] (secured). (CORE-15587)
* Fixed an issue that blocked notifications for some new tenants. (CORE-15240)



## June 14, 2018 {#section_7ABC327992CB46B0B8E4A631B8B68899}

Fixes and improvements for June, 2018. 


* Enabled a link to GDPR access for Administrators. (CORE-11731)
* Updated Beta Feedback feature to restrict file types that can be attached to feedback. (CORE-10474)
* Fixed an issue with deleting audiences from Audience Library. (CORE-12792)
* Fixed an issue that resulted in a blank screen while accessing Workspace links using Federated IDs. (CORE-11620)




## May 10, 2018 {#section_498AF78DA17C4720AA0F32B51493E550}

New features and fixes in the [!DNL Adobe Experience Cloud] interface. 

| Feature | Description |
|--- |--- |
|New administration landing page|When you sign in to the Experience Cloud and navigate to the Administration page, a new intuitive interface is available to help you quickly access your Experience Cloud solutions and Core Services.|
**Fixes** 

* Fixed an issue where the image upload failed due to a Scene7 update. (CORE-12746)
* Made updates to drop support for TLS 1.0 protocol, as mandated by PCI to eliminate security vulnerability. (CORE-7695)


## October 26, 2017 {#section_11195859B4094177A939C0561428B525}

**Known Issue** 

Many of the maintenance notifications around scheduled maintenance / product updates are missing from the notifications email digest. We are working to ensure all maintenance notifications are included in the email digest. 

## August 8, 2017 {#section_2313A875454044F490B418506DD24593}


| Feature | Description |
|--- |--- |
|Notifications - Granular settings|You can enable notifications for product and solution events and activities, including notifications about [Customer Attributes](../attributes/attributes.md) upload activity.|
|Notifications - Maintenance notifications|In Notification settings, you can enable maintenance notifications for products and solutions.|
|Admin Console for Experience Cloud Solutions|New Experience Cloud customers can begin using the Admin Console, a central location for managing your Adobe entitlements across your entire organization.<br>The migration to the Admin Console for user management will proceed in waves. Adobe will contact you (system administrators) when it is time to migrate.<br>Analytics administrators, see  [Analytics Migration](https://marketing.adobe.com/resources/help/en_US/experience-cloud/admin-console/analytics-migration/).|


## May 22, 2017 {#section_242FE649FA1B4BFA88EC6E353D175ACC}

| Feature | Description |
|--- |--- |
|Bulk Report Suite Mapping|In  Administration >  Report Suite Mapping, you can now select multiple report suites, then map them to an organization. (Previously, you had to map them individually.)  <br>[Mapping report suites](../core-services/core-services.md) to a single organization helps enable cross-solution features and services in the Experience Cloud.|
|Updates to Experience Cloud Audiences|**Applying Report Suites**<br>You can now apply a report suite to all your [audience rules](https://marketing.adobe.com/resources/help/en_US/mcloud/t-audience-create.html). (Previously, you had to specify a report suite in each rule definition.) <br>**Props and Variables**<br>You can now include Analytics props and default variables (in addition to eVars and events) in real-time audiences.|

## November 8, 2016 - 16.11.1 {#section_7065A9BCCDF544C2BB37E9A7D661EA6A}


| Feature | Description |
|--- |--- |
|Update to Profile & Passwords|Users can no longer edit IMS user profile information under  Personal Details In  Edit Profile >  Profile & Passwords. Instead users are redirected to `accounts.adobe.com`. This applies to all identity types (Adobe ID, Enterprise, and Federated).|

**Fixes** 

* Fixed an issue with technical passwords that caused an error in folder sharing between Creative Cloud and Experience Cloud. (MAC-31067, MAC-32014)
* Fixed an issue with the upload of certain file types, including PDF, that was found after the October release in Assets Core Service. (MAC-32517)


