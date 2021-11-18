---
description: Learn how to use attribute rules to create an audience and define a composite audience in Adobe Experience Cloud.
keywords: core services
solution: Experience Cloud
title: Create an audience 
uuid: 7e622539-296e-4ff3-93b0-ec1c08b35429
feature: Audience Library
topic: Administration
role: Admin
level: Experienced
exl-id: b65a12f5-fa89-400a-b279-13c381cd6c22
---
# Create an audience

Learn how to use attribute rules to create an audience and define a composite audience in Experience Cloud.

This article helps you understand how to:

* Create an audience
* Create a rule
* Use rules to define a composite audience

The following graphic represents two rules in a composite audience.

![Two rules in a composite audience](assets/audience_sharing.png)

Each circle represents a rule that defines audience membership. Visitors that qualify as members in both audience rules overlap to become the composite, defined audience.

>[!NOTE]
>
>The audience is fully defined after data collection for the specified period completes.

The following example shows how to create the rules for a composite audience. This audience is composed of:

* Home & Garden section derived from page data, or raw analytics data.
* Chrome and Safari users derived from an [!DNL Adobe Analytics] segment [published](audience-library.md#task_32FEEFE0B32E4E388CD4D892D727282A) to the [!DNL Experience Cloud].

  ![Create the rules for a composite audience](assets/audience_create.png) 

**To create an audience**

1. In the [!DNL Experience Cloud], under [!DNL Experience Platform], select **[!UICONTROL People]** > **[!UICONTROL Audience Library].**
1. On the [!UICONTROL Audiences] page, select **[!UICONTROL New]**. ![](assets/add_icon_small.png)

   ![Step Result](assets/audience_create_new.png)

1. On the [!UICONTROL Create New Audience] page, specify a title and description.
1. Under [!UICONTROL Rules], select an attribute source:

   * **[!UICONTROL Real-Time Analytics Data:]** (or Raw data) This is attribute data derived from Real-Time Analytics image requests, and includes data such as eVars and events. You must select a report suite when using this attribute source, and define the dimension or event to include. This report suite selection provides the variable structure used by the report suite.
   >[!NOTE]
   >
   >Due to caching, deleted report suites in Analytics require 12 hours before the deletion is shown in the Experience Cloud.

   * **[!UICONTROL Experience Cloud:]** Attribute data derived from the [!DNL Experience Cloud] sources. For example, this can be data from audience segments you create in [!DNL Analytics], or data from [!DNL Audience Manager].

1. Define audience rules, then select **[!UICONTROL Save].**

>[!NOTE]
>
>You should have an understanding of your implementation variables when defining audience rules.

Under [!UICONTROL Rules], define the *`Home & Garden`* attribute selections:

* **[!UICONTROL Attribute Source:]** Raw Analytics Data
* **[!UICONTROL Report Suite:]** Report Suite 31
* Dimension = **[!UICONTROL Store (Merch) (v6)]** > **[!UICONTROL Equals]** > **[!UICONTROL Home & Garden]**

![Attribute selections in Audience Library](assets/home_garden.png)

The *Chrome & Safari Visitors* is an audience segment shared from Analytics:

* **[!UICONTROL Attribute Source:]** Experience Cloud
* **[!UICONTROL Dimension:]** Chrome & Safari Visitors

![Chrome & Safari Visitors](assets/chrome_safari.png)

For comparison, you might add an *OR* rule to see all visitors to a site section, such as Patio & Furniture.

![OR rule for an audience](assets/audiences_rule_patio.png)

The resulting rule is a defined audience comprising Chrome & Safari users who visited Home & Garden. The Patio & Furniture segment provides additional insight into all visitors visiting that site section.

![Defined audience in Experience Cloud](assets/defined_audience.png)

* **Historical Estimate:** (Dotted circle) Represents rules created based on [!DNL Analytics] data.
* **Actual Audience:** (Solid circle) Any rule created that has 30 days of data from Audience Manager. When the Audience Manager data reaches 30 days, the line becomes solid and represents actual numbers.

After the data collection completes for the specified period, the circles combine to show a defined audience.

After the audience is saved, it is available for other applications. For example, you can include a shared audience in an Adobe Target activity.
