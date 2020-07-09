---
description: Learn about the Experience Cloud Admin Tool, to  view a sortable and filterable list of all Experience Cloud users and policies.
keywords: core services
seo-description: Learn about the Experience Cloud Admin Tool, to  view a sortable and filterable list of all Experience Cloud users and policies.
seo-title: View Experience Cloud users and user details
solution: Experience Cloud
title: View Experience Cloud users and user details 
index: yes
---
 
# View Experience Cloud users and policies in the Admin Tool

Administrators can view a sortable and filterable list of all Experience Cloud users and policies with details in the Admin Tool. User details include a user’s product access, roles, and last accessed information. Policy details include a policy's (product profile) user, group, developer, integration and admin list, as well as detailed permission and resource information for the policy. (**Note:** User and product management is configured in the [Admin Console](admin-getting-started.md).)

1. Log in to `https://experience.adobe.com/.`

   ![](assets/admin-tool.png)

1. From the Experience Cloud Home, click **[!UICONTROL Admin Tool.]**

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
|[!UICONTROL Last Login] |Time and Date of the most recent user login to the Experience Cloud. This column can be sorted by ascending or descending dates. <br> **Important:** As of January 13, 2020 a user’s last login data will be kept for 365 days. This information is intended to show current login activity in the Experience Cloud and not a recommendation to take action on inactive accounts prior to January 13th, 2020. |

## Customize the user list view

You can search, sort, or filter the columns to customize the user list.

* Search for users by Name or Email. Searches match the text string you type.
* Sort column by ascending or descending values. This applies to [!UICONTROL Name,] [!UICONTROL Email,] and [!UICONTROL Last Login] Columns.
* Click the **[!UICONTROL Filter By]** icon to apply multiple filters to list users with specific criteria. When multiple filter categories are applied, searches contain Email Domain `AND` ID TYPE `AND` Solution.

|Element | Description|
|---------|----------|
|[!UICONTROL Email Domain] filter | Search for character strings in the Email column to narrow results to one or multiple domains. Add multiple filters by pressing enter after each search term|
|[!UICONTROL ID Type] filter | Choose from available ID Types. Multiple ID types can be used as a filter.|
|[!UICONTROL Solution] filter | Choose from available solutions. Multiple solution filters search for results containing Solution 1 `OR` Solution 2.|

## View user details

On the [!UICONTROL Users] page, to view a user's details, click the user's email.

![](assets/admin-tool-user-details.png)

A detailed view of each user displays important details about the user’s solution access, admin and product roles, and last accessed information.

## About Section

This section displays a summary of the user account including:

* User Avatar and System Admin Badge (If applicable)
* Name
* Email
* Username (Federated ID accounts may have usernames differing from Email address)
* [ID Type](https://helpx.adobe.com/enterprise/using/identity.html)
* Country
* Last Login

## Solutions Summary

This section displays a summary of Experience Cloud solutions that the user can access. Includes the product administrative role when applicable.

## Detailed Product Access List

This section displays a complete list of all product profiles membership for the user.

|Element | Description|
|---------|----------|
|[!UICONTROL Product] | Name of the product associated with the product profile.|
|[!UICONTROL Instance] | Name of the instance (such as login company or tenant) associated with the product and product profile.|
|[!UICONTROL Product Profile] | Unique name of the product profile.|
|[!UICONTROL Assigned by Group] | Name of the User Group that associates the user to a product profile. Blank results indicate the user was assigned to the product profile directly, not through a group.|
|[!UICONTROL Product Roles] | Role assignment of the user within the product profile. Currently, this information applies only to Adobe Target product profiles.|

## Policies page

This page displays complete list of Experience Cloud policies in your organization. It provides information about products, instances, users, developers, integrations, and groups. You can search, sort, and filter for custom views of the policy list.

|Element | Description|
|---|---|
|[!UICONTROL Product Profile] |The name of the product profile. Column can be sorted A->Z, Z->A. Click a product profile's name to see more details about the policy.|
|[!UICONTROL Product] |The product associated with the product profile. Column can be sorted A->Z, Z->A.|
|[!UICONTROL Instance] |The instance (e.g. tenant or login company) associated with product profile. Products that do not have unique instances or tenants will display a " - " for the value. Column can be sorted A->Z, Z->A.|
|[!UICONTROL Number of Users] |Unique count of users associated with the product profile including direct assignment and group assignment. Column can be sorted smallest to largest or largest to smallest.|
|[!UICONTROL Number of Developers] |Count of developer roles associated with the product profile. Column can be sorted smallest to largest or largest to smallest. |
|[!UICONTROL Number of Integrations] |Count of integrations associated with the product profile. Column can be sorted smallest to largest or largest to smallest. |
|[!UICONTROL Groups Associated] |List of any groups that used to assign users to the product profile. Multiple values are separated by a comma. Filter can be applied to view specific groups. |

## Customize the policies list view

You can search, sort, or filter the columns to customize the policies list.

* Search for product profiles by name. Searches match the text string you type.
* Sort column by ascending or descending values. This applies to [!UICONTROL Product Profile,] [!UICONTROL Product,] [!UICONTROL Instance,] [!UICONTROL Number of users,] [!UICONTROL Number of Developers,] and [!UICONTROL Number of Integrations] Columns.
* Click the **[!UICONTROL Filter By]** icon to apply multiple filters to list product profiles with specific criteria. When multiple filter categories are applied, searches contain Groups associated `AND` Instance `AND` Solution.

|Element | Description|
|---------|----------|
|[!UICONTROL Groups associated] filter | Search for character strings in the groups associated column to narrow results to one or multiple groups. Add multiple filters by pressing enter after each search term.|
|[!UICONTROL Instance] filter | Search for character strings in the instance column to narrow results to one or multiple instances. Add multiple filters by pressing enter after each search term.|
|[!UICONTROL Solution] filter | Choose from available solutions. Multiple solution filters search for results containing Solution 1 `OR` Solution 2.|

## View policy details

On the [!UICONTROL Policies] page, to view a policy's details, click the product profile name.

A detailed view of each product profile displays important details about the product profile’s subjects (users, groups, etc.), and permissions and resources enabled by the product profile.  Details of the product profile can be exported to CSV files.  The [!UICONTROL Export CSV] option will produce 2 CSV files: Subject Details (Users, User Groups, Developers, Integrations, Administrators) and Permissions and Resources items.

## Summary Section

This section displays a summary of the product profile including:

* Product profile name
* Number of users
* Number of developers
* Number of integrations
* Products Associated
* Instance


## Detailed Subject List

This section displays a complete list of all users, user groups, developers, integrations, and administrators assigned to the product profile.

|Tab | Description|
|---------|----------|
|[!UICONTROL Users] | List of Users included in the product profile. User group association will appear in [!UICONTROL Assigned by group] column.
|[!UICONTROL User Groups] | List of user groups associated with the product profile.|
|[!UICONTROL Developers] | List of developers associated with the product profile.|
|[!UICONTROL Integrations] | List of integrations associated with the product profile.|
|[!UICONTROL Administrators] | List of administrators associated with the product profile.|

## Detailed Permissions and Resources Lists

This section displays a complete list of permissions and resources available for the product profile. Permissions and resources that have been included in the product profile have been marked with a "✔".  The lists of permissions and resources have been categorized into tabs and columns for easier viewing.

