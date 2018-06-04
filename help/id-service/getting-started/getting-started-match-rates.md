---

title: Understanding ID Syncronization and Match Rates
description: An overview of ID synchronization processes and match rates in the Experience Cloud ID service, including Adobe Media Optimizer.
seo-title: Understanding Adobe Experience Cloud ID Service and Match Rates
seo-description: An overview of the synchronization processes and match rates in the Adobe Experience Cloud ID service, including Adobe Media Optimizer.
short-title: free text
audience: all
doc-type: article
author: name
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

# Understanding ID Synchronization and Match Rates

An overview of ID synchronization processes and match rates in the Experience Cloud ID service, including Adobe Media Optimizer and the ID service.

## ID Synchronization and Match Rates

ID synchronization matches IDs assigned by the ID service to IDs assigned to site visitors by our customers. For example, say the ID service has assigned a visitor ID 1234. Another platform knows this visitor by ID 4321. The ID service maps these IDs together during the synchronization process. The results add new data points to what our customers know about their site visitors. And, if the ID service can't match an ID, it creates a new one and uses that ID for future synchronization.

Match rates measure and validate the effectiveness of the ID synchronization process. High match rates suggest that a particular service will be more effective and provide access to a larger online audience than a service with low match rates. Comparing match rates is a quantifiable way to evaluate different integrated ad tech platforms.

![](media/getting-started-match-rates/idsync2.png "ID syncronization in the ID Service") 

## Note Ensuring High Match Rates

To generate high match rates, it is important to set up the ID service properly \(see the [standard implementation guide](mcvid-standard.html#)\). 

A proper implementation helps ensure high match rates because lets the ID service set the cookies it requires to function and synchronize IDs with enabled data partners. However, factors such as slow Internet connections, data collection from mobile devices or wireless networks can affect how well the ID service collects, synchronizes, and matches IDs. 
These client-side variables are beyond the control of the ID service or Adobe.

>[!PROCEDURE Title="ID Synchronization Process Described"] 
>
>>[!Step]
>>
>>**Load Page**
>>
>>When a visitor comes to your site and loads a page, the `Visitor.getInstance` function makes a [CORS](mcvid-cors.html#) or JSON-P call to the ID service. The ID service responds with a cookie that includes the visitor's Experience Cloud ID \(MID\). The MID is a unique ID assigned to each site visitor. 
>See also, [Cookies and the Experience Cloud ID Service](mcvid_cookies.html#).
>
>[!END]
>[!STEP]
>
>**Load iFrame** 
>
>While the page body is loading, the ID service loads an iFrame called the Destination Publishing iFrame. The Destination Publishing iFrame loads in a domain separate from the parent page. This design helps ensure page performance and improves security because the iFrame:
>
>+ Loads asynchronously in relation to parent page. This means the parent page can load independently from the Destination Publishing iFrame. Loading the iFrame and loading ID sync pixels from within the iFrame won't affect the parent page or the user experience.
>+ Loads as fast as possible. If this is too fast, you can load the iFrame after the window load event \(not recommended\). See [idSyncAttachIframeOnWindowLoad](mcvid-idsyncattachiframeonwindowload.html#) for details.
>+ Prevents code in the iFrame from gaining access to or affecting the parent page.
>
>See also, [How the Experience Cloud ID Service Requests and Sets IDs](mcvid_id_request.html#).
>
>[!END]
>[!STEP]
>
>**Fire ID syncs** 
>
>The ID sync is a URL that is fired in the Destination Publishing iFrame. As shown in this generic example, an ID sync URL contains a partner's ID synchronization endpoint and a redirect URL, which is a redirect back to Adobe that includes their ID.
>
>+ `http://abc.com?partner_id=abc&sync_id=123&redir=http://dpm.demdex.net/ibs:dpid=<ADOBE\_PARTNER\_ID>&dpuuid=<PARTNER\_UUID>` 
> 
>See also, [ID Synchronization for Inbound Data Transfers](https://marketing.adobe.com/resources/help/en_US/aam/c_id_sync_in.html).
>
>[!END]
>[!STEP]
>
>**Store IDs** 
>
>Synchronized IDs are stored on the [edge and core data servers](https://marketing.adobe.com/resources/help/en_US/aam/c_compedge.html).
>
>[!END]
>[!END]

## Sync Services Manages ID Synchronization

The term Sync Services refers to internal Experience Cloud technologies responsible for ID synchronization. This service is enabled by default. To disable it, add an [optional variable](mcvid-disableidsync.html#) to the ID service `Visitor.getInstance` function. Sync Services matches different Experience Cloud IDs such as:

+ Third-party Experience Cloud cookie IDs to first-party Experience Cloud IDs.
+ First-party Experience Cloud cookie IDs to Adobe Media Optimizer \(AMO\) IDs.
+ Third-party Experience Cloud cookie IDs to third-party data provider and targeting platform IDs. This includes services and platforms such as data providers, demand and/or supply-side platforms, ad networks, exchanges, etc.
+ First-party Experience Cloud cookie IDs to cross-device partner IDs.

## ID Synchronization with Adobe Media Optimizer

Adobe Media Optimizer is an exception to the iFrame-based ID synchronization process. Because Media Optimizer is a trusted domain, ID syncs take place from the parent page rather than in the Destination Publishing iFrame. 

During synchronization, the ID service calls Media Optimizer at `cm.eversttech.net`, which is a legacy domain name used by Media Optimizer prior to its acquisition by Adobe. Sending data to Media Optimizer helps improve match rates and is automatic for ID service customers using version 2.0 \(or higher\). 

See also,
+ [Media Optimizer Cookies](https://marketing.adobe.com/resources/help/en_US/whitepapers/cookies/cookies_media_optimizer.html).
+ [Understanding calls to the Demdex domain](https://marketing.adobe.com/resources/help/en_US/aam/demdex-calls.html)
