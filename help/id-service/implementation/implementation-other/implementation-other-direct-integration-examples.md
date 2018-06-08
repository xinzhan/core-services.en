---

title: Direct integration use cases
description: Direct integration use cases for the Adobe Experience Cloud ID Service
seo-title: Direct integration use cases for ID Service
seo-description: Direct integration use cases for the Adobe Experience Cloud ID Service
short-title: Direct Integration
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

# Direct Integration Use Cases

These examples cover 2 common use cases related to a direct integration and the Experience Cloud ID \(`MID`\). The `MID` is a unique, persistent ID for your site visitors.

>[!NOTE] 
>+ Review and understand the [code syntax and variables](implementation-other-direct-integration.md) before diving into the use cases.
>+ For more information about the MID, see [Cookies and the Experience Cloud ID Service](../../getting-started/getting-started-cookies.md).

## Use Case 1: I Have a MID but Want to Pass My Own Visitor IDs and Set an Authentication State

### Conditions: This use case assumes you:

+ Have a MID for the site visitor. Let's call this ID `1234`.
+ Know this visitor by your own unique ID. Let's call this ID `9876`.
+ Want to link the MID \(`1234`\) to your own, unique ID \(`9876`\).
+ *\(Optional\)* Want to set an authentication status on this visitor.

### Actions

Given these conditions, make a call to the ID service that includes:

+ The MID \(`1234`\).
+ Your data provider ID. This is a unique ID assigned to your company. Let's call this ID `4444`.
+ Your ID for the visitor \(`9876`\).
+ *\(Optional\)* A status ID to define the authentication state for this visitor.

And, if you happen to have any of the other parameters listed in the [direct integration guide](implementation-other-direct-integration.md) \(e.g.,`d_blob` or `dcs_region`, etc.\) it's ok to pass those in as well.

### Solution and code sample

Format your call to the ID service like this:

`https://dpm.demdex.net/id?d_mid=**1234**&d_cid=**4444**%01**9876**%01**1**&d_ver=2` 

Note how the sample call contains the:

+ MID: `d_mid=**1234**` 
+ MID joined to your unique ID for the visitor: `d_mid=**1234**&d_cid=**4444**%01**9876**%011` 
+ Authentication state ID: `...d_cid=4444%019876%01**1**` \ (hint: it's that last digit\).

## Use Case 2: I Do Not Have a MID and Need to Generate It

### Conditions: This use case assumes you:

+ Do not have a MID for the site visitor.
+ Need to request a MID from the ID service.
+ Know your [organization ID](../../reference/reference-requirements.md). Let's call this 5555.

### Actions

Given these conditions, make a call to the ID service that includes your Organization ID.

And, if you happen to have any of the other parameters listed in the [direct integration guide](../../reference/reference-requirements.md) \(e.g.,`d_blob` or `dcs_region`, etc.\) it's ok to pass those in as well.

### Solution and code sample

Format your call to the ID service like this:

`https://dpm.demdex.net/id?d_orgid=**5555**&d_ver=2` 

>[!NOTE]
>Please note how the sample call contains your Organization ID, `d_orgid=**5555**`. It would return a Experience Cloud ID for this visitor.
