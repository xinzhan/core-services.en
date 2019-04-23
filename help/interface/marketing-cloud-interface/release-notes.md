---
description: Features, release notes, and known issues for the Experience Cloud interface.
keywords: core services
seo-description: Features, release notes, and known issues for the Experience Cloud interface.
seo-title: Cumulative release notes
solution: Experience Cloud
title: Cumulative release notes
uuid: fcff8cc6-e587-4bf2-9a75-261d4eabc7d4
---

# Cumulative release notes

Features, release notes, and known issues for the Experience Cloud interface.

For a list of documentation updates, see [Experience Cloud](../doc-updates.md#concept_4C8983FCD23848A4B1E4C2D99ED82784). 

For release notes covering all solutions, see [Experience Cloud Release Notes](https://marketing.adobe.com/resources/help/en_US/whatsnew/). 

## Release 19.1.1 - January 17 2019

* Fixed an issue preventing the help search from returning results. (MCUI-1670)
* Fixed and improved eVar management in Triggers. (MCUI-6400) 

## Release 16.5.1 - May 26 2016 {#section_3785F182BC13493F84903CA69EB6D0A8}

**Features and Improvements** 

<table id="table_ABBCE1A66F534059BD728BC2B9AEFA80"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Pre-configured product configurations in the Admin Console </p> </td> 
   <td colname="col2"> <p>Experience Cloud customer administrators can leverage product configurations that are pre-created and mapped to default permission groups for Analytics and Dynamic Tag Management. </p> <p>This optimization is available for newly provisioned organizations, and it reduces the amount of time required by organizations to manage users in the Admin Console. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Feed improvement </p> </td> 
   <td colname="col2"> <p> When creating a new post in the Experience Cloud Feed, the To line now uses the currently active topic instead using the organization by default.</p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes** 

* Fixed an issue preventing thumbnails from showing for assets shared from Assets on Demand to the Experience Cloud Feed. (MAC-29955) 

## Release 16.2 February 18 2016 {#section_D9610373116C4D77A38F67815C725EA3}

<table id="table_C9B288CF42034F329C3C72D95D22E515"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud Assets improvements </p> </td> 
   <td colname="col2"> <p>In Experience Cloud Assets, you can store, share, and synchronize your digital assets from one central location. Experience Cloud Assets leverages some of the features available in <span class="keyword"> Adobe Experience Manager</span> (AEM). </p> <p>See <a href="../experience-cloud-assets/experience-cloud-assets.md#concept_DDA5224C907D4A4F817D795DA0ED64D0" format="dita" scope="local"> Experience Cloud</a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Account linking improvements </p> </td> 
   <td colname="col2"> <p>Improved the interface workflow for linking solution accounts with the Experience Cloud (Adobe ID). This new workflow locates all the user's accounts associated with an organization, and lets you choose which account to link. We also streamlined the account linking experience, so that you no longer need to access the Manage Organizations page to manually link accounts. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes** 

* Fixed an issue preventing linking and SSO for Analytics. This issue displayed the "Notice: The error message: ERROR IMS SSO Failed: Unable to find linked company."

**Known Issue** 

If you access Dynamic Tag Management via the **[!UICONTROL Experience Cloud]** > **[!UICONTROL Activation]** interface, but your Dynamic Tag Management account is not linked to the Experience Cloud (Adobe ID), you will not be able to log in to Dynamic Tag Management. To avoid this issue, navigate directly to [!DNL dtm.adobe.com] in a new browser tab. 

## Release 16.1 - January 21 2016 {#section_33B3F7DF6CA347E3AA93801BAC6232CE}

<table id="table_4223658257DA41C999AC710A10D26771"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Audience Library messages </td> 
   <td colname="col2"> <p> We improved Audience Library to include helpful messages when building audiences or when a time-out occurs. </p> <p>For example, when adding more than five rules, a message displays indicating you exceeded maximum allowable rules. (MAC-27376, MAC-27375) </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Microsoft is [ending support](https://www.microsoft.com/en-us/WindowsForBusiness/End-of-IE-support) for Internet Explorer 8, 9, and 10. As such, we will not fix issues reported against these specific versions of Internet Explorer. 

## Release 15.10 - October 14 2015 {#section_68123833D3634BD3A473C12862BF9606}

**Known Issues** 

* Customers are not able to log into Report Builder if they SSO into Analytics via the Experience Cloud. This issue does not impact customers using legacy Analytics credentials.
* Known issue with the "Link to Report" function in Analytics. Customers logging into Analytics via the Experience Cloud are directed to a non-SSO login page for Analytics when trying to share a report.

## Release 15.9 - September 10 2015 {#section_BCCE3E7DF62A4FF5A57B9C8FE2A5F37B}

* Fixed an Audience Manager API performance issue causing intermittent timeouts when uploading customer attributes data. (MAC-26305)
* Fixed an issue that prevented users from adding up to 200 customer attributes to a subscription. (MAC-26188)
* Fixed an Audience Library issue that prevented audience sharing from Analytics segmentation. This issue caused "Collecting Data" (0 audiences) to display. To prevent this issue, Adobe recommends keeping the segment sizes under 50k audience members per segment. (MAC-25788)
* Fixed a previous known issue on the Customer attributes - Edit Schema page that was causing a Content Aware error that was issued when changing a display name. (MAC-25589, AN-103834)

## Release 15.7 - July 22 2015 {#section_2683A152176944E48EF6C943892975B7}

* Fixed an issue that prevented attribute descriptions specified on the View/Edit Schema page (in customer attributes) from being updated in Analytics reports. (MAC-25985)
* Fixed an issue preventing the thumbnails from rendering for uploaded assets. (MAC-25863)
* Fixed an issue that prevented new segments created in reports & analytics from being available in Experience Cloud Audiences. (MAC-25817)
* Fixed an issue that prevented audience sharing from Analytics, when using the visitor ID service. (MAC-25788, MAC-25747)
* Added support for multibyte characters in customer attributes. (MAC-25552)

**Known Issue** 

A known issue is causing duplicate auto-generated accounts to be created in Audience Manager, and automatically linking them to a user's Experience Cloud identity. This issue occurs if you attempt to navigate to Audience Manager before linking your accounts. Adobe recommends that you link your Audience Manager accounts to the Experience Cloud before navigating to Audience Manager. (MAC-25640) 

## Release 15.6.1 - June 11 2015 {#section_AD2019F8D2F84C9EB2B0533FAACF7043}

No information available

## Release 15.5.1 - May 13 2015 {#section_EF197410964E40D294D0D8024738CFBA}

<table id="table_14E7B35E06C84A258A21D09691B58354"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>The left navigation menus have been updated and arranged to provide access to all the core services and solutions. Notable changes include: </p> 
    <ul id="ul_5BEBAB86B9234A239C4E2DAF8826D8E3"> 
     <li id="li_7FA9F64CE69144B8A8A92746BF40E5A1">The <span class="term"> Audience Library</span> and <span class="term"> Customer Attributes</span> menu selections are now located under <span class="term"> Audiences</span>. </li> 
     <li id="li_95D62A43AE6243DBB2A65EDB830D05C4">The <span class="term"> Exchange</span> menu selection was moved from the Help drop-down menu to the left navigation rail. </li> 
     <li id="li_0443FD50C78446CD8AA27A4F272CAD31"> <span class="term"> Solutions</span> has been removed. You can launch all solutions from the bottom half of the navigation rail. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

* Fixed an issue preventing customer attributes from syncing for some customers.
* Fixed an issue preventing [Adobe Target Product Documentation](https://marketing.adobe.com/resources/help/ja_JP/target/a4t/) page from displaying in Japanese.
* Fixed an issue preventing the use of Japanese text in comments between the [!DNL Creative Cloud] and the [!DNL Experience Cloud].

## Release 15.4.1 - April 8 2015 {#section_75634120CC934B3381EDEA7F6F976F0A}

<table id="table_3A6FBAE36558425A803B078150862C92"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Administration improvements: </p> 
    <ul id="ul_7D5FCBEFA262435D865CA1018BFB792E"> 
     <li id="li_6E98974CCB094ABBAB57C51ED56C3F00"> <span class="wintitle"> Admin Console</span> </li> 
     <li id="li_8CDAB6301FD44C3999EE4EEB1A0A2FD6">Enterprise and federated ID support </li> 
    </ul> </td> 
   <td colname="col2"> <p>User and group management functionality has been moved to the Admin Console. The new navigation path is: </p> <p> <span class="uicontrol"> Experience Cloud</span> &gt; <span class="uicontrol"> Administration</span> &gt; <span class="uicontrol"> Launch Admin Console</span></p> <p> Also, support for enterprise and federated IDs has been added. You can use enterprise IDs, federated IDs, and Adobe IDs in the same enterprise deployment. For example, use Adobe IDs for users who may use other Adobe product and services. Use enterprise or federated IDs for users where you want to strictly manage their accounts. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes** 

* Fixed an issue preventing single sign-on between the [!DNL Experience Cloud] and [!DNL Media Optimizer].

**Known Issues** 

* Linking and unlinking your dynamic tag management organization with the Experience Cloud is not working for newly created Experience Cloud organizations. We are working to fix this and restore normal functionality with the May release. If you experience problems when trying to single-sign on into dynamic tag management via the Experience Cloud, use the legacy login at [!DNL dtm.adobe.com].
* A known issue is preventing audience sharing from report suites which are not owned by the linked Analytics account. Remedial efforts are underway

## Release 15.3.2 - March 19 2015 {#section_07760FD9CA43497FA8BDCCA990A24BFD}

<table id="table_54025DBE2D094FF1BE837BA60816C6DF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Customer Attributes </p> </td> 
   <td colname="col2"> <p>If you capture enterprise customer data in a customer relationship management (CRM) database, you can upload the data into a customer attribute data source in the Experience Cloud. After the data is uploaded, you can run <span class="uicontrol"> Visitor Profile</span> &gt; <span class="uicontrol"> Customer Attributes</span> reports in Analytics. </p> <p>You can also use the uploaded data as an audience segment in <span class="keyword"> Adobe Target</span>. </p> <p>See <a href="../attributes/attributes.md#concept_ACFEE7C8B8E94875BA0825CDF4913AF1" format="dita" scope="local"> Customer Attributes</a> product documentation. </p> <p> For information about modernizing your solutions for core services, see <a href="../core-services/core-services.md#concept_07ED1D5C64234E77976E6D572E78FB9C" format="dita" scope="local"> Enable your solutions for core services</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Release 15.3.1 - March 4 2015 {#section_57CB69C044DD47BDBC1A1BEC38957551}

<table id="table_EB3FFBA2DF904546A5185EC9A63BBA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Group Mapping </p> </td> 
   <td colname="col2"> <p>The Group Management page has been redesigned as an administrative interface that lets you create groups, add users to groups, and apply permissions across Experience Cloud solutions. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>One-to-many mapping </p> </td> 
   <td colname="col2"> <p>When linking solution accounts in the Experience Cloud, if you have multiple solutions and organizations, you can now map multiple products and services to a single organization. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Activation </p> </td> 
   <td colname="col2"> <p> <a href="../activation/activation.md#concept_EE756B6B0A0643DAB8CA3A00E665406C" format="dita" scope="local"> Activation</a> now displays in the left navigation in the <span class="keyword"> Experience Cloud</span>. <span class="wintitle"> Activation</span> is a <span class="keyword"> Experience Cloud</span> core service currently comprised of the dynamic tag management technology, and directs you there when clicked. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Documentation Updates - Core Services </p> </td> 
   <td colname="col2"> <p>Added the topic <a href="../core-services/core-services.md#concept_07ED1D5C64234E77976E6D572E78FB9C" format="dita" scope="local"> Enable your solutions for core services</a> to assist you with implementing core services. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Release 15.2.1 - February 19 2015 {#section_BC694D5AE16A4E16B44B353ED67947F3}

Fixes: 

* Improved the user email invitation workflow for account provisioning.
* Fixed an asset folder issue preventing [!DNL Experience Cloud] and [!DNL Adobe Campaign] assets from displaying identical folder hierarchies.
* Fixed an issue preventing the deletion of audiences that were part of deactivated [!DNL Target] activities.
* Fixed an issue preventing the Add (plus) icon from displaying under [!UICONTROL Rules] on the [!UICONTROL Create New Audience] page.
* Improved Experience Cloud interface support for Internet Explorer 9.

## Release 15.1.1 - January 15 2015 {#section_F1A352E928AF432E94CC0A289C345184}

New features and fixes in the [!DNL Adobe Experience Cloud] collaboration and sharing interface. 

<table id="table_AD0A8CA760E64227BB04BA6B0E425E80"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Read-only access. </p> </td> 
   <td colname="col2"> <p>Administrators can now grant non-administrative users read-only access. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes** 

* Fixed an issue in which PNG files could not be rendered on a card.
* Fixed an issue with uploading files to Experience Cloud Assets via drag and drop.

**Known Issues** 

* Users are not able to share PowerPoint files on boards.
* Group and entitlement changes made in User Management take effect only after a new login.
* Some users might have issues uploading large file-types to Experience Cloud Assets.
* Users might be missing links on their Experience Cloud cards from Media Optimizer.
* Some administrative users might experience issues linking their accounts after accepting an invitation to join the Experience Cloud.
* Experience Cloud interface can reduce in performance when in parallel use by multiple users.
* Some users are able to delete an out-of-date asset instead of receiving an error notification.
* Some users might experience issues when logging into two browsers with the same Adobe ID simultaneously.
* Some users might be unable to re-add a Creative Cloud user to a shared folder after the Creative Cloud user has been deleted.
* Some users might experience a delay in the notification that occurs when a folder is shared from the Experience Cloud to Creative Cloud.
* Some users might experience an issue sharing a folder between the Experience Cloud and Creative Cloud.
* Some users may have trouble creating an audience within an Analytics report suite after shared audiences have been enabled.
* Some users may have trouble uploading assets to a board.

## Release 14.11.1 - November 13 2014 {#section_A6CF1D4F27B9496892A89C983EB39102}

Known issues: 

* Some users are able to delete an out-of-date asset instead of receiving an error notification.
* Some [!DNL .png] files cannot be rendered on a card.
* Some users may have trouble uploading assets to a board.
* Group and entitlement changes made in user management only take effect after a new login.
* Admins must log out and back in to see changes made in Account Settings.
* User are not able to share PowerPoint files on boards.
* [!DNL Experience Cloud] interface can reduce in performance when in parallel use by many users.
* Adobe Experience Manager to Creative Cloud synchronization is not working.

## Release 14.10.1 - October 16 2014 {#section_E3A0F4423B814707AA3745E083500835}

New features and fixes in the [!DNL Adobe Experience Cloud] collaboration and sharing interface. 

<table id="table_7C1ACE8108D54782AE128ACD35069DF5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Edit User Permissions </p> </td> 
   <td colname="col2"> <p>Owners of a board can now edit user permissions on the particular board. </p> <p> 
     <ol id="ol_B12251C510744538AF9BCE60ACB04016"> 
      <li id="li_87B3EDE9542B47CEBE0BE7F2D1DE844D">On the board, click <span class="uicontrol"> Settings</span>. </li> 
      <li id="li_0F4786B0E1E743069D082E7DC488A031">Next to each owner, specify <span class="uicontrol"> Owner</span>, <span class="uicontrol"> Viewer</span>, or <span class="uicontrol"> Editor</span>. </li> 
     </ol> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes** 

* Creating a card from a PDF and sharing it to the board was returning an error message.

**Known Issues** 

* Some users may have trouble uploading assets to a board.
* Some [!DNL .png] files cannot be rendered on a card.
* Group and entitlement changes made in user management only take effect after a new login.
* Some users may not be able to create a card from a PDF and share it to a board.
* Some users are able to delete an out-of-date asset instead of receiving an error notification.
* User are not able to share PowerPoint files on boards.
* [!DNL Experience Cloud] interface can reduce in performance when in parallel use by many users.
* The [!DNL Search&Promote] linking is not available from the [!UICONTROL Organizations & Product Access] page.

## Release 14.9.1 - September 18 2014 {#section_20F156A9CC2F4FC59C4970075C181D3A}

**Fixes and Improvements** 

* When you navigate to [!DNL marketing.adobe.com], the login experience is now consistent with Adobe's Creative Cloud login.
* On the Manage Organizations page, the linking experience (after an invite is received) is now consistent for each solution.

**Known Issues** 

* Group and entitlement changes made in user management only take effect after a new login.
* Some users may not be able to create a card from a PDF and share it to a board.
* Some users may have trouble uploading assets to a board.
* Some users are able to delete an out-of-date asset instead of receiving an error notification.
* User are not able to share PowerPoint files on boards.
* Some [!DNL .png] files cannot be rendered on a card.
* [!DNL Experience Cloud] interface can reduce in performance when in parallel use by many users.
* The [!DNL Search&Promote] linking is not available from the [!UICONTROL Organizations & Product Access] page.
* Some users may experience their [!DNL Creative Cloud] contents being removed from their folder, if the content is unshared in the [!DNL Experience Cloud].

## Release 14.8.1 - August 21 2014 {#section_03BF00F6A95A490C91BCC0A1988FA7AA}

New features and fixes in the [!DNL Adobe Experience Cloud] collaboration and sharing interface. 

<table id="table_1E7DBEB5E83B4E4285B6FD1D718CD16D"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>You can now access <span class="keyword"> Adobe Mobile Services</span> from the left-hand navigation. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Known Issues** 

* Group and entitlement changes made in user management only take effect after a new login.
* Some users may not be able to create a card from a PDF and share it to a board.
* Some users may have trouble uploading assets to a board.
* Some users may not be able to log in from [!DNL Target] to [!DNL Experience Cloud].
* Some Audience Manager users cannot log into the [!DNL Experience Cloud].
* Some users are able to delete an out-of-date asset instead of receiving an error notification.
* Files deleted from [!DNL Experience Cloud] are not being deleted from [!DNL Digital Asset Management].
* User are not able to share PowerPoint files on boards.
* Some [!DNL .png] files cannot be rendered on a card.
* [!DNL Experience Cloud] interface can reduce in performance when in parallel use by many users.
* The [!DNL Search&Promote] linking is not available from the [!UICONTROL Organizations & Product Access] page.
* Some users may experience their [!DNL Creative Cloud] contents being removed from their folder, if the content is unshared in the [!DNL Experience Cloud].

## Release 14.7.1 - July 24 2014 {#section_B22D4F830756463DB27BB4D508D9ADD5}

New features and fixes in the [!DNL Adobe Experience Cloud] collaboration and sharing interface. 

**Known Issues** 

* Files deleted from [!DNL Experience Cloud] are not being deleted from [!DNL Digital Asset Management].
* Some [!UICONTROL Exchange] users may find their names in the comments to be a long string ID instead of their names
* Some [!DNL .png] files cannot be rendered on a card
* Uploading files allows more file types than the drag-and-drop method. For best results, upload using [!UICONTROL Assets].
* The [!DNL Search&Promote] linking is not available from the [!UICONTROL Organizations & Product Access] page.
* [!DNL Exchange] users must clear their cookies to improve their experience.
* [!DNL Experience Cloud] interface can slow down when in parallel use by many users.
* Some users may experience their [!DNL Creative Cloud] contents being removed from their folder if the content is unshared in the [!DNL Experience Cloud].
* You will be logged out after 15 minutes of inactivity. Also, logging out in one location will log you out of the [!DNL Experience Cloud].
* Some users may not be able to link their Audience Manager accounts to [!DNL Experience Cloud].
* [!UICONTROL Exchange] users can only see English in language selector.

**Fixes** 

None to report. 

## Release 14.6.1 - June 19 2014 {#marketing_cloud_interface}

New features and fixes in the [!DNL Adobe Experience Cloud] collaboration and sharing interface. 

**Improvement** 

<table id="table_C9BD63436BF0414B97B8D07387D1993B"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="wintitle"> Save</span> button in Audiences </p> </td> 
   <td colname="col2"> <p>When you create an audience, the <span class="wintitle"> Save</span> button on the <span class="wintitle"> Create New Audience</span> page is now disabled until all the required fields are completed. 
     <!--MAC-19712 --></p> </td> 
  </tr> 
 </tbody> 
</table>

**Known Issues** 

* Files deleted from [!DNL Experience Cloud] are not being deleted from [!DNL Digital Asset Management].
* Uploading files allows more file types than the drag-and-drop method. For best results, upload using Assets.
* The [!DNL Search&Promote] linking is not available from the [!UICONTROL Organizations & Product Access] page.
* Filters applied to trended reports from [!DNL Analytics] are not applied to cards in the [!DNL Experience Cloud].
* Some users are not able to link their audience management account with their [!DNL Experience Cloud] account.
* You will be logged out after 15 minutes of inactivity. Also, logging out in one location will log you out of the Experience Cloud.
* Some Exchange users may find their names in the comments to be a long string ID instead of their names

**Fixes** 

* Fixed an issue preventing video upload to apps.

## Release 14.5.1 - May 22 2014 {#section_7E22B2CB3ABA4D6EAED8CA8EFDE5433E}

<table id="table_4E4B34EEE3D94D78BA1A1FBC62950559"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud Exchange </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Experience Cloud</span> &gt; <span class="uicontrol"> Help</span> &gt; <span class="uicontrol"> Exchange</span></p> <p>The <span class="keyword"> Experience Cloud</span><span class="wintitle"> Exchange</span> is a single destination where you can search, browse, select, pay, and download digital marketing extensions via apps. </p> <p>Apps include data connectors, custom configurations to Adobe's core product, 3rd party applications, reports, and <span class="keyword"> Experience Cloud</span> cards. </p> <p>See <a href="../exchange.md#concept_E07F16F070544B82B56527A845C41D59" format="dita" scope="local"> Exchange Marketplace</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Experience Cloud Audiences </p> </td> 
   <td colname="col2"> <p> <span class="uicontrol"> Experience Cloud</span> &gt; <span class="uicontrol"> Audiences</span></p> <p> <span class="wintitle"> Audiences</span> is where you create, edit, and manage audiences, similar to how you work with segments. For example, you can create a segment in reports and analytics, then share it to <span class="wintitle"> Experience Cloud</span><span class="wintitle"> Audiences</span>. Once shared, the audience is available in <span class="keyword"> Adobe Target</span> for campaign activities, and in Adobe Audience Manager for segmentation. </p> <p> <p>Note: To request enablement in Target, visit <a href="https://www.adobe.com/go/audiences" format="http" scope="external"> https://www.adobe.com/go/audiences</a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>Users who are mentioned on <span class="keyword"> Experience Cloud</span> cards now have permissions to that card. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> </p> </td> 
   <td colname="col2"> <p>New Adobe users can link their Scene7 accounts to Adobe ID as well as their team members. Administrators can unlink users from Scene7 accounts as well. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Asset synchronization. </p> </td> 
   <td colname="col2"> <p> You can share assets within Adobe Experience Manager (AEM) Assets with Adobe Experience Cloud and Adobe Creative Cloud such that any changes to these assets are reflected in the shared copies of the assets in Adobe Experience Cloud and Adobe Creative Cloud. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes** 

* [!DNL Experience Cloud] was not linking to [!DNL Adobe Target]. This issue occurred if the [!DNL Adobe Target] login can be used on multiple [!DNL Target] servers.
* [!DNL Adobe Media Optimizer] was not creating users automatically when the user has been created in [!DNL Experience Cloud].
* Options in combo boxes used for adding new users temporarily disappeared while typing.
* The Comments link on asset card view was not clickable.
* After adding a custom tag to an asset, no other metadata changes were not persisting.
* Deleting an image, Assets does not warn if the image is used in Adobe Target Essentials.
* Slow [!UICONTROL Experience Cloud] interface performance when in parallel use by many users.
* Deleting an image in [!UICONTROL Experience Cloud Assets] was not issuing a warning if the image was used in [!DNL Adobe Target Essentials].
* When **[!UICONTROL remember me]** was not selected during login, the user was logged out after 15 minutes.
* Users were having to log out and back in for all permission and entitlement changes to take effect.
* Logging in to the [!DNL Experience Cloud] was taking longer than a second.
* For certain users, deleting files from the [!DNL Experience Cloud] did not synchronizing with [!DNL Digital Asset Management].
* Users were being logged out after only 15 minutes of browser inactivity.
* User were not able to share PowerPoint files on boards.
* Some users were experiencing poor visual layout in Internet Explorer 10 than other browsers.

## Release 14.4.1 - April 22 2014 {#section_E2A699764E744D2E8D418E9A3D40AF6B}

<table id="table_D95C0DC64F2A4B47BAC83E504CFD6825"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Create cards from help topics </p> </td> 
   <td colname="col2"> <p>After you enable the Share to Adobe Experience Cloud feature in your browser's Bookmark toolbar, you can now share help pages from the microsite URL. </p> <p> <b>To share a help topic</b> </p> 
    <ol id="ol_F94B816121494B0FA16CC07B0E96AED8"> 
     <li id="li_F47187D4B5FE46D3A51D257DD569B4D6"> <p>In the <span class="keyword"> Experience Cloud</span>, click <span class="uicontrol"> Administration</span>. </p> </li> 
     <li id="li_94EF58E7A4974B63951E14F72A710183"> <p>Drag the <span class="uicontrol"> Share to Adobe Experience Cloud</span> button to your Bookmark toolbar. </p> </li> 
     <li id="li_69EEC4F25D8F4AD7AA106A10B7F50FF6"> <p>Navigate to a help page (or remain on this one), then click <span class="uicontrol"> Share to Adobe Experience Cloud</span> in your browser's Bookmarks toolbar. </p> <p>This step creates a card, which you can view in the <span class="wintitle"> Experience Cloud</span>. </p> </li> 
    </ol> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes**

* After adding a custom tag to an asset, no other metadata changes can be persisted.
* Users have to refresh the board to make the deleted cards disappear from view.
* When **[!UICONTROL Remember me]** is not selected during login, the user is logged out after 15 minutes
* [!DNL Analytics] solution landing page shows formatting errors.
* Users must log out and log back in for all permission and entitlement changes to take effect.
* Deleting an image, [!UICONTROL Assets] does not warn if the image is used in [!DNL Adobe Target Essentials].
* Comments link on asset card view is not clickable.
* Options in combo boxes for adding new users temporarily disappear while typing.
* Logging in to the [!DNL Experience Cloud] takes longer than a second.
* Data shared from [!DNL Media Optimizer] is misrepresented in the [!DNL Experience Cloud].
* Adobe [!DNL Media Optimizer] does not create users automatically when user has been created in the [!DNL Experience Cloud].
* The [!DNL Experience Cloud] cannot be linked to [!DNL Adobe Target], if the [!DNL Adobe Target] login can be used on multiple [!DNL Target] servers.
* [!DNL Experience Cloud] interface can slow down when in parallel use by many users.
* [!DNL Search&Promote] linking is not available from the [!UICONTROL Organizations & Product Access] page.
* [!DNL Adobe Media Optimizer] simulation cards are not rendering correctly.
* Filters applied to trended reports from [!DNL Analytics] are not applied to cards in [!DNL Experience Cloud].
* Filters applied to trended reports from Analytics are not applied to cards in Experience Cloud.
* Some Excel or CSV files cannot be uploaded to a board.
* Some users may not be able to link their audience management account with their [!DNL Experience Cloud].
* Some users may experience error when sharing [!DNL Analytics] segments in the [!DNL Experience Cloud].
* Some users may not be able to drill down to subfolders in [!UICONTROL Asset Selector].
* Some users are not able to share AdLens gadgets in the [!DNL Experience Cloud].

## Release 14.3.1 - March 13 2014 {#section_5D142E3225E3477A84DC01B8197D39BC}

Version 14.3.1 is a maintenance release that focuses on speed, stability and security. It does not include major new features. 

**Fixes** 

* Added the ability to remove your avatar image.
* Fixed an issue preventing you from unlinking your [!DNL Adobe Media Optimizer] accounts.

**Known Issues** 

* Deleting an image in Experience Cloud Assets does not warn if the image is used in Adobe Target Essentials.
* Refreshing a card from [!DNL Analytics] can sometimes lead to an empty chart in the expanded card.
* Users must log out and log back in for all permission and entitlement changes to take effect.
* When *`Remember me`* is not selected during login, the user will be logged out after 15 minutes.
* [!DNL Analytics] solution landing page shows formatting errors.
* The Comments link on asset card view is not clickable.
* Experience Cloud interface can slow down when in parallel use by many users
* Experience Cloud cannot be linked to [!DNL Adobe Target], if the [!DNL Adobe Target] login can be used on multiple Target servers.
* Logging in to Experience Cloud takes longer than a second.
* After adding a custom tag to an asset, no other metadata changes can be persisted.
* [!DNL Adobe Media Optimizer] does not create users automatically when user has been created in Experience Cloud.
* Options in combo boxes for adding new users temporarily disappear while typing.
* Data shared from [!DNL Media Optimizer] is mis-represented in Experience Cloud.
* Sharing Flickr images fails.
* Filters applied to trended reports from [!DNL Analytics] are not applied to cards in Experience Cloud.
* Group and entitlement changes made in user management only take effect after a new login.
* [!DNL Search&Promote] linking is not available from [!UICONTROL Organizations & Product Access].
* User have to refresh the board to make the deleted cards disappear from view.
* Some Excel or CSV files cannot be uploaded to a board.
* [!DNL Adobe Media Optimizer] simulation cards are not rendering correctly.
* Some PNG files cannot be rendered on a card.
* Beta feedback cannot be submitted.

## Release 14.2.1 - February 24 2014 {#section_5AD81B0737C843AFB4BE9C4420D70EB3}

<table id="table_DFAB002358C94A17A7F91DAB323A488F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Feature </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>OEmbed </p> </td> 
   <td colname="col2"> <p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Refresh Data </p> </td> 
   <td colname="col2"> <p> 
     <!--MAC-18174-->The <span class="uicontrol"> Refresh Data</span> icon for a graph on a card is now hidden if the solution does not allow a data refresh. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Fixes** 

* Fixed an issue that prevented shared [!DNL Analytics] reports from applying segment filters.
* Fixed an issue causing solutions to display on the [!UICONTROL Experience Cloud Solutions] page as linked, even if the solutions accounts were not linked.
* Fixed an issue that prevented [!DNL Adobe Target] customers in Asia from being able to click the **[!UICONTROL Continue to Experience Cloud]** button on the linking page.
* Fixed an issue that prevented the sharing of YouTube videos.
