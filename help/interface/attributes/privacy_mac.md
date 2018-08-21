---
description: Considerations and best practices regarding personally identifiable information (PII) uploaded and used in the Adobe Experience Cloud.
keywords: customer attributes;core services
seo-description: Considerations and best practices regarding personally identifiable information (PII) uploaded and used in the Adobe Experience Cloud.
seo-title: Privacy considerations - customer attributes
solution: Experience Cloud
title: Privacy considerations - customer attributes
uuid: c4279cc9-9b9c-45be-8e2f-c5ea174511eb
index: y
internal: n
snippet: y
translate: y
---

# Privacy considerations - customer attributes


<!-- <p>https://wiki.corp.adobe.com/display/omtrplatform/Visitor+Enrichment+and+privacy#VisitorEnrichmentandprivacy-INFORMATIONASSOCIATIONOPTIONS </p> -->


* First and last name
* Home or other physical address
* Email address
* Telephone number
* Social Security Number
* Other identifier that permits physical or online contacting of an individual. (Varies by location. Please verify and comply with local laws and regulations related to privacy and PII for all the places where you do business.)
Adobe provides tools that allow advertisers to collect behavioral information about consumers that visit their sites or use their applications. Adobe also provides tools allow advertisers to enhance this information with offline or external customer records that the advertiser may have within other information management systems. 

One common reason advertisers do this is to improve the information available when making consumer-appropriate marketing and advertising decisions. Adobe Analytics and Target allow advertisers to upload personally identifiable information (PII), such as email addresses, only after it has been hashed to make it impossible to use for contacting the individual. Hashed information can still be used for analysis and for marketing purposes. As a reminder, Adobe prohibits advertisers from sending sensitive personal information to Adobe, such as medical records, financial account information, and information about minors. 

Adobe realizes that these types of marketing and advertising decisions may have consumer privacy implications, which is why Adobe has built in privacy controls to help advertisers meet their consumers' expectations. Adobe recommends its advertisers carefully consider which information is appropriate to use for marketing purposes and in which circumstances the advertiser has permission to use such information. 

**Best practices** 

When uploading PII to Adobe Analytics or Target, Adobe recommends that the customer hashes PII prior to uploading it to Adobe. Hashed information can still be used for analysis and for marketing purposes. As a reminder, Adobe prohibits advertisers from sending sensitive personal information to Adobe Analytics and Target, such as medical records, financial account information, and information about minors. 

Adobe recommends its advertisers carefully consider which information is appropriate to use for marketing purposes and in which circumstances the advertiser has permission to use such information. 

As consumer privacy law remains in flux, Adobe recommends that advertisers respect three common tenets: 

1. Do what you say (in your privacy policy).
1. Say what you do (in your privacy policy).
1. Do not surprise your consumers.
With these expectations in mind, Adobe recommends that when an advertiser associates browsing activities to PII, the advertiser provides notices or personalization indicating that the consumer is authenticated. An example of this is including a greeting within the header of the website. Adobe also recommends that advertisers describe in its privacy policy what type of browsing information it associates with PII and under what circumstances browsing information is associated with PII. Lastly, Adobe strongly recommends advertisers review the opt-out choices they provide their consumers to understand whether and how they can use unauthenticated profile information post opt out. 

<!-- <p> <b>Vinay Geol</b> should help craft privacy regarding how all MAC uses privacy/cookies. Privacy implications around each part of the workflow. Moving from CRM to MAC. Can it include PII? What is PII? What isn't PII? </p> 
<p>CRM data is Known Data or Info. Going to combine with activity that occurs when visitor was not authenticated. PII wiki: </p> 
<p>https://wiki.corp.adobe.com/display/omtrplatform/Visitor+Enrichment+and+privacy#VisitorEnrichmentandprivacy-INFORMATIONASSOCIATIONOPTIONS </p> 
<p>Refactoring of implementation docs as it relates to privacy and cookies. </p> 
<p>Add content to https://marketing.adobe.com/resources/help/en_US/mcloud/t_publish_audience_segment.html, as follows: </p> 
<p> Audiences are not filtered based on the authentication state of a visitor. If a visitor can browse your site in un-authenticated and authenticated states, actions that occur when a visitor is un-authenticated can still cause a visitor to be included in an audience. Please review &amp;lt;link&amp;gt; to understand the full privacy implications of audience sharing. </p> 
<p>That "link" goes to a topic dedicated to PII, with this text: </p> 
<p> - Adobe Analytics allows its advertisers to upload personally identifiable information (PII) such as email addresses. When uploading PII to Adobe Analytics, Adobe recommends that the customer should hash PII prior to uploading it to Adobe. Hashed information can still be used for analysis and for marketing purposes. As a reminder, Adobe prohibits advertisers from sending sensitive personal information to Adobe Analytics, such as medical records, financial account information, and information about minors. </p> 
<p> - Adobe recommends its advertisers carefully consider which information is appropriate to use for marketing purposes and in which circumstances the advertiser has permission to use such information. </p> 
<p> - As consumer privacy law remains in flux, Adobe recommends that advertisers respect three common tenets: 1) Do what you say (in your privacy policy); 2) Say what you do (in your privacy policy); and 3) Don't surprise your consumers. </p> 
<p> - With these expectations in mind, Adobe recommends that when an advertiser associates browsing activities to PII, the advertiser provide notices/personalization indicating that the consumer is authenticated. An example of this is including a 'Hello, Jane' greeting within the header of the website. Adobe also recommends that advertisers describe in its privacy policy what type of browsing information it associates with PII and under what circumstances browsing information is associated with PII. Lastly, Adobe strongly recommends advertisers review the opt out choices they provide their consumers to understand whether and how they can use unauthenticated profile information post opt out. </p> 
<p>Possibly revamp the cookies to include privacy, with best practices: https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/ </p> -->
