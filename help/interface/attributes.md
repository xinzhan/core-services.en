---
title: How to use Customer Attributes
description: Learn about the Customer Attributes service in Adobe Experience Cloud. Discover how to upload Customer Attribute data for use in Adobe Analytics and Adobe Target.
solution: Experience Cloud
feature: Customer Attributes
role: Admin
topic: Administration
level: Experienced
exl-id: fe8ad013-76da-49f8-aa51-dc5f6c1b1d79
---
# Customer Attributes overview 

[!UICONTROL Customer Attributes] in Experience Cloud enables you to upload your captured enterprise data from a customer relationship management (CRM) database. You can upload the data into a Customer Attribute data source in the Experience Cloud, then use the data in Adobe Analytics and Adobe Target.

To locate this feature, navigate to **[!DNL Experience Platform]** > **[!UICONTROL People]** > **[!UICONTROL Customer Attributes]**

![Customer Attributes overview](assets/custom_reports.png)

## Prerequisites for uploading Customer Attributes {#section_BD38693AFBF34926BA28E964963B4EA0}

* **Solution enablement:** [Enable your solutions for Experience Platform services](core-services.md#concept_07ED1D5C64234E77976E6D572E78FB9C).

* **Group membership:** To upload Customer Attribute data, users must be members of the [Customer Attributes group](admin-getting-started.md#task_3295A85536BF48899A1AB40D207E77E9). You must also belong to either an Adobe Analytics group or an Adobe Target group.

  To know whether your company has access to Customer Attributes, your [!DNL Experience Cloud] administrator should log into the [Experience Cloud](https://experience.adobe.com). Navigate to **[!UICONTROL Administration]** > **[!UICONTROL Admin Console]** > **[!UICONTROL Products]**. If *Customer Attributes* displays as one of the [!UICONTROL Product Profiles], you are ready to begin.

  Users that are added to the Customer Attributes see the [!UICONTROL Customer Attributes] menu item on the left side of the Experience Cloud interface.

* **Adobe Target** `at.js` (any version) or `mbox.js` version 58 or later is required for Customer Attributes.

  See [How to deploy at.js](https://experienceleague.adobe.com/docs/target/using/implement-target/client-side/deploy-at-js/how-to-deployatjs.html?lang=en) or [Mbox.js Implementation](https://experienceleague.adobe.com/docs/target/using/implement-target/client-side/mbox-implement/mbox-download.html?lang=en).

## What is enterprise customer data? {#section_6F34C29F11414842AA57D2B1248FA3C6}

Enterprise data resides in other systems. It can be complex and mean different things to different people. This data can include information such as memberships, loyalty level, age, gender, products owned, interests, and Lifetime Value.

The following image is an example of a data file showing subscriber data for products, including member IDs, entitled products, most-launched products, and so on.

![What is enterprise customer data?](assets/01_crs_usecase.png)

After you create the data file, you can upload it to the Customer Attribute source that you create in **[!UICONTROL Experience Cloud]** > **[!UICONTROL Customer Attributes]**.

See [Upload Customer Attribute data](t-crs-usecase.md#task_BCC327B2A0EF4A1BBB2934013AB92B78) to learn this workflow.

## Examples of Customer Attributes in Analytics and Target {#section_4E77650F6CEE4C4ABCD0B3221A5AE5D9}

After the data resides in the Experience Cloud, you can customize it and share it to solutions for reporting, segmentation, activities, and campaigns.

For example:

| Solution | Advantages and Use Cases |
|--- |--- |
|Adobe Analytics|Marketers and analysts can understand:<ul><li>The online campaigns that are most effective with your gold-level customers.</li><li>The products that gold-level customers search for versus products that platinum-level customers search for.</li><li>Whether your site redesign is having a positive impact on conversion rates for older customers.</li><li>The products that customers with a low lifetime value tend to research on my site.</li></ul>|
|Adobe Target|Attribute data enables Adobe Target users to:<ul><li>Show loyalty club members special discounts and offers.</li><li>Recommend more expensive products to your luxury customers.</li><li>For customers who already receive emails, show an up-sell offer in the space normally reserved for email sign-ups</li></ul>|

{style="table-layout:auto"}
