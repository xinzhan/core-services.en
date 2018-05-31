# 2016 Release Notes

Feature releases, updates, or changes to the Experience Cloud ID service for 2016.

These changes are also captured in the [Experience Cloud Release notes](https://marketing.adobe.com/resources/help/en_US/whatsnew/). See the [previous release notes](https://marketing.adobe.com/resources/help/en_US/whatsnew/?f=c_legacy_releases.html) for older Experience Cloud announcements.

## Version 1.10

November, 2016

**Important:** 

-   Version 1.10 requires AppMeasurement 1.8.0.

**Important:** 

**Important:** 

-   
-   Using Experience Cloud ID service Library 2.0.0+, ID synching will begin for Adobe Media Optimizer by default. See [Understanding ID Synchronization and Match Rates](https://marketing.adobe.com/resources/help/en_US/mcvid/mcvid-match-rates.html).

 **Fixes and Improvements** 

-   Added instructions on how to implement the ID service in a server-side environment. See [Server-Side Implementation of the Experience Cloud ID Service](mcvid-setup-server-side.html#).
-   Added `Visitor.overwriteCrossDomainMCIDAndAID`, a boolean function that lets you overwrite the Experience Cloud and Analytics IDs on other domains that you own. See [overwriteCrossDomainMCIDAndAID](mcvid-overwrite-visitor-id.html#).
-   Added `TS = UTC` timestamp as a property of the `visitor.appendVisitorIDsTo`function. The ID service uses the timestamp to determine if it should use the IDs in the redirect URL based on a 5-minute aging interval. See [appendVisitorIDsTo \(Cross-Domain Tracking\)](mcvid-appendvisitorid.html#).
-   Added `Visitor.getLocationHint,` a new function that returns a region ID. See [getLocationHint](mcvid-getlocationhint.html#).
-   Added `idSyncByURL` and `idSyncByDataSource`, 2 functions that let you manually implement an ID sync in the Destination Publishing iFrame. See [ID Synchronization by URL or Data Source](mcvid-idsync.html#).
-   Fixed a bug that blocked the AppMeasurement tracking call if `disableThirdPartyCalls:true`.
-   Fixed a bug that prevented the ID service from passing the Experience Cloud ID \(MID\) across different domains.

## Version 1.9.0

October, 2016

 **Fixes and Improvements** 

-   Fixed a bug that passed Audience Manager unique user IDs \(AAMUUIDs\) as Experience Cloud IDs to the ID service.
-   If time-to-live \(TTL\) for an AMCV cookie has expired, the ID service will still return that information to the server as long as the cookie contains a Experience Cloud ID. After this call, the ID service makes an asynchronous call to update the cookie. This helps improve performance because the ID service doesn't have to wait for a server response. It can use existing AMCV cookie values and then request an update.
-   The ID service automatically synchronizes Experience Cloud IDs \(MIDs\) with Adobe Media Optimizer and other internal Adobe domains directly on the page. Automatic synchronization is enabled for all existing and new accounts. This helps improve match rates for Media Optimizer. Applies to VisitorAPI.js version 1.8, or higher. See also, [Understanding ID Synchronization and Match Rates](mcvid-match-rates.html#).

 **New and Revised Documentation** 

 **New:** [mcvid-regions.html\#](mcvid-regions.html#) 

## Version 1.8.0

September, 2016

 **Fixes and Improvements** 

Added `disableThirdPartyCalls` as an optional, Boolean flag you can set in the `Visitor.getInstance` function. When `disableThirdPartyCalls= true`, the ID service will not make calls to other domains. By default, `disableThirdPartyCalls= false`. See [disableThirdPartyCalls](mcvid-disablethirdpartycalls.html#).

## Version 1.7.0

August, 2016

 **Fixes and Improvements** 

-   Added `idSyncAttachIframeOnWindowLoad` as an optional boolean flag you can set in the `Visitor.getInstance` function. When `idSyncAttachIframeOnWindowLoad= true`, the ID service loads the ID synchronization iFrame on window load. By default, the ID service loads the iFrame as fast as possible. This flag *replaces*`idSyncAttachIframeASAP`, which is deprecated. See [Configurations](mcvid-function-vars.html#).
-   Added functionality to support tracking Experience Cloud IDs across domains, native apps and hybrid apps to web transitions. See [appendVisitorIDsTo \(Cross-Domain Tracking\)](mcvid-appendvisitorid.html#).
-   Added functions to visitorAPI.js code that determine if the ID service has generated the visitor Experience Cloud ID client-side or server-side or if ID calls timed out. See [mcvid-timeout-functions.html\#](mcvid-timeout-functions.html#) and[mcvid-client-side-id.html\#](mcvid-client-side-id.html#).

 **New and Revised Documentation** 

Revised: [Requirements for the Experience Cloud ID Service](mcvid-requirements.html#) 

 **Known Issues** 

Customers using Audience Manager DIL code and visitorAPI.js code on the same page should set the DIL variable `secureDataCollection= false`. See [secureDataCollection](https://marketing.adobe.com/resources/help/en_US/aam/?f=dil-secure-data-collection.html).

## Version 1.6.0

July, 2016

**Important:** Version 1.6.0 of the Experience Cloud ID service *requires* AppMeasurement for JavaScript version 1.6.2. If you upgrade to ID service version 1.6.0, please make sure you are using the right AppMeasurement code version.

|Feature|Description|
|-------|-----------|
| Cross-Origin Resource Sharing \(CORS\)

 | CORS allows browsers to request resources from a domain other than the current domain. The Experience Cloud ID service supports CORS standards to enable client side, cross-origin resource requests. The ID service reverts to JSONP requests on browsers that do not support CORS.

 See:

 -   [mcvid-cors.html\#](mcvid-cors.html#) 
-    [mcvid-use-cors-only.html\#](mcvid-use-cors-only.html#) 

 |

 **Fixes and Improvements** 

-   Added a `d_fieldgroup` parameter to ID synchronization calls to `dpm.demdex.net`. This new parameter is used for internal troubleshooting and debugging purposes.
-   Added a title attribute to the ID service iFrame. An iFrame title helps screen readers provide page information to users who require assistance when interacting with online content. The iFrame title attribute is set to `Adobe ID Syncing iFrame`.
-   Added `idSyncAttachIframeASAP: true` as an optional flag you can set in the `Visitor.getInstance` function. When `true`, the ID service loads the ID synchronization iFrame as fast as possible. This is designed to help improve ID synchronization match rates. By default, the ID service loads the iFrame on window load. See [Configurations](mcvid-function-vars.html#).
-   Fixed a bug with a callback function that caused AppMeasurement to get stuck in an infinite loop.
-   Changed the default `loadTimeout` interval to 30,000 milliseconds \(from 500 milliseconds\). See [Configurations](mcvid-function-vars.html#).

 **New and Revised Documentation** 

 **New** 

-   [Implement the Experience Cloud ID Service for Analytics](mcvid-setup-analytics.html#) 
-   [Implement the Experience Cloud ID Service for Analytics, Audience Manager, and Target](mcvid-setup-aam-analytics-target.html#) 

 **Revised** 

-   [Requirements for the Experience Cloud ID Service](mcvid-requirements.html#) 
-    [Test and Verify the Experience Cloud ID Service](mcvid-test-verify.html#) 

## Version 1.5.7

June, 2016

|Feature|Description|
|-------|-----------|
| Changes to the `iframe.sandbox` attribute

 | The iFrame is now set so that `iframe.sandbox='allow-scripts allow-same-origin';`.

 Allowing only these 2 tokens helps improve security and provides the ID service with the basic functionality required for ID synchronization.

 The sandbox attribute is not supported in Internet Explorer version 9 or earlier. For more information, see the Attributes section in this [iFrame documentation](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe).

 |
| Encoding the Experience Cloud ID \(MID\)

 | The ID service encodes the MID value returned from the server or when it's set by the `visitor.setMarketingCloudVisitorID()` function. For more information about the MID, see [Cookies and the Experience Cloud ID](mcvid_cookies.html#).

 |

 **Fixes** 

The visitor API no longer forces an extra re-synchronization call with Audience Manager when there is no legacy Analytics visitor ID.

## Version 1.5.x

May, 2016

 **Documentation Updates** 

-    [SDK Requirements for Android and iOS](mcvid-requirements.html#section_73B2446FBA8E463888642C7D7DFD94F1) 
-    [mcvid-dwb.html\#](mcvid-dwb.html#) 
-    [Test and Verify the Experience Cloud ID Service](mcvid-test-verify.html#) 

## Version 1.5.x

April, 2016

 **Documentation Updates** 

[Implement the Experience Cloud ID Service for Target](mcvid-setup-target.html#) 

## Version 1.5.4

March, 2016

|Feature|Description|
|-------|-----------|
| Opt-out support

 | The Experience Cloud ID service supports visitor opt-out requests.

 |
| Change ID synchronization interval

 | The Experience Cloud ID service now makes ID synchronization calls on every call to the data collection servers. Previously, the ID service made only 1 request on the first call to get a Experience Cloud ID.

 |

 **Documentation Updates** 

-   [Implement the Experience Cloud ID Service for Analytics](mcvid-setup-analytics.html#) : New procedure that describes how to set up the ID service with Analytics.
-   [Experience Cloud ID Service Migration Decision Points](mcvid-migration-decisions.html#) : Revised text for clarity. Working with a single domain means you can migrate away from a data collection CNAME if you no longer wish to manage it. However, there's no requirement to change if your CNAME is working.

 

## Version 1.5.3

January, 2016

 **Documentation Updates** 

|Topic|Description|
|-----|-----------|
|  [Customer IDs and Authentication States](mcvid-authenticated-state.html#) 

 | Revised text. Customer IDs must be passed in as un-encoded values only. Encoding IDs will create double-encoded identifiers.

 |

## Older Changes

**Parent topic:** [2017 Release Notes](mcvid-notes-2017.html)

