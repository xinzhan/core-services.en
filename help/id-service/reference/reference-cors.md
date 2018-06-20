---
title: cors support in the experience cloud id service
description: browsers use cross origin resource sharing (cors) to request resources from a domain other than the current domain.
seo-title: cors support in the experience cloud id service
seo-description: browsers use cross origin resource sharing (cors) to request resources from a domain other than the current domain.
short-title: cors support
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/reference/reference-cors.md
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