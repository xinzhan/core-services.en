# 2017 Release Notes

Feature releases, updates, or changes to the Experience Cloud ID service for 2017.

These changes are also captured in the [Experience Cloud Release notes](https://marketing.adobe.com/resources/help/en_US/whatsnew/). For older ID service release notes, see the [previous release notes](https://marketing.adobe.com/resources/help/en_US/whatsnew/?f=c_legacy_releases.html) or the links at the bottom of this page.

**Attention:** There are no customer-facing release notes or code changes for March, April, May, and October 2017. For those months, the ID service code remained unchanged at v2.1.

## Version 2.5

September, 2017

|Feature|Description|
|-------|-----------|
| `getVisitorValues` | This is an asynchronous API that returns identifiers for Analytics, the ID service, data collection opt-out, geographic location, and metadata "blob" content by default. Also, you can control which IDs you want to return with the optional `visitor.FIELDS` enum. See [getVisitorValues](mcvid-getvisitorvalues.html#).|

**Bug Fixes and Other Changes** 

-   Fixed a Chrome-related bug that caused the ID service to throw an error when clicking the back button in that browser.
-   The ID service now re-fires ID syncs when the region ID in the event call response changes.
-   Added new documentation, [Content Security Policies and the Experience Cloud ID Service](mcvid-csp.html#), that explains how to whitelist calls to Adobe domains used by the ID service.

## Version 2.4

August, 2017

|Feature|Description|
|-------|-----------|
| `isCoopSafe` | An optional, Boolean configuration that determines if the ID service sends \(or does not send\) data to the Adobe Experience Cloud Device Co-op. See [isCoopSafe](mcvid-coopsafe.html#).|

**Revised Documentation** 

Updated and revised the[FAQs](mcvid-faq-intro.html#) to include separate FAQs for different Experience Cloud solutions.

## Version 2.3

July, 2017

|Feature|Description|
|-------|-----------|
| `sdidParamExpiry` | When added to the `Visitor.getInstance` function, this configuration lets you override the default Supplemental Data ID \(SDID\) expiration interval when passing that ID from one page to another. You would use `sdidParamExpiry` with the `appendSupplimentalDataTo` helper function. See [sdidParamExpiry](mcvid-sdidparamexpiry.html#).|
| `resetState` | This function is designed mainly for A4T customers to help solve issues related to working with IDs on single page sites/screens or apps. See [resetState](mcvid-resetstate.html#).|

**Bug Fixes and Other Changes** 

-   Fixed a bug in VisitorAPI.js v2.2 that prevented the ID service and Target from working together in Internet Explorer.
-   Revised code to help improve how the ID service sends data to the Destination Publishing iFrame. This helps reduce CPU usage.

## Version 2.2

June, 2017

|Feature|Description|
|-------|-----------|
| [whitelistParentDomain and whitelistIframeDomains](mcvid-whitelistdomain.html#) | These configurations let different instances of ID service code implemented in an iFrame and on the parent page communicate with each other. They're designed to help resolve problems with 2 specific use cases where you may or may not control the parent page/domain and you have ID service code loading in the iFrame of a domain that you do control.|

## Documentation Updates for May

|Topic|Description|
|-----|-----------|
| [ID Service FAQs](mcvid-faq.html#) | Updated the Analytics section with information on how to find tracking server information.|

## Documentation Updates for April

|Topic|Description|
|-----|-----------|
| [mcvid-subdomain-config.html\#](mcvid-subdomain-config.html#) | Added links to Audience Manager documentation that describes calls to the `demdex.net` domain.|
| [Understanding ID Synchronization and Match Rates](mcvid-match-rates.html#) | Revised Media Optimizer section to describe the call to `cm.eversttech.net`. This is the automatic ID sync that the ID service performs with Media Optimizer. This feature was released in January, 2017. See [Version 2.0](mcvid-notes-2017.html#section_0CEAC6007C1241B58AD607E2B76B2B7E) below.|

## Version 2.1

February, 2017

**Features** 

|Feature|Description|
|-------|-----------|
| ID service API property, `idSyncContainerID` | This property sets the container ID used by Audience Manager for ID syncs. See [idSyncContainerID](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-idsyncontainerid.html).|
| ID service API method, `appendSupplementalDataIDTo(URL,SDID)` | This public method appends the Supplemental Data ID \(SDID\) as a query string parameter to a redirect URL. See [appendSupplementalDataIDTo](mcvid-appendsupplementaldataidto.html#). \(MCID-285\)|

**Fixes** 

Fixed a bug that caused the ID service to make redundant server calls for an ID instead of using the ID stored in the AMCV cookie. \(MCID-296\)

**New Documentation** 

[Using DNS Prefetch with Different Experience Cloud Solutions and Services](https://marketing.adobe.com/resources/help/en_US/mcloud/dns-prefetch.html) 

## Version 2.0

January, 2017

**Important:** The ID service code v2.0 automatically synchronizes IDs with Adobe Media Optimizer by default. This means you'll see a call from the page to `cm.eversttech.net`, which is a legacy Media Optimizer domain controlled by Adobe. See also, [Understanding ID Synchronization and Match Rates](mcvid-match-rates.html#).

 **Fixes and Improvements** 

-   Fixed a bug that prevented AppMeasurement from making tracking calls to Analytics. \(MCID-254, MCID-256, MCID-286\)
-   Fixed a bug that prevented the ID service from failing right away if a visitor had enabled an ad blocker and that blocker was configured to exclude the demdex.net domain. This is a rare and unusual bug because most ad blocking tools do not block the demdex.net domain. \(MCID-233\)
-   Fixed a bug caused by interactions between ID service code and a custom script on a customer's website. This issue prevented Internet Explorer 9 from loading Web pages. \(MCID-206\)

## Previous Years

Older ID service release notes.

-   **[2016 Release Notes](mcvid-notes-2016.html)**  
Feature releases, updates, or changes to the Experience Cloud ID service for 2016.
-   **[2015 Release Notes](mcvid-notes-2015.html)**  
Release notes and updates for 2015.

