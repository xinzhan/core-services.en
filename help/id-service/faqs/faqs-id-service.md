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

## What sort of functionality or capabilities does the ID service provide?**

For an outline of capability and functionality of the Experience Cloud ID Service, [please review the documentation overview page](../../getting-started/getting-started-overview.md)

This can be difficult to diagnose. One thing you can check are the content security policy headers on your site. If you have a strict security policy, those settings can block the third-party calls made by the ID service. 

[See Content Security Policies and the Experience Cloud ID Service](../../reference/reference-analytics/reference-analytics-cname.md) for more information.

## Page Load Times and Latency

Place the `VisitorAPI.js` library at the top of the page in the `<head>` section of your code. This helps ensure that the call for an ID goes out before the page body starts loading and maximizes the chances that an ID will return successfully.

The ID service call is asynchronous and is the only call to the `demdex.net` domain. It will not block other calls or affect time to first page interaction.

For Target customers, placing ID service code in the `<body>` of the page may increase the odds that it could block a Target call. If you must place ID service code in the body of your page, it should be placed after the open `<body>` tag.

## Page Load Times and Latency

+ link here
