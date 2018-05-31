---

title: Experience Cloud ID Service API Methods
description: List of API Methods for the Adobe Experience Cloud ID Service
SEO title: API Methods for the Adobe Experience Cloud ID Service
SEO description: List of API Methods for the Adobe Experience Cloud ID Service
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: ID Service API
guide subtopic 1: ID Service API Methods
guide subtopic 2:

---

# List of Methods for the Experience Cloud ID Service

Public methods that let you interact with the ID service.


## [appendSupplementalDataIDTo](id-service-api-methods-appendsupplementaldataidto.md) 
This helper method lets you append the Supplemental Data ID \(SDID\) as a query string parameter to a redirect URL. This is useful when using A4T and you need to persist the SDID from one page to another and stitch those separate visits together. To use this function, you must have implemented the ID service with the same Organization ID on the source and destination domains.

## [appendVisitorIDsTo \(Cross-Domain Tracking\)](mcvid-appendvisitorid.md) 
This function lets you share a visitor's Experience Cloud ID across domains when browsers block third-party cookies. To use this function, you must have implemented the ID service and own the source and destination domains. Available in VisitorAPI.js version 1.7.0 or higher.

## [callTimeOut Methods](mcvid-timeout-functions.md)

## [ID Synchronization by URL or Data Source](mcvid-idsync.md)
The ID service functions `idSyncByURL` and `idSyncByDataSource` let you manually implement an ID sync in the Destination Publishing iFrame. These are available in VisitorAPI.js versions 1.10, or higher.

## [getInstance](mcvid_getinstance.html)
`getInstance` returns a visitor ID object for the specified Experience Cloud organization ID. This is required to initialize the visitor ID object provided to AppMeasurement through `s.visitor`.

## [getAnalyticsVisitorID](mcvid_getanalyticsvisitorid.html)
Returns the legacy Analytics ID \(if any\) that was stored in the `s_vi` cookie before the Experience Cloud ID service was implemented. It returns an empty string if a visitor was never assigned an Analytics ID.

## [getCustomerIDs](mcvid_getcustomerids.html)
`getCustomerIDs` returns any customer IDs set by the Experience Cloud ID service.

## [setCustomerIDs](mcvid_setcustomerids.html)
 `setCustomerIDs` sets 1 or more key-value pairs that define customer IDs and their authentication state.

## [getMarketingCloudVisitorID](mcvid-getmcvid.html) 
`getMarketingCloudVisitorID` returns the Experience Cloud visitor ID.

## [getLocationHint](mcvid-getlocationhint.html)
Returns the Experience Cloud ID service region ID. A region ID \(or location hint\), is a numeric identifier for the geographic location of a particular ID service data center. You need the region ID in order to make server-side API calls to Audience Manager.

## [getVisitorValues](mcvid-getvisitorvalues.html)
This is an asynchronous API that returns identifiers for Analytics, the ID service, data collection opt-out, geographic location, and metadata "blob" content by default. Also, you can control which IDs you want to return with the optional `visitor.FIELDS` enum.

## [isClientSideMarketingCloudVisitorID](mcvid-client-side-id.html)

## [resetState](mcvid-resetstate.html)
This function is designed mainly for A4T customers to help solve issues related to working with IDs on single page sites/screens or apps.
