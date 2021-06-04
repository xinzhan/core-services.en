---
description: Learn about the Experience Cloud Admin Tool. View a sortable and filterable list of all Experience Cloud users and policies.
keywords: core services
solution: Experience Cloud
title: View Experience Cloud users and user details 
index: yes
feature: Admin Console
topic: Administration
role: Administrator
level: Experienced
exl-id: 127eecdd-3862-48ba-8cf6-a8082d2b7bae
---
# View Experience Cloud users and policies in the Admin Tool

Administrators can view a sortable and filterable list of all Experience Cloud users and policies with details in the Admin Tool. User details include a user’s product access, roles, and last accessed information. Policy details include a policy's (product profile) user, group, developer, integration and admin list, as well as detailed permission and resource information for the policy. 

>[!NOTE]
>
>User and product management is configured in the [Admin Console](admin-getting-started.md).

1. Log in to `https://experience.adobe.com/.`

   ![](assets/admin-tool.png)

1. Under [!UICONTROL Quick Access], click **[!UICONTROL Admin Tool.]**

    (Alternatively, in the home page URL you can replace _home_ with _admin._)

    The [!UICONTROL Users] page displays.

## Users page

This page displays complete list of users with access to Experience Cloud in your organization. It provides information about solution entitlement and last login. You can search, sort, and filter for custom views of the user list.

![](assets/admin-tool-users.png)

|Element | Description|
|---|---|
|[!UICONTROL Name] |The first and Last name of the user. You can sort this column from A to Z and Z to A.  Click a user's name to see more details about the user.|
|[!UICONTROL Email] |The email address associated with the user. Column can be sorted A->Z, Z->A.|
|[!UICONTROL ID Type] |The identity type for the user's account. Filter can be applied to view specific ID types. See [Manage identity types](https://helpx.adobe.com/enterprise/using/identity.html) for more information.|
|[!UICONTROL Solutions] |Summary of Experience Cloud solutions that the user can access. You can apply filters to narrow down list of users with specific solution access.|
|[!UICONTROL Last Login] |Time and Date of the most recent user login to the Experience Cloud. This column can be sorted by ascending or descending dates. <br> **Important:** As of January 13, 2020 a user’s last login data will be kept for 365 days. This information is intended to show current login activity in the Experience Cloud and not a recommendation to take action on inactive accounts prior to January 13, 2020. |

## Customize the user list view

You can search, sort, or filter the columns to customize the user list.

* Search for users by Name or Email. Searches match the text string you type.
* Sort column by ascending or descending values. This sort applies to [!UICONTROL Name,] [!UICONTROL Email,] and [!UICONTROL Last Login] Columns.
* To apply multiple filters to list users with specific criteria, click the **[!UICONTROL Filter By]** icon. When multiple filter categories are applied, searches contain Email Domain `AND` ID TYPE `AND` Solution.

|Element | Description|
|---------|----------|
|[!UICONTROL Email Domain] filter | Search for character strings in the Email column to narrow results to one or multiple domains. Add multiple filters by pressing enter after each search term|
|[!UICONTROL ID Type] filter | Choose from available ID Types. Multiple ID types can be used as a filter.|
|[!UICONTROL Solution] filter | Choose from available solutions. Multiple solution filters search for results containing Solution 1 `OR` Solution 2.|

## View user details

On the [!UICONTROL Users] page, to view a user's details, click the user's email.

![](assets/admin-tool-user-details.png)

A detailed view of each user displays important details about the user’s solution access, admin and product roles, and last accessed information.

## About section

This section displays a summary of the user account including:

