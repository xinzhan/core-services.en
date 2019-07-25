---
description: Publish an Analytics audience segment to the Experience Cloud and to Adobe Target, for audience marketing activities.
keywords: core services
seo-description: Publish an Analytics audience segment to the Experience Cloud and to Adobe Target, for audience marketing activities.
seo-title: Publish an Analytics audience segment
solution: Experience Cloud
title: Publish an Analytics audience segment
uuid: 4201dc22-4b79-457c-a614-949bba087617
---

# Publish an Analytics audience segment

Publish an Analytics audience segment to the Experience Cloud and to Adobe Target, for audience marketing activities.

1.  In Analytics, [build a segment](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html).
1.  On the Segment Builder, enable the **[!UICONTROL Publish this segment to the Experience Cloud]** option.

    ![](assets/ec_audience_example.png) 

    | Element | Description |
    |--- |---|
    |Publish this segment to the Experience Cloud (for &lt;report suite name&gt;)|Publishes this segment to the Experience Cloud. You can use the audience for marketing and segmentation activities in Adobe Target, Audience Manager, Advertising Cloud, Campaign, and Audience Analytics.<br>The Title and Description fields are required for the segment to be published.<br>When this option is enabled, the title and audience segment definition are shared, but actual data is not. When that audience is associated with an activity in Target, Analytics begins sending IDs for visitors that qualify for that Experience Cloud and Target audience. At that point, the audience name and corresponding data begins displaying on the  Experience Cloud Audiences page.<br>Audiences shared to the Experience Cloud from Analytics cannot exceed 20 million audience members.<br>Due to caching, deleted report suites in Analytics require 12 hours before the deletion is shown in the Experience Cloud.<br>To delete a segment that has been published to the Experience Cloud, you have to unpublish it first. To unpublish a segment, just **unclick** the checkbox that you used to publish it. You **cannot** unpublish a segment that is currently in use by any of the following Adobe solutions: [!DNL Analytics] (in [!DNL Audience Analytics]), [!DNL Campaign], [!DNL Advertising Cloud] (for [!DNL Core Service] & [!DNL Audience Manager] customers) and all other external partners (for [!DNL Audience Manager] customers). You **can** unpublish a segment that is in use by [!DNL Target].<br>Once a visitor qualifies for the audience shared from  Analytics, there is a 24 - 48 hour delay before that information is actionable in Target, Advertising Cloud, and Campaign.<br>**Data Privacy**<br>Audiences are not filtered based on the authentication state of a visitor. If a visitor can browse your site in un-authenticated and authenticated states, actions that occur when a visitor is un-authenticated can still cause a visitor to be included in an audience. Review [Analytics Privacy Overview](https://marketing.adobe.com/resources/help/en_US/reference/?f=c_Privacy_Overview) to understand the full privacy implications of audience sharing.|
    |Select the window for audience creation|Note that this is a **rolling** time window, not a fixed one.|

1.  Click **[!UICONTROL Save]**.
1.  Access [!DNL Adobe Target], click [!UICONTROL Audiences].
1.  On the [!UICONTROL Audiences] page, locate the audience sourced from the Experience Cloud.

    These audiences are available for use in activities. 
