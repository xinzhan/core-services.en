---

title: Test and Verify the Experience Cloud ID Service
description: appendSupplementalDataIDTo helper method for the Adobe Experience Cloud ID Service API
seo-title: Adobe Experience Cloud ID Service API Methods - appendSupplementalDataIDTo
seo-description: appendSupplementalDataIDTo helper method for the Adobe Experience Cloud ID Service API
short-title: Test and verify
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

# Test and Verify the Experience Cloud ID Service

These instructions, tools, and procedures help you determine if the ID service is working properly. These tests apply to the ID service in general and for different ID service and Experience Cloud solution combinations.

## Before You Begin

| Recommendations      | Description                                                                                                                                                                                                                                                                                                                                                                                                                                |
| :------------------- | :---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| Browser Environments | When testing in a normal browser session, clear your browser cache before each test. Alternatively, you can test the ID service in an anonymous or incognito browser session. In an anonymous session, you don't need to clear your browser cookies or cache before each test.                                                                                                                                                                  |
| Value                | The [Adobe debugger](https://marketing.adobe.com/resources/help/en_US/sc/implement/debugger.html) and the [Charles HTTP proxy](https://www.charlesproxy.com/) can help you determine if the ID service has been configured to work properly with Analytics. The information in this section based on the results returned by the Adobe debugger and Charles. However, you should feel free to use whatever tool or debugger works best for you. |

## Testing with the Adobe Debugger

Your service integration is configured properly when you see a Experience Cloud ID \(MID\) in the Adobe debugger response. See [Cookies and the Experience Cloud ID Service](../../getting-started/getting-started-cookies.md) for more information about the MID.

### To verify the status of the ID service with the Adobe debugger

+ Clear your browser cookies or open an anonymous browsing session.
+ Load your test page that contains ID service code.
+ Open the Adobe debugger.
+ Check the results for a `MID`.

## Understanding Adobe Debugger Results

The MID is stored in a key-value pair that uses this syntax: `MID=Experience Cloud ID`. The debugger displays this information as shown below.

### Implementation Success

The ID service has been implemented properly if you see a response that looks similar to this:

`mid=20265673158980419722735089753036633573` 

If you're an Analytics customer, you may see an Analytics ID \(AID\) in addition to the MID. This happens:

+ With some of your early/long-time site visitors.
+ If you have a grace period enabled.

### Implementation Failure

Contact [customer care](https://helpx.adobe.com/marketing-cloud/contact-support.html) if the debugger:

+ Does not return a MID.
+ Returns an error message that indicates your partner ID has not been provisioned.

## Testing with the Charles HTTP Proxy

To verify the status of the ID service with Charles:

+ Clear your browser cookies or open an anonymous browsing session.
+ Start Charles.
+ Load your test page that contains ID service code.
+ Check for the request and response calls and data described below.

## Understanding Charles Results

Refer to this section for information about where to look, and what to look for, when you use Charles to monitor HTTP calls.

### Successful ID Service Requests in Charles

Your ID service code is working properly when the `Visitor.getInstance` function makes a JavaScript call to `dpm.demdex.net`. A successful request includes your [Organization ID](mcvid-requirements.html#section_A02F537129A64FFBB690D5738D360C26). The Organization ID is passed as a key-value pair that uses this syntax: `d_orgid=organization ID`. Look for the `dpm.demdex.net` and the JavaScript calls under the Structure tab. Look for your Organization ID under the Request tab.

![Charles request](../../assets/charles_request.png) 

### Successful ID Service Responses in Charles

Your account has been provisioned correctly for the ID service when the response from the [Data Collection Servers](https://marketing.adobe.com/resources/help/en_US/aam/c_compcollect.html) \(DCS\) return a MID. The MID is returned as a key-value pair that uses this syntax: `d_mid:visitor Experience Cloud ID`. Look for the MID in the Response tab as shown below.

![Successful Charles response](../../assets/charles_response_success.png) 

### Failed ID Service Responses in Charles

Your account has not been provisioned correctly if the MID is missing from the DCS response. An unsuccessful response returns an error code and message in the Response tab as shown below. Contact customer care if you see this error message in the DCS response.

![Unsuccessful Charles response](../../assets/charles_response_unsuccessful.png) 

For more information about error codes, see [DCS Error Codes, Messages, and Examples](https://marketing.adobe.com/resources/help/en_US/aam/dcs_error_codes.html).