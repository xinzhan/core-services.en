---
description: Frequently asked questions about Customer attributes in Adobe Experience Cloud, for Adobe Analytics and Adobe Target.
keywords: Customer Attributes
solution: Experience Cloud
title: Get answers to frequently asked questions about Customer Attributes 
uuid: e93eb531-23c7-4d75-92e8-75699f58546a
feature: Customer Attributes
topic: Administration
role: Administrator
level: Experienced
exl-id: 6031e544-822b-4843-b3d8-98a36a3c40e8
---
# Frequently asked questions about [!UICONTROL Customer Attributes]

Frequently asked questions and best practices for [!UICONTROL Customer Attributes] in Adobe Analytics and Adobe Target.

## Best practices and limitations {#section_7F5189B3DAA84EE6865B91D2026EE05A}

Guidance and limitations when using [!UICONTROL Customer Attributes].

| Issue | Description |
|--- |--- |
|[!UICONTROL Customer attribute] subscription limitations|When you upgrade to Analytics Premium, there is a 24-hour delay before more attributes are available. You might see an [!UICONTROL Attribute Subscription Max] error issued during this delay.|
|Multiple logins on the same device|When using [!UICONTROL Customer Attributes] to upload customer profiles into a data source, Adobe recommends against users sharing devices (meaning, the same Experience Cloud ID). The Experience Cloud ID (ECID) persists on the device. Sharing devices can cause the ECID to link multiple users to the same ECID, causing unexpected results in [!DNL Target]. **Note:** For Mobile, the ECID is permanent after the Mobile app is installed. Reinstall the app to generate a new ECID. For Web, a new ECID is generated after the browser cookie is cleared.|
|Daily frequency upload limitation| Adobe recommends that you update Customer Attributes only once per day. You must wait at least 24 hours to upload another customer profile data file for the same set of profiles.|
|Custom Analytics ID (`s.visitorID`)|Setting a customer ID using `s.visitorID` is a method of identifying users in Analytics. However, integrations in which [!DNL Analytics] data is exported or imported using the ID Service do not function when a visitor is identified using `s.visitorID.`<br>This includes, but is not limited to, shared Audiences, [!DNL Analytics] for Adobe Target (A4T), and [!UICONTROL Customer Attributes].<br>For these integrations, setting a custom Analytics ID is not supported.|
|Character length limitations in [!DNL Analytics]|When creating an [!DNL Analytics] subscription, field lengths for the uploaded files are truncated to 255.|

{style="table-layout:auto"}

## FAQ about Customer Attributes {#section_E47866EEA83348E09FE43CEC5E44C461}

