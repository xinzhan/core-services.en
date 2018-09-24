---
description: FAQ and best practices for customer attributes in Analytics and Target.
keywords: customer attributes
seo-description: FAQ and best practices for customer attributes in Analytics and Target.
seo-title: Frequently asked questions, limitations, and best practices
solution: Experience Cloud
title: Frequently asked questions, limitations, and best practices
uuid: e93eb531-23c7-4d75-92e8-75699f58546a
index: y
internal: n
snippet: y
translate: y
---

# Frequently asked questions, limitations, and best practices

FAQ and best practices for customer attributes in Analytics and Target.


## Best practices and limitations {#section_7F5189B3DAA84EE6865B91D2026EE05A}

Guidance and limitations when using Customer Attributes. 

<table id="table_0F2D0988F8574B3DA732A25B58405DCA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Issue </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Customer Attribute Subscription Limitations </p> </td> 
   <td colname="col2"> <p>When you upgrade to Analytics Premium, there is a 24-hour delay before additional attributes are available. You may see an <b>Attribute Subscription Max</b> error issued during this delay. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Custom Analytics ID (s.visitorID) </p> </td> 
   <td colname="col2"> <p>Setting a customer ID using <span class="varname"> s.visitorID</span> is a method of identifying users in Analytics. However, integrations in which Analytics data is exported or imported using the ID Service will not function when a visitor is identified using <span class="varname"> s.visitorID</span>. </p> <p>This includes, but is not limited to, shared audiences, Analytics for Target (A4T), and Customer Attributes. </p> <p>For these integrations, setting a custom Analytics ID is not supported. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Character length limitations in Analytics </p> </td> 
   <td colname="col2"> <p>When creating an Analytics subscription, field lengths for the uploaded files are truncated to 255. </p> </td> 
  </tr> 
 </tbody> 
</table>


## FAQ about customer attributes {#section_E47866EEA83348E09FE43CEC5E44C461}


