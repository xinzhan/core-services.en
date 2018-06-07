---

title: ID Service FAQs
description: Frequently asked questions and answers around the Experience Cloud ID Service
seo-title: Adobe Experience Cloud ID Service FAQs
seo-description: Frequently asked questions and answers around the Adobe Experience Cloud ID Service
short-title: free text
doc-type: article
author: name
index: yes
translate: yes
version:
private-feature-pack:
beta:
redirect:

---

# ID Service FAQs

Frequently asked questions about features, functionality, and issues related to using the Experience Cloud ID service.

## Functionality

### What sort of functionality or capabilities does the ID service provide?**
+ For an outline of capability and functionality of the Experience Cloud ID Service, [please review the documentation overview page](/id-service/overview.md) 
+ This can be difficult to diagnose. One thing you can check are the content security policy headers on your site. If you have a strict security policy, those settings can block the third-party calls made by the ID service. 
+ [See Content Security Policies and the Experience Cloud ID Service](../../reference/reference-analytics/reference-analytics-cname.md) for more information.

### Page Load Times and Latency
+ **How does the placement of the ID service VisitorAPI.js library affect page load times?**
    + Place the `VisitorAPI.js` library at the top of the page in the `<head>` section of your code. This helps ensure that the call for an ID goes out before the page body starts loading and maximizes the chances that an ID will return successfully.
    + The ID service call is asynchronous and is the only call to the `demdex.net` domain. It will not block other calls or affect time to first page interaction.
    + For Target customers, placing ID service code in the `<body>` of the page may increase the odds that it could block a Target call. If you must place ID service code in the body of your page, it should be placed after the open `<body>` tag.
+ **Does the ID service make a server call with every page load?**
    + No, this call will only happen the first time the page renders and once every 7 days thereafter. In the meantime, server calls are not required. The ID service operates in client-side mode and does not need to make a server call to return an ID.
+ **When using the ID service, what can cause slow page load times or affect the user experience?**
    + It is hard to catalog all of the possible conditions. Billions of consumer clients connect to our services and the tremendous variety in where and how they connect affect performance. For example:
        + Speeds vary greatly on mobile networks. These networks also suffer from signal and data or voice packet loss.
        + Connectivity suffers on devices connecting over WiFi under diverse conditions. For example, packet loss and speed problems are common in public places like coffee shops or in other environments like aircraft where packets must bounce through a satellite before reaching terrestrial networks.
        + Poorly configured local networks can negatively impact connectivity and speed.
        + Client devices may have their own problems such as low memory, excessive disk swapping, or limited CPU power relative to current workloads.
        + Browsers queue and execute remote server calls and even process the responses with different rules, depending on the browser maker and version. This behavior affects speed and performance.
+ **Can you name some improvements you made to shorten page load times?**
    + For example, thread yielding. We introduced thread yielding in case of multiple ID sync requests. We observed from lab reports that for customers performing multiple ID syncs, the UI would get blocked due to a lot of continuous CPU computations happening. As a result, we introduced thread yielding to separate out the ID sync requests by 100 msec each.
    + This change improves performance for customers using Visitor 2.3.0+ and DIL 6.10+. The improvements in page load times are shown in the figure below:

![Sync Improvements](../assets/id_sync_improvements_copy.png)
+ **Do browser requests using CORS vs JSON-P affect page performance?**
    + Resource requests with CORS are generally more preferable than with JSONP. With JSONP, some browsers queue and de-prioritize requests relative to other synchronous and asynchronous calls on the page. CORS helps ensure that these requests are treated with a higher priority in the browser call stack.
    + See [CORS Support in the Experience Cloud ID Service](../../reference/reference-cors.md)
    
### Security
+ **Does the ID service support CORS?**
    + See [CORS Support in the Experience Cloud ID Service](../../reference/reference-cors.md)
+ **What is CORS?**
    + Cross-Origin Resource Sharing or CORS, is a method that browsers use to request resources. The ID service always requests resources using CORS in browsers that support it. The ID service requests resources with JSON-P in older browsers that do not support CORS. See Experience Cloud.
+ **What if my security requirements are so strict that I never want to use JSONP?**
    + If you have strict security requirements, set the ID service API config useCORSOnly: true. You should only enable this mode if you’re confident that your site visitors use browsers that support CORS.
    + See [Experience Cloud](../../reference/reference-cors.md) and useCORSOnly.
