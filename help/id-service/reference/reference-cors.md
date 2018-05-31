---

title: API Methods - appendSupplementalDataIDTo
description: appendSupplementalDataIDTo helper method for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Methods - appendSupplementalDataIDTo
SEO description: appendSupplementalDataIDTo helper method for the Adobe Experience Cloud ID Service API
author: giurgiu
doc type: technical doc
archetype: administrator
machine translation: y
business unit: digital-experience
cloud: experience-cloud
solution: core-services-id-service
guide: Admin
guide topic: ID Service API
guide subtopic 1: ID Service API Configurations
guide subtopic 2:

---

# CORS Support in the Experience Cloud ID Service

Browsers use Cross Origin Resource Sharing (CORS) to request resources from a domain other than the current domain. The Experience Cloud ID service supports CORS standards that enable these client-side, cross-origin resource requests. The ID service reverts to JSONP requests on older browsers or browsers that do not support CORS.

## Problems with Same-Origin Policies and ID Service Requests

Same-origin policies are security controls or restrictions enforced by a web browser. When enforced on this level, the web browser itself determines if a request for resources made from one page to another will be permitted or blocked. To determine if a request is a same-origin request, the browser compares:

+ Uniform Resource Identifiers (URIs)
+ Host names (e.g., `http://www.my-webpage-example.com`)
+ Port numbers (e.g., port 80 and 440 for HTTP and HTTPS requests)

The browser allows a request to succeed if both pages share these characteristics and blocks resource requests if they do not.

## CORS Resolves Problems with Same-Origin Policies

CORS provides a secure, effective way to request resources across different domains. 

The CORS specification includes a set of HTTP headers that browsers use to send, receive, and evaluate resource requests. Evaluating a resource request is called a preflight check. This check lets browsers and servers determine which requests are allowed or blocked. 

The preflight check is transparent to the app, API, or script that requests a resource. Two headers that are important in the resource request process include:

+ `Origin:` A request header that identifies the source of a request.
+ `Access-Control-Allow-Origin:` A response header that indicates if a resource can be shared with the requestor.

Let's take a look at how these headers work. 

In this example, say we have a financial services company that has implemented the Experience Cloud ID service on their site, `www.finance-website.com`. The following table defines how the CORS request and response headers check for access to a resource.
