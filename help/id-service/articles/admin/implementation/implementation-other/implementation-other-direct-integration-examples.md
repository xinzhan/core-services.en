# Direct Integration Use Cases

These examples cover 2 common use cases related to a direct integration and the Experience Cloud ID \(MID\). The MID is a unique, persistent ID for your site visitors.

[!NOTE] 

+ Review and understand the [code syntax and variables](mcvid-direct-integration.html#) before diving into the use cases.
+ For more information about the MID, see [Cookies and the Experience Cloud ID Service](mcvid_cookies.html#).

[!END]

## Use Case 1: I Have a MID but Want to Pass My Own Visitor IDs and Set an Authentication State

<!-- BAD TABLE
|Use Case Element|Description|
|----------------|-----------|
|  **Conditions**| This use case assumes you:

+ Have a MID for the site visitor. Let's call this ID 1234.
+ Know this visitor by your own unique ID. Let's call this ID 9876.
+ Want to link the MID \(1234\) to your own, unique ID \(9876\).
+ *\(Optional\)* Want to set an authentication status on this visitor.

 |
|  **Actions** 

 | Given these conditions, make a call to the ID service that includes:

+ The MID \(1234\).
+ Your data provider ID. This is a unique ID assigned to your company. Let's call this ID 4444.
+ Your ID for the visitor \(9876\).
+ *\(Optional\)* A status ID to define the authentication state for this visitor.

 And, if you happen to have any of the other parameters listed in the [direct integration guide](mcvid-direct-integration.html#) \(e.g.,`d_blob` or `dcs_region`, etc.\) it's ok to pass those in as well.

 |
|  **Solution and code sample** 

 | Format your call to the ID service like this:

  `https://dpm.demdex.net/id?d_mid=**1234**&d_cid=**4444**%01**9876**%01**1**&d_ver=2` 

 Note how the sample call contains the:

+ MID: `d_mid=**1234**` 
+ MID joined to your unique ID for the visitor: `d_mid=**1234**&d_cid=**4444**%01**9876**%011` 
+ Authentication state ID: `...d_cid=4444%019876%01**1**` \(hint: it's that last digit\).

 |

## Use Case 2: I Do Not Have a MID and Need to Generate It

|Use Case Element|Description|
|----------------|-----------|
|  **Conditions** 

 | This use case assumes you:

 + Do not have a MID for the site visitor.
+ Need to request a MID from the ID service.
+ Know your [organization ID](mcvid-requirements.html#section_A02F537129A64FFBB690D5738D360C26). Let's call this 5555.

 |
|  **Actions** 

 | Given these conditions, make a call to the ID service that includes your Organization ID.

 And, if you happen to have any of the other parameters listed in the [direct integration guide](mcvid-direct-integration.html#) \(e.g.,`d_blob` or `dcs_region`, etc.\) it's ok to pass those in as well.

 |
|  **Solution and code sample** 

 | Format your call to the ID service like this:

  `https://dpm.demdex.net/id?d_orgid=**5555**&d_ver=2` 

 Note how the sample call contains your Organization ID, `d_orgid=**5555**`. It would return a Experience Cloud ID for this visitor.
-->