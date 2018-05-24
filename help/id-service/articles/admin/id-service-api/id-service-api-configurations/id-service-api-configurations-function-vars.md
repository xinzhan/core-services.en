---

title: Full list of API Configurations
description: Full list of API Configurations with samples and instructions for Adobe Experience Cloud ID Service
SEO title: Full list of API Configurations for Adobe Experience Cloud ID Service
SEO description: API Configurations with samples and instructions for Adobe Experience Cloud ID Service
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: ID Service API
guide subtopic 1: ID Service API Configurations
guide subtopic 2:

---

# Full list of API Configurations for Experience Cloud ID Service
Configure the Experience Cloud ID Service by passing these properties to the `Visitor.getInstance` static method.

---

## [audienceManagerServer and audienceManagerServerSecure](id-service-api-configurations-subdomain-config.md) 

## [cookieDomain](id-service-api-configurations-cookiedomain.md)  
Required for multi-part, top-level domains where either of the last two parts of the URL are *greater than* 2 characters.

## [cookieLifetime](id-service-api-configurations-cookielifetime.md) 

### [disableThirdPartyCalls](id-service-api-configurations-disablethirdpartycalls.md) 
An optional, Boolean flag that prevents the ID service from making calls to other domains.

### [idSyncAttachIframeOnWindowLoad](id-service-api-configurations-idsyncattachiframeonwindowload.md) 
An optional, Boolean flag that controls how the Experience Cloud ID service loads the ID synchronization iFrame.

### [idSyncContainerID](id-service-api-configurations-idsyncontainerid.md)
This property sets the data source container ID that you want to use for ID syncs.

### [disableIdSyncs](mcvid-disableidsync.html)
An optional, Boolean flag that disables ID synchronization.

### [disableThirdPartyCookies](mcvid-disable-cookies.html)
An optional, Boolean flag that prevents the Experience Cloud ID service from returning the third-party, demdex.net cookie.

### [isCoopSafe](mcvid-coopsafe.html)
An optional, Boolean configuration that determines if the ID service sends \(or does not send\) data to the Adobe Experience Cloud Device Co-op.

### [loadTimeout](mcvid-loadtimeout.html)
Sets a timeout interval in milliseconds. Used to tell other solutions \(e.g., Analytics, Audience Manager, Target, etc.\) how long to wait for a response from the ID service.

### [overwriteCrossDomainMCIDAndAID](mcvid-overwrite-visitor-id.html)
This property overwrites a visitor's Experience Cloud and Analytics IDs as they navigate from one domain to a second domain. To overwrite an ID, you must own and have implemented the ID service on each domain. This code does not let you overwrite IDs on domains you do not control.

### [sdidParamExpiry](mcvid-sdidparamexpiry.html)
This configuration lets you override the default Supplemental Data ID \(SDID\) expiration interval when passing that ID from one page to another using the `appendSupplementalDataIDTo` helper function. 

By default, the ID service code on the receiving page has 30 seconds to get the SDID from the URL sent by the referring page. If the ID service code on the receiving page can't retrieve the SDID in less than 30 seconds it requests a new SDID. This functionality is mainly for A4T customers who need to pass the SDID from one page to another and want control over this timeout interval.

### [useCORSOnly](mcvid-use-cors-only.html)

### [whitelistParentDomain and whitelistIframeDomains](mcvid-whitelistdomain.html)
These configurations let different instances of ID service code implemented in an iFrame and on the parent page communicate with each other. 

They're designed to help resolve problems with 2 specific use cases where you may or may not control the parent page/domain and you have ID service code loading in the iFrame of a domain that you do control. They are available in `VisitorAPI.js` code version 2.2, or higher.

**Parent topic:** [ID Service API](mcvid_library.html)

