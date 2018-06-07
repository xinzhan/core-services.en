---

title: callTimeOut Methods
description: Call these ID service functions to determine the timeout status for a Experience Cloud ID service, Analytics, or Audience Manager ID request.
seo-title: callTimeOut Methods
seo-description: Call these ID service functions to determine the timeout status for an Adobe Experience Cloud ID service, Analytics, or Audience Manager ID request.
short-title: callTimeOut Methods
doc-type: article
audience: 
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

# callTimeOut Methods

Call these ID service functions to determine the timeout status for a Experience Cloud ID service, Analytics, or Audience Manager ID request. Available in `VisitorAPI.js` version 1.7.0 or higher.

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
