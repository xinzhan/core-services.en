---
title: Customer Attributes Support for General Data Protection Regulation 
description: Learn about Customer Attributes Support for General Data Protection Regulation
feature: Customer Attributes
topic: Administration
role: Admin
level: Experienced
exl-id: 02417c0c-6780-4699-9470-f1685c3cd25d
---
# Customer Attributes support for General Data Protection Regulation

This page describes how [!UICONTROL Customer Attributes] supports General Data Protection Regulation (GDPR).

>[!IMPORTANT]
>
>The contents of this document are not legal advice or meant to substitute for legal advice. Consult with your legal counsel for advice concerning GDPR.

The [General Data Protection Regulation](https://business.adobe.com/privacy/general-data-protection-regulation.html), a law in effect May 25, 2018, gives all individuals (data subjects) within the borders of the European Union (EU) control of their personal data. It also simplifies the regulatory environment for international business. This law applies to all businesses (data controllers) that offer goods or services to, monitor the behavior of, or collect personal data from individuals within the borders of the EU at the time their personal data is processed, regardless of the data controller's business location.

Adobe Experience Cloud acts as a data processor for any personal data it receives and stores on behalf of its customers. As a data controller, you determine the personal data that Adobe Experience Cloud processes and stores on your behalf.

This document describes how [!UICONTROL Customer Attributes] supports your data subjects' GDPR data access and deletion rights using the Adobe Experience Platform Privacy Service API and Privacy Service UI.

For more information about what GDPR means for your business, see [GDPR and Your Business](https://business.adobe.com/privacy/general-data-protection-regulation.html).

## Required setup to send requests for [!UICONTROL Customer Attributes]

To make requests to access and delete data for [!UICONTROL Customer Attributes], you must:

1. Identify the following:

   * [Organization ID](#organizations.md)
   * Alias ID of CRS Data Source you want to act on
   * CRM ID of the profile you want to act on

   Your [organization ID](#organizations.md) is a 24-character alphanumeric string appended with @AdobeOrg. You need the organization's ID to submit requests to the Privacy API. Contact Adobe Customer Care at `gdprsupport@adobe.com` if you cannot locate the ID.

1. In [!UICONTROL Privacy Service], you can submit Access and Delete requests to Customer Attributes, and check the status of existing requests.

## Required field values in [!UICONTROL Customer Attributes] JSON requests

"company context":

* "namespace": **imsOrgID**
* "value": <*your IMS Org ID value*>

"users":

* "key": <*usually the name of the customer*>

* "action": either **access** or **delete**

* "user IDs":

    * "namespace": <*Alias ID of CRS Data Source*>
    
    * "type": **integrationCode**

    * "value": <*CRM ID*>

* "include": **CRS** (which is the Adobe product that applies to the request)

* "regulation": **gdpr** (which is the privacy regulation that applies to the request)

## Example of JSON request

```
{
  "companyContexts": [
    {
      "namespace": "imsOrgID",
      "value": "<IMS_ORG_ID>"
    }
  ],
  "users": [
    {
      "key": "<KEY>",
      "action": [
        "<access/delete>"
      ],
      "userIDs": [
        {
          "namespace": "<Alias ID of CRS Data Source>",
          "type": "integrationCode",
          "value": "<CRM ID>"
        }
      ]
    }
  ],
  "regulation": "<gdpr/ccpa/pdpa>",
  "include": [
    "CRS"
  ]
}
```

## Data Fields returned for access requests

```
attributes:
{
"value”:<*value*>,
"key”:<*key*>,
"displayName”:<*displayName*>
}
```
