---

title: API Configurations - idSyncContainerID
description: idSyncContainerID configurations for the Adobe Experience Cloud ID Service API
SEO title: Adobe Experience Cloud ID Service API Configurations - idSyncContainerID
SEO description: idSyncContainerID configurations for the Adobe Experience Cloud ID Service API
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

**Containers** 

Containers are objects created by Audience Manager. Although they're not externally accessible, these container list all the data sources that:

+ Are available to you, but not used, for ID syncing.
+ Are being used for ID syncing.

Even if you're not an Audience Manager customer, your account will have these containers if you're exchanging IDs with different data sources on different pages across your domain. This is because Audience Manager provides the technology and back-end functionality that enables ID synchronization.

## Use Cases

Depending on your situation, you may or may not need to add this configuration to your ID service code.

**Not Needed** 

You do not need to use this configuration if:

+ You use the ID service with any Experience Cloud solution and don't perform ID syncs with other data sources. In this case, your account has a default container with ID 0 and no action is required.
+ All your data sources are in a single container.

**Needed** 

You need to use this configuration when all of these conditions apply:

+ You don't use Audience Manager.
+ You need to synchronize IDs with other data sources that are organized by containers.
+ You need to synchronize IDs with data sources in different containers on different pages across your domain.

## Setting Container IDs when using DIL and VisitorAPI.js

If you have deployed `DIL` *and* `VisitorAPI.js` on the same page:

+ Visitor ID service code takes precedence over DIL for ID syncs.
+ Set the `idSyncContainerID` configuration in the ID service code only.

**Parent topic:** [Configurations](mcvid-function-vars.html)

