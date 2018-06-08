---

title: Experience Cloud ID Service API Methods
description: List of API Methods for the Adobe Experience Cloud ID Service
seo-title: API Methods for the Adobe Experience Cloud ID Service
seo-description: List of API Methods for the Adobe Experience Cloud ID Service
short-title: API Methods
doc-type: reference
audience: admin
index: true
translate: true
version: false
private-feature-pack: false
beta: false
redirect: false

---

<!--Meta Data Values

**Required Meta for search optimization and page data**

title: free text string

description: free text string

seo-title: free text string

seo-description: free text string

**Optional Meta for extended capabilities**

audience:
all (default), admin, developer, end-user
 
index: true (default), false
 
translate:
true (default), false
 
doc-type:
reference (default), tutorials

version:
false (default), Classic, Standard, 6.5, 6.4, 6.3, 6.2
 
private-feature-pack:
false (default), true
 
beta:
false (default), true
 
redirect:
false (default), pathname
-->

# List of Methods for the Experience Cloud ID Service

Public methods that let you interact with the ID service.

## [appendSupplementalDataIDTo](id-service-api-methods-appendsupplementaldataidto.md) 
This helper method lets you append the Supplemental Data ID \(SDID\) as a query string parameter to a redirect URL. This is useful when using A4T and you need to persist the SDID from one page to another and stitch those separate visits together. To use this function, you must have implemented the ID service with the same Organization ID on the source and destination domains.

## [appendVisitorIDsTo \(Cross-Domain Tracking\)](id-service-api-methods-appendvisitorid.md) 
This function lets you share a visitor's Experience Cloud ID across domains when browsers block third-party cookies. To use this function, you must have implemented the ID service and own the source and destination domains. Available in VisitorAPI.js version 1.7.0 or higher.

## [callTimeOut Methods](id-service-api-methods-timeout-functions.md)

## [ID Synchronization by URL or Data Source](id-service-api-methods-idsync.md)
The ID service functions `idSyncByURL` and `idSyncByDataSource` let you manually implement an ID sync in the Destination Publishing iFrame. These are available in VisitorAPI.js versions 1.10, or higher.

## [getInstance](id-service-api-methods-getinstance.md)
`getInstance` returns a visitor ID object for the specified Experience Cloud organization ID. This is required to initialize the visitor ID object provided to AppMeasurement through `s.visitor`.

## [getAnalyticsVisitorID](id-service-api-methods-getanalyticsvisitorid.md)
`getAnalyticsVisitorID` returns the legacy Analytics ID \(if any\) that was stored in the `s_vi` cookie before the Experience Cloud ID service was implemented. It returns an empty string if a visitor was never assigned an Analytics ID.

## [getCustomerIDs](id-service-api-methods-getcustomerids.md)
`getCustomerIDs` returns any customer IDs set by the Experience Cloud ID service.

## [setCustomerIDs](id-service-api-methods-setcustomerids.md)
 `setCustomerIDs` sets 1 or more key-value pairs that define customer IDs and their authentication state.

## [getMarketingCloudVisitorID](id-service-api-methods-getmcvid.md) 
`getMarketingCloudVisitorID` returns the Experience Cloud visitor ID.

## [getLocationHint](id-service-api-methods-getlocationhint.md)
`getLocationHint` returns the Experience Cloud ID service region ID. A region ID \(or location hint\), is a numeric identifier for the geographic location of a particular ID service data center. You need the region ID in order to make server-side API calls to Audience Manager.

## [getVisitorValues](id-service-api-methods-getvisitorvalues.md)
`getVisitorValues` this is an asynchronous API that returns identifiers for Analytics, the ID service, data collection opt-out, geographic location, and metadata "blob" content by default. Also, you can control which IDs you want to return with the optional `visitor.FIELDS` enum.

## [resetState](id-service-api-methods-resetstate.md)
`resetState` This function is designed mainly for A4T customers to help solve issues related to working with IDs on single page sites/screens or apps.