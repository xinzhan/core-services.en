---
title: api configurations - idsynccontainerid
description: idsynccontainerid configurations for the adobe experience cloud id service api
seo-title: adobe experience cloud id service api configurations - idsynccontainerid
seo-description: idsynccontainerid configurations for the adobe experience cloud id service api
short-title: idsynccontainerid
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
git-edit: https://git.corp.adobe.com/AdobeDocs/core-services.en/tree/master/help/id-service/id-service-api/id-service-api-configurations/id-service-api-configurations-idsyncontainerid.md
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

# idSyncContainerID

This property sets the data source container ID that you want to use for ID syncs.

## Syntax
`idSyncContainerID:container ID here`

## Code Sample

```javascript
var visitor = Visitor.getInstance ("Insert Experience Cloud organization ID here",{
   ...
   //Set container ID
   idSyncContainerID:80
});
```

## What are Containers and When would I use them?

### Containers
Containers are objects created by Audience Manager. Although they're not externally accessible, these container list all the data sources that:

+ Are available to you, but not used, for ID syncing.
+ Are being used for ID syncing.

Even if you're not an Audience Manager customer, your account will have these containers if you're exchanging IDs with different data sources on different pages across your domain. This is because Audience Manager provides the technology and back-end functionality that enables ID synchronization.

## Use Cases

Depending on your situation, you may or may not need to add this configuration to your ID service code.

### Not Needed
You do not need to use this configuration if:

+ You use the ID service with any Experience Cloud solution and don't perform ID syncs with other data sources. In this case, your account has a default container with ID 0 and no action is required.
+ All your data sources are in a single container.

### Needed
You need to use this configuration when all of these conditions apply:

+ You don't use Audience Manager.
+ You need to synchronize IDs with other data sources that are organized by containers.
+ You need to synchronize IDs with data sources in different containers on different pages across your domain.

## Setting Container IDs when using DIL and VisitorAPI.js

If you have deployed `DIL` *and* `VisitorAPI.js` on the same page:

+ Visitor ID service code takes precedence over DIL for ID syncs.
+ Set the `idSyncContainerID` configuration in the ID service code only.