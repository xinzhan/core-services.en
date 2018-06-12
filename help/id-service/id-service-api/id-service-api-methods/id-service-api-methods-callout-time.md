---
title: calltimeout methods
description: call these id service functions to determine the timeout status for a experience cloud id service, analytics, or audience manager id request.
seo-title: calltimeout methods
seo-description: call these id service functions to determine the timeout status for an adobe experience cloud id service, analytics, or audience manager id request.
short-title: calltimeout methods
doc-type: reference
audience: admin
index: true
translate: true
version: false
private-feature-pack: false
beta: false
redirect: false
product: core services id service
cloud: experience cloud
archetype: admin
user-guide: id service admin guide
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-methods/id-service-api-methods-callout-time.md
git-issue: https://git.corp.adobe.com/AdobeDocs/core-services.en/issues/new
git-repo: https://git.corp.adobe.com/adobedocs/core-services.en
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

# callTimeOut Methods

Call these ID service functions to determine the timeout status for a Experience Cloud ID service, Analytics, or Audience Manager ID request. 

Available in `VisitorAPI.js` version 1.7.0 or higher.

## Timeout Functions

| Solution or Service         | Function Syntax                                        |
| --------------------------- | ------------------------------------------------------ |
| Experience Cloud ID Service | `var variableName = visitor.MCIDCallTimedOut()`        |
| Analytics                   | `var variableName = visitor.AnalyticsIDCallTimedOut()` |
| Audience Manager            | `var variableName = visitor.AAMIDCallTimedOut()`       |

## Function Responses

| Response | Description                                                                       |
| -------- | --------------------------------------------------------------------------------- |
| `TRUE`   | The ID service sent a request and the request timed out.                          |
| `FALSE`  | The ID service sent a request and received a successful response from the server. |
| `NULL`   | The ID service did not send a request.                                            |