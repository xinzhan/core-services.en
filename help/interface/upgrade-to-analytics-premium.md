---
description: Learn about the requirements and what to expect when upgrading to Analytics Premium.
keywords: Adobe Analytics Premium upgrade
solution: Experience Cloud
title: Upgrade to Analytics Premium and the Experience Cloud 
topic: Administration
uuid: 450a601c-d199-4e90-b525-19bd9f9576d2
feature: Admin Console
role: Admin
level: Experienced
exl-id: 746d396d-9629-42db-8c55-07d2d24e4611
---
# Upgrading to Analytics Premium and the Experience Cloud

Administrators can learn about the requirements and what to expect when upgrading to Analytics Premium, and where to find help as an Experience Cloud administrator.

## Analytics Premium {#section_7F50AD7906544F899B844BE31D3BB507}

Upgrading to Adobe Analytics Premium gives you all the capabilities or products available Analytics Standard, including Data Warehouse, Ad Hoc Analysis, Report Builder, and Data Connectors.

Analytics Premium gives you:

* Access to 250 conversion variables (eVars)
* [Mobile App Analytics](https://experienceleague.adobe.com/docs/mobile-services/using/home.html?lang=en)
* Data Workbench (Visual data query; rules-based attribution; cross-channel analysis)

>[!NOTE]
>
>No migration is necessary when upgrading, but there are a few considerations to be aware of:
>
>* eVars 76-250 and 100-250 (Standard) are visible in Admin Tools, but are not enabled.
>* Contribution Analysis is turned on by Adobe. It does not change location (it is still available on the Anomaly Detection page), but it automatically starts analyzing all data points.

## Analytics Premium Complete {#section_BFAD815EDF364845A52B340B2FD5B64C}

In Analytics Premium Complete, you get all the capabilities of [Analytics Premium](upgrade-to-analytics-premium.md#section_7F50AD7906544F899B844BE31D3BB507), plus the following upgrades:

| Product | Upgrades |
|--- |--- |
|Reports & Analytics|<ul><li>[Contribution Analysis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=en)</li><li>[Customer Attributes](attributes.md#concept_ACFEE7C8B8E94875BA0825CDF4913AF1) (Up to 200)</li></ul>|
|Data Workbench|<ul><li>Algorithmic Attribution</li><li>Pre-built workspaces</li></ul>|
|Analytics Platform|[Live Stream](https://github.com/AdobeDocs/analytics-1.4-apis/blob/master/docs/live-stream-api/index.md) (raw data, dashboards, triggers)|

{style="table-layout:auto"}

## Predictive Intelligence {#section_B407932C07A7476F83FB0275C3FB63DC}

Upgrading to Predictive Intelligence enables [Analytics Premium](upgrade-to-analytics-premium.md#section_7F50AD7906544F899B844BE31D3BB507) plus: 

|  Product  | Upgrades  |
|---|---|
|  Reports & Analytics  | [Contribution Analysis](https://experienceleague.adobe.com/docs/analytics/analyze/analysis-workspace/virtual-analyst/contribution-analysis/ca-tokens.html?lang=en)  |
|  Data Workbench  | Pre-built workspaces for audience qualifications and predictive marketing.  |
|  Analytics Platform  | Live Stream (dashboards and triggers)  |

{style="table-layout:auto"}

## Customer 360 {#section_3B2AC245388248688067DC9A48957AFB}

Upgrading to Customer 360 offers [Analytics Premium](upgrade-to-analytics-premium.md#section_7F50AD7906544F899B844BE31D3BB507) plus:

| Product | Upgrades |
|--- |--- |
|[Customer Attributes](attributes.md)|Customer Attributes  (analysis and segment sharing)|
|Data Workbench|<ul><li>Derived Customer Attributes</li><li>Pre-built workspaces for audience discovery</li></ul>|
|Analytics Platform|[Customer Attributes](attributes.md)|

{style="table-layout:auto"}

## Advanced Attribution {#section_9E4986A8389946CCAA7D003268343296}

Advanced Attribution offers access to [Analytics Premium](upgrade-to-analytics-premium.md#section_7F50AD7906544F899B844BE31D3BB507), plus Algorithmic Attribution in Data Workbench (25% server call volume).

## Data Workbench Requirements {#section_D959CA68D6DB42C38707F8E0CA3654CC}

The supported user(s) can request that all client licenses be updated to reflect the Premium by emailing `dwb@adobe.com`. This update enables features like Algorithmic Attribution.

TechOps reviews your contract commitment and determine the proper managed infrastructure, increasing or reducing capacity, and then they coordinate with you, through the Account Manager or consulting, to deploy any changes.

Any software that is running on-premise must be deactivated. This software includes Sensors, which means you must ensure proper tracking through [!DNL Analytics] tags.

## Experience Cloud - Administrate Users and Products {#section_6471C54454024301B2E0B687F79F6738}

Experience Cloud and core services are available to Analytics Standard and Premium users, if you have followed the implementation modernization described in [Getting started - enable your applications for core services](core-services.md#concept_07ED1D5C64234E77976E6D572E78FB9C). (That process helps you modernize your implementation, and enables you to become and administrator in the Experience Cloud.)

After you join the Experience Cloud, you can log in via the Experience Cloud at [!DNL experience.adobe.com] and begin using core services (including Customer Attributes, Audiences, and Mobile app analytics).

### Administrate Users and Groups

User management is performed in the [Adobe Admin Console](https://helpx.adobe.com/enterprise/using/admin-console.html) (product link).

You can set up a 1:1 map between a group created in the Adobe Admin Console and a solution group (such as Adobe Analytics). Thereafter, a new user added to the mapped Admin Console group has an Analytics application account automatically created and linked to the user's Adobe ID. (Existing users must manually link their application account credentials to access applications via the Experience Cloud login.)

>[!NOTE]
>
>You can map several application groups to one Admin Console group. However, Adobe recommends 1:1 mapping. Mapping the groups ahead of time allows you to invite, create, permission, and add multiple users by uploading a CSV.