| Question | Answer |
|--- |--- |
|Can I receive notifications about upload status for Customer Attributes?|Yes.|
|What should I do to get started with Customer Attributes?|<ol><li>Get provisioned. If you are an Analytics customer, Adobe is provisioning you for Customer Attributes. If you use only Adobe Target and do not have Analytics, request provisioning for core services by contacting Customer Care.</li> <li>Have a conversation with your CRM team. Find out what kind of customer data is available that you want to use in Analytics and throughout the Experience Cloud.</li><li>Implement core services. See [Enabling your solutions for core services](core-services.md) for steps on how to modernize your implementation. (See the section about syncing customer IDs for important information.)</li></ol> **Note:** An administrator's FAQ for implementing core services is available [here](faq.md).|
|How many Customer Attributes am I allowed to use?|You can upload hundreds of `.csv` columns to the Customer Attribute service. However, when configuring subscriptions and selecting attributes, the following limits apply (per report suite), depending on the solutions you own:  <ul><li>Foundation: 0</li><li>Select: 3</li><li>Prime: 15</li><li>Ultimate: 200</li><li>Standard: 3 total</li><li>Premium: 200</li><li>Adobe Target Standard: 5</li><li>Adobe Target Premium: 200</li></ul>|
|Is migrating to the Experience Cloud ID Service required?|Migration depends on the solutions you use. <ul><li>Adobe Analytics: Strongly recommended </li><li>Adobe Target: Required. </li></ul><br>Using the Experience Cloud ID service enables the latest Experience Cloud functionality, including real-time audiences, the Adobe Target modernization, Analytics integration, and video heartbeat tracking. <br> For more details, see [Enable your solutions for core services](core-services.md). <br>**Note:** The [Experience Cloud ID Service](https://experienceleague.adobe.com/docs/id-service/using/intro/overview.html?lang=en) is the modernized implementation of what is formerly known as _Analytics visitor ID service._|
|How does the Customer Attribute functionality relate to Adobe Audience Manager?|While Audience Manager can receive data to perform audience identification, it cannot perform analytics functionality that ties attributes to historical behavioral data. It also does not provide the reporting, analysis, and segmentation capabilities that are available in Adobe Analytics. [!UICONTROL People] enables rich data from across solutions to be tied together and associated with a single ID for use across the Experience Cloud. <br>In Adobe Target, Customer Attributes appear as individual attributes that can be combined with other rules to build audiences. Audiences shared to the [!UICONTROL People] service are full audiences that cannot be modified.|
|**(Analytics only)** How is this functionality different from what is provided in Analytics premium?|In the past, customers interested in combining Customer Attribute data with Analytics data have relied heavily on the Data Workbench tool for this functionality. [!UICONTROL Customer Attributes] exposes this functionality to a wider audience by providing Customer Attributes as dimensions and metrics in reports & analytics, Ad Hoc Analysis, and report builder. Analytics Standard customers have access to Customer Attributes, but with limited capabilities. The full capability is available to Analytics Premium customers.|
|**(Adobe Target Only)** Can I pre-load or upload data for customers that Adobe Target has never seen?|Yes. When the visitor makes their first request to Adobe Target, the system fetches the existing information Adobe has about them from Customer Attributes and use that data for targeting. **Note:**  Retrieving this data can take up to 20 min from the visitor's first interaction with Adobe Target.|
|**(Adobe Target Only)** Can I create a super audience by combining Customer Attribute data with shared audience data?|No. Shared audience data is a completed audience.|
|**(Adobe Target only)** How does the [!UICONTROL Customer Attributes] functionality compare to Adobe Target's bulk profile API?|The bulk profile API enables Adobe Target profiles to be updated directly via the API, either for an individual profile or in bulk. The capability is similar to Customer Attributes, with the following key differences:<ul><li>The profile API is a REST API call and Customer Attributes uses FTP.</li><li>Adobe Target's profile API only sends data to Adobe Target instead of to the whole Experience Cloud.</li><li>Customer Attributes provides a simple interface to create and manage this external data.</li></ul>|
|**(Adobe Target only)** Does uploading data from Customer Attributes to Adobe Target extend the Adobe Target visitor's profile lifetime?|Yes. See [Visitor Profile Lifetime](https://experienceleague.adobe.com/docs/target/using/audiences/visitor-profiles/visitor-profile.html?lang=en) in Adobe Target Help.|
|**(Adobe Target only)** Can I target on the data uploaded in Customer Attributes immediately after the visitor is identified by the customer ID?|Yes. On the server call to Adobe Target, which includes the mbox third-party ID, all Customer Attribute data are available.|
|**(Adobe Target only)** What does the **[!UICONTROL Sync Status]** column represent for files uploaded in Customer Attribute source?|The number of records published and synced by Adobe Target can be viewed by selecting the Sync Status icon against a specific attribute file. `Sync %` is a real-time metric that specifies the % of profiles that have been synced in Adobe Target.<br> **Note:** It may take up to 24 hours for attributes to sync with Adobe Target.|
|What do the file upload metrics represent in Customer Attributes Source?|You can check the status of attributes uploaded to Customer Attributes with the help of following metrics: <ul><li>Records:  Number of records in the attributes file.</li><li>**New Records:** Number of new records present in the attributes file.</li> <li>**Updated Records:** Number of records in that exist in Customer Attributes with updated values in the file.</li><li>**All Data (Records):** Total number of records successfully uploaded to Customer Attributes.</li></ul>|

{style="table-layout:auto"}