<table id="table_88631069013B408EBB0A810657662B36"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Question </th> 
   <th colname="col2" class="entry"> Answer </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Can I receive notifications about upload status for customer attributes? </p> </td> 
   <td colname="col2"> <p>Yes. See <a href="../admin-getting-started/organizations.md#concept_0105453AD71847B8BFCAF4A40915F157" format="dita" scope="local"> Manage notifications</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> What should I do to get started with customer attributes? </p> </td> 
   <td colname="col2"> 
    <ol id="ol_1FACEF0990B6486B8DE86245D17695A8"> 
     <li id="li_F0C1542853684F8591FDC1B441D31A56"> <p>Get provisioned. </p> <p>If you are an <b>Analytics</b> customer, Adobe is provisioning you for customer attributes. If you use only <b>Target</b> and do not have Analytics, you must request provisioning for core services by contacting Customer Care. </p> </li> 
     <li id="li_444FEDEE4B7244F79BA847662F5B17CB"> <p>Have a conversation with your CRM team. Find out what kind of customer data is available that would be interesting for use in Analytics and throughout the Experience Cloud. </p> </li> 
     <li id="li_32D4AAF8C29748A78801A0E1BFB37AF5"> <p>Implement core services. </p> <p>See <a href="../core-services/core-services.md#concept_07ED1D5C64234E77976E6D572E78FB9C" format="dita" scope="local"> Getting started - enable your solutions for core services</a> for steps on how to modernize your implementation for core services. (See the section about synching customer IDs for important information.) </p> </li> 
    </ol> <p> <b>Note:</b> An administrator's FAQ for implementing core services is available <a href="../admin-getting-started/faq.md#concept_13219B4E51784577B6FF78AAA203DE91" format="dita" scope="local"> here</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> How many customer attributes am I allowed to use? </p> </td> 
   <td colname="col2"> <p>You can upload hundreds of <span class="filepath"> .csv</span> columns to the customer attribute service. However, when configuring subscriptions and selecting attributes, the following limits apply depending on the solutions you own: </p> <p> 
     <ul id="ul_2BB85067918D4BB3B59394F3E3E37A6D"> 
      <li id="li_93703988B9934384B4B94A839D028380"> <b>Analytics Standard</b>: 3 total </li> 
      <li id="li_D1E5E7BD24C54591B14D15DE97447835"> <b>Analytics Premium</b>: 200 per report suite </li> 
      <li id="li_8C891FE3D1EF49FA9F81E2E32CD0B9CA"> <b>Target Standard:</b> 5 </li> 
      <li id="li_2B66D43023F34EA685CE2C38A9250CEA"> <b>Target Premium:</b> 200 </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Is migrating to the Experience Cloud ID Service required? </p> </td> 
   <td colname="col2"> <p>Migration depends on the solutions you use. </p> <p> 
     <ul id="ul_9C473434B5DA4C6299AAB209DEDFCDE7"> 
      <li id="li_8BC10EB2825F4ADF8CA61F71D4994A28"> <b>Adobe Analytics</b>: Strongly recommended </li> 
      <li id="li_56F518E3F3DF4C93B6F7EF3B40ACC52F"> <b>Adobe Target:</b> Required. </li> 
     </ul> </p> <p>Using the ID service enhances the functionality opens the doors to using the latest Experience Cloud functionality, including real-time audiences, the Target modernization, Analytics integration, and video heartbeat tracking. </p> <p>For more details see <a href="../core-services/core-services.md#concept_07ED1D5C64234E77976E6D572E78FB9C" format="dita" scope="local"> Core Services - How to Enable Your Solutions</a>. </p> <p> <b>Note</b>: The <span class="term"> Experience Cloud ID service</span> is the modernized implementation of what is formerly known as the <span class="term"> Analytics visitor ID service</span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>How does the customer attribute functionality relate to Adobe Audience Manager? </p> </td> 
   <td colname="col2"> <p>While Audience Manager can receive data to perform audience identification, it cannot perform analytics functionality that ties attributes to historical behavioral data or provide the reporting, analysis, and segmentation capabilities that are available in Adobe Analytics. The People core service enables rich data from across solutions to be tied together and associated with a single ID for use across the Experience Cloud. </p> <p> In Adobe Target, customer attributes appear as individual attributes that can be combined with other rules to build audiences. Audiences shared in the People core service are full audiences that cannot be modified. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>(Analytics only) </b>How is this functionality different from what is provided in Analytics premium? </p> </td> 
   <td colname="col2"> <p>In the past, customers interested in combining customer attribute data with Analytics data have relied heavily on the data workbench tool for this functionality. Customer attributes exposes this functionality to a wider audience by providing customer attributes as dimensions and metrics in reports &amp; analytics, ad hoc analysis, and report builder. Analytics Standard customers will have access to customer attributes, but with limited capabilities. The full capability is available to Analytics Premium customers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>(Target Only)</b> Can I pre-load or upload data for customers that Target has never seen? </p> </td> 
   <td colname="col2"> <p> Yes. When the visitor makes their first request to Target, the system will fetch the existing information we have about them from Customer Attributes and use that data for targeting. </p> <p> <p>Note:  Retrieving this data can take up to 20 min from the visitor's first interaction with Target. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>(Target Only)</b> Can I create a super audience by combining customer attribute data with shared audience data? </p> </td> 
   <td colname="col2"> <p>No. Shared audience data is a completed audience. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>(Target only) </b>How does the customer attributes functionality compare to Target's bulk profile API? </p> </td> 
   <td colname="col2"> <p> The <a href="https://marketing.adobe.com/developer/documentation/test-target/r-profile-update" format="https" scope="external"> bulk profile API</a> enables Target profiles to be updated directly via the API, either for an individual profile or in bulk. The capability is similar to customer attributes, with the following key differences: </p> 
    <ul id="ul_5AAA4A8497C04F50A8AAA9F776BB868E"> 
     <li id="li_B20AEA397F3B4C86A1140CDA61ABD575">The profile API is a REST API call and customer attributes uses FTP. </li> 
     <li id="li_7FBE428EF5D34B6AA09B6368E8210344">Target's profile API only sends data to Target instead of to the whole Experience Cloud. </li> 
     <li id="li_CBB4D3FAF53944E0A066A4AD9F9C8760">Customer attributes provides a simple interface to create and manage this external data. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>(Target only)</b> Does uploading data from customer attributes to Adobe Target extend the Target visitor's profile lifetime? </p> </td> 
   <td colname="col2"> <p>Yes. See <a href="https://marketing.adobe.com/resources/help/en_US/target/ov/?f=c_visitor_profile_lifetime" format="https" scope="external"> Visitor Profile Lifetime</a> in Adobe Target Help. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> (Target only)</b> Can I target on the data uploaded in customer attributes immediately after the visitor is identified by the customer ID? </p> </td> 
   <td colname="col2"> <p>Yes. </p> <p>On the server call to Target, which includes the mbox third-party ID, all customer attribute data will be available. </p> </td> 
  </tr> 
 </tbody> 
</table>

