---
description: Publish an Analytics audience segment to the Experience Cloud and to Adobe Target, for audience marketing activities.
keywords: core services
seo-description: Publish an Analytics audience segment to the Experience Cloud and to Adobe Target, for audience marketing activities.
seo-title: Publish an Analytics audience segment
solution: Experience Cloud
title: Publish an Analytics audience segment
uuid: 1b371c1e-4ebc-408e-92b8-ee6f1cbccd5a
index: y
internal: n
snippet: y
translate: y
---

# Publish an Analytics audience segment


>1. In Analytics, [ build a segment](https://marketing.adobe.com/resources/help/en_US/analytics/segment/seg_build.html).
>1. On the Segment Builder, enable the **[!UICONTROL  Make this an Experience Cloud audience]** option.
>   ![](assets/ec_audience_example.png) 



><table id="table_1830C54F8B0C4FB094F30929DEAE01EB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Element </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Make this an Experience Cloud audience (for &lt;<i>report suite name</i>&gt;) </p> </td> 
   <td colname="col2"> <p> Publishes this segment to the Experience Cloud. You can use the audience for marketing activities in <span class="keyword"> Adobe Target</span> and segmentation in <span class="keyword"> Audience Manager</span>. </p> <p>The <span class="uicontrol"> Title</span> and <span class="uicontrol"> Description</span> fields are required for the segment to be published. </p> <p>When this option is enabled, the title and audience segment definition are shared, but actual data is not. When that audience is associated with an activity in <span class="keyword"> Target</span>, <span class="keyword"> Analytics</span> begins sending IDs for visitors that qualify for that <span class="keyword"> Experience Cloud</span> and <span class="keyword"> Target</span> audience. At that point, the audience name and corresponding data begins displaying on the <span class="wintitle"> Experience Cloud Audiences</span> page. </p> <p>Audiences shared to the <span class="keyword"> Experience Cloud</span> from <span class="keyword"> Analytics</span> cannot exceed 20 million audience members. </p> <p>Due to caching, deleted report suites in Analytics require 12 hours before the deletion is shown in the Experience Cloud. </p> <p>In <span class="keyword"> Analytics</span>, you can edit or delete a published segment. If the segment is in use, a warning message is issued when you edit a segment. You cannot delete a published segment that is in use by <span class="keyword"> Adobe Target</span>. </p> <p>Once a visitor qualifies for the audience shared from <span class="keyword"> Analytics</span>, there is a 24 - 48 hour delay before that information is actionable in <span class="keyword"> Target</span>, <span class="keyword"> Advertising Cloud</span>, and <span class="keyword"> Campaign</span>. </p> <p><b> Data Privacy</b> </p> <p>Audiences are not filtered based on the authentication state of a visitor. If a visitor can browse your site in un-authenticated and authenticated states, actions that occur when a visitor is un-authenticated can still cause a visitor to be included in an audience. Review <a href="https://marketing.adobe.com/resources/help/en_US/reference/?f=c_Privacy_Overview" format="https" scope="external"> Analytics Privacy Overview</a> to understand the full privacy implications of audience sharing. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Select the window for audience creation </p> </td> 
   <td colname="col2"> <p>Note that this is a <b>rolling</b> time window, not a fixed one. </p> </td> 
  </tr> 
 </tbody> 
</table>

>
>1. Click **[!UICONTROL  Save]**.
>1. Access [!DNL  Adobe Target], then navigate to the [!UICONTROL  Segment] list.
>1. On the [!UICONTROL  Segment] page, click **[!UICONTROL  Import Experience Cloud Audiences]**

>       This option displays the [!DNL  Analytics] segment for use in activities. 
