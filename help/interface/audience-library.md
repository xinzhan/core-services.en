---
seo description: Learn how to manage the translation of visitor data into audience segmentation in Adobe Experience Cloud Audience service.
solution: Experience Cloud
type: Documentation
title: Adobe Experience Cloud Audiences 
uuid: 92faf3a8-1375-4e32-905b-74cad48144d3
description: Learn how to manage the translation of visitor data into audience segmentation in Experience Cloud Audience service.
feature: Audience Library
topic: Administration
role: Admin
level: Experienced
exl-id: 1c6e54ac-4886-46ed-9df7-201d2df31847
---
# Experience Cloud audiences {#topic_679810123CAA4E0CA4FA3417FB0100C7}

Audiences are collections of visitors (a list of visitor IDs). Adobe's Audience Library lets you manage the translation of visitor data into audience segmentation. As such, creating, and managing audiences is similar to creating and using segments. You can also share the audience segment to products and services in [!DNL Experience Cloud]. 

![Experience Cloud audiences](assets/audiences.png) 

Audiences can be created or derived from various sources, such as: 

* New ones created in the [!DNL Experience Cloud]
* [!DNL Analytics] segments published to the [!DNL Experience Cloud]
* [!DNL Audience Manager]

**Real-Time versus historical audiences**

All audiences, regardless of where they are sourced, are accessible for real-time targeting use cases. However, audiences shared from Analytics to Audience Manager are not accessible for real-time targeting. The system evaluates audiences in two ways: 

* Historical audiences from Analytics are evaluated every four hours. Total time to process and share takes up to eight hours. Historical audiences always include return visitors.
* Real-time audiences are sourced in the Experience Cloud Audiences and evaluated in real time.

## How applications use audiences {#concept_01EB9345C5344597BC94A864EDD38EE1}

The following table describes how audiences are used in Experience Cloud applications: 

| Solution | Description |
|--- |--- |
|Experience Cloud Audiences|Create, manage, and share audiences natively using the [Audience Library](audience-library.md) interface. You can:<ul><li>Use real-time audiences using raw analytics attributes</li><li>Combine audiences to create composite ones, joining real-time and historical data</li><li>See graphical views of estimated audiences size</li></ul><br>For suggestions about what type of audience you want to create see: [Experience Cloud Audiences](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en).|
|Analytics|In segmentation, you can build a segment, combine it with a report suite, and then publish the segment to the Experience Cloud. Publishing the segment displays it on the [!UICONTROL Audience Library] page in Experience Cloud. (See [Publish Segments to the Experience Cloud](https://experienceleague.adobe.com/docs/analytics/components/segmentation/segmentation-workflow/seg-publish.html?lang=en) in Analytics help for details.) The audience is also available as a targeted audience for a campaign experience delivered by Adobe Target, and in Audience Manager. After you share an audience from Adobe Analytics, and select it for use in an active campaign, the visitor profiles who meet the segment definition criteria for the past 90 days are sent to [!UICONTROL Audience Services]. The limit for shared audiences has been increased to 75. Audiences shared to the Experience Cloud from Analytics cannot exceed 20 million unique members. Also, due to caching, deleted report suites in Analytics require 12 hours before the deletion is shown in the Experience Cloud.|
|Mobile Services|Analyze mobile traffic using the sunburst visualization in the [!UICONTROL Device Types] report.|
|[!DNL Target]|The [ID service](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=en) unifies visitor IDs and data into a single, actionable profile for use across applications. The [Publish to the Experience Cloud](audience-library.md) checkbox during the segment creation process in Adobe Analytics allows the segment to be available within the Adobe Target's custom audience library. A segment created in Analytics or Audience Manager can be used for activities in [!DNL Target]. For example, you can create campaign activities based on [!DNL Analytics] conversion metrics and audience segments created in [!DNL Analytics].|
|Audience Manager|Shared audiences are available in Audience Manager segmentation. All Experience Cloud audiences are available natively in Audience Manager, which provides:<ul><li>Built-in automation regarding how they are shared and consumed in application workflows</li><li>Offsite destinations</li><li>Look-alike modeling</li></ul>|
|Campaign|<ul><li>Import shared audiences from different Adobe Experience Cloud applications into Adobe Campaign.</li><li>Export recipient lists in the form of shared audiences. These shared audiences can be used in the different Adobe Experience Cloud applications that you use.</li></ul>|
|Advertising Cloud|Use the audience as targets.|

{style="table-layout:auto"}

>[!IMPORTANT]
>
>Once a visitor qualifies for the audience shared from Analytics, there is a 4-8 hour delay before that information is actionable in [!DNL Target], Ad Cloud, and Campaign Standard.

## More help - questions, guidance, and use cases {#section_C7F151644D8A45F7B6FC54F58845635D}

| Help with | Resource |
|--- |--- |
|Cannot find Audiences?|Ensure that you are provisioned. See [Getting started - enable your applications for core services](core-services.md).<br>Go [here](https://adobe.allegiancetech.com/cgi-bin/qwebcorporate.dll?idx=X8SVES) to request access to Profiles and Audiences (integrations provisioning form).|
|Use cases|For more guidance on what application to use, go to [Audience Creation Options](https://experienceleague.adobe.com/docs/experience-cloud-kcs/kbarticles/KA-16471.html?lang=en) in the Knowledge Base.|
|Forum|The [Audiences forum](https://experienceleaguecommunities.adobe.com/t5/Adobe-Experience-Cloud-Audiences/ct-p/experience-cloud-audiences-community) is another resource to get help with audiences.|

{style="table-layout:auto"}

## Audience Library interface elements {#section_D04ACEF61CEF4B189AE6BA9F40D0DBF4}

The [!DNL Experience Cloud] provides a library for creating and managing audiences, with native, real-time audience identification. 

**[!UICONTROL Experience Cloud]** > **[!UICONTROL Experience Platform]** > **[!UICONTROL People]** > **[!UICONTROL Audience Library]** 

![Add audience in Audience Library](assets/audience_library.png) 

| Element | Description |
|--- |--- |
|New|[Create an audience](audience-library.md).|
|Title & Description|A column heading that identifies and describes the audience.|
|Author|The person who created the audience segment.|
|Source|Identifies where the audience was created.<ul><li>**Analytics:** A segment created in Adobe Analytics, then [published to the Experience Cloud](audience-library.md).</li><li>**Experience Cloud:** A new audience [created in Experience Cloud Audiences](audience-library.md).</li><li>**Audience Manager:** Audiences created Audience Manager automatically display in the Experience Cloud Audiences.</li></ul>|
|Current Size|The current audience size.|
|Active|The active status of the segment.|

{style="table-layout:auto"}