* User Avatar and System Admin Badge (If applicable)
* Name
* Email
* Username (Federated ID accounts can have usernames differing from Email address)
* [ID Type](https://helpx.adobe.com/enterprise/using/identity.html)
* Country
* Last Login

## Solutions summary

This section displays a summary of Experience Cloud solutions that the user can access. Includes the product administrative role when applicable.

## Detailed product access list

This section displays a complete list of all product profiles membership for the user.

|Element | Description|
|---------|----------|
|[!UICONTROL Product] | Name of the product associated with the product profile.|
|[!UICONTROL Instance] | Name of the instance (such as login company or tenant) associated with the product and product profile.|
|[!UICONTROL Product Profile] | Unique name of the product profile.|
|[!UICONTROL Assigned by Group] | Name of the User Group that associates the user to a product profile. Blank results indicate that the user was assigned to the product profile directly, not through a group.|
|[!UICONTROL Product Roles] | Role assignment of the user within the product profile. Currently, this information applies only to Adobe Target product profiles.|

## Policies page

This page displays complete list of Experience Cloud policies in your organization. It provides information about products, instances, users, and developers. You can search, sort, and filter for custom views of the policy list.

![](assets/admin-tool-policies.png)

|Element | Description|
|---|---|
|[!UICONTROL Product Profile] |The name of the product profile. Column can be sorted A->Z, Z->A. To see more details about the policy, click a product profile's name.|
|[!UICONTROL Product] |The product associated with the product profile. Column can be sorted A->Z, Z->A.|
|[!UICONTROL Instance] |The instance (for example, tenant or login company) associated with product profile. Products that do not have unique instances or tenants display a " - " for the value. Column can be sorted A->Z, Z->A.|
|[!UICONTROL Number of Users] |Unique count of users associated with the product profile including direct assignment and group assignment. Column can be sorted smallest to largest or largest to smallest.|
|[!UICONTROL Number of Developers] |Count of developer roles associated with the product profile. Column can be sorted smallest to largest or largest to smallest. |

## Customize the policies list view

You can search, sort, or filter the columns to customize the policies list.

* Search for product profiles by name. Searches match the text string you type.
* Sort column by ascending or descending values. This sort applies to [!UICONTROL Product Profile,] [!UICONTROL Product,] [!UICONTROL Instance,] [!UICONTROL Number of users,] and [!UICONTROL Number of Developers,] Columns.
* Click the **[!UICONTROL Filter By]** icon to apply multiple filters to list product profiles with specific criteria. When multiple filter categories are applied, searches contain Groups associated `AND` Instance `AND` Solution.

|Element | Description|
|---------|----------|
|[!UICONTROL Instance] filter | Search for character strings in the instance column to narrow results to one or multiple instances. Add multiple filters by pressing enter after each search term.|
|[!UICONTROL Solution] filter | Choose from available solutions. Multiple solution filters search for results containing Solution 1 `OR` Solution 2.|

## View policy details

On the [!UICONTROL Policies] page, to view a policy's details, click the product profile name.

![](assets/admin-tool-policy-detail.png)

A detailed view of each product profile displays important details about the product profile’s subjects (users, groups, and so on). It also displays permissions and resources enabled by the product profile.

Details of the product profile can be exported to CSV files. The [!UICONTROL Export CSV] option produces two CSV files:

* Subject Details (Users, User Groups, Developers, Integrations, Administrators)
* Permissions and resources items

## Summary section

This section displays a summary of the product profile including:

* Product profile name
* Number of users
* Number of developers
* Number of integrations
* Products Associated
* Instance

## Detailed subject list

This section displays a complete list of all users, user groups, developers, integrations, and administrators assigned to the product profile.

|Tab | Description|
|---------|----------|
|[!UICONTROL Users] | List of Users included in the product profile. User group association appears in [!UICONTROL Assigned by group] column.|
|[!UICONTROL User Groups] | List of user groups associated with the product profile.|
|[!UICONTROL Developers] | List of developers associated with the product profile.|
|[!UICONTROL Integrations] | List of integrations associated with the product profile.|
|[!UICONTROL Administrators] | List of administrators associated with the product profile.|

## Detailed permissions and resources lists

This section displays a complete list of permissions and resources available for the product profile. Permissions and resources that have been included in the product profile have been marked with a "✔". The lists of permissions and resources have been categorized into tabs and columns for easier viewing. Tabs and columns display the list of sections that apply to the current product.
