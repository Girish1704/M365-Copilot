# Exercise 4.7: Reviewing Security and Compliance in Copilot Using eDiscovery

## Introduction

In this exercise, you will use **Microsoft Purview eDiscovery** to create a case and place a hold on content locations that contain **Microsoft 365 Copilot** interaction data. You will learn how to preserve and search for Copilot prompts and responses stored in user mailboxes.

## Using eDiscovery in M365 Copilot

**Microsoft Purview eDiscovery (Standard)** is a tool that allows you to search and export content across Microsoft 365 services, including **Microsoft 365 Copilot**. You can also place an eDiscovery hold on content locations such as Exchange mailboxes, SharePoint sites, OneDrive accounts, and Microsoft Teams.

When you use **Microsoft Copilot**, your prompts and responses are stored in your mailbox. This data may contain sensitive or confidential information. eDiscovery helps you identify, preserve, collect, review, and export this data for legal, regulatory, or security investigations.

eDiscovery supports searching for Copilot interactions across Word, Excel, PowerPoint, Teams, and other Microsoft 365 apps. You can also filter specifically for Copilot interactions when building your search query.

### Task 1: Create an eDiscovery Case

In this task, you will create a new eDiscovery case in the **Microsoft Purview** portal.

1. In the **Microsoft Purview** portal, select **Solutions (1)** from the left navigation pane, and then choose **eDiscovery (2)**.

    ![](./media/adm-cop-7.7-g1.png)

1. Select **Cases (1)**, and then choose **Create case (2)**.

    ![](./media/adm-cop-7.7-g19.png)

1. Enter the following name in the **Case name (1)** field, and then select **Create (2)**.

    ```
    Copilot Case
    ```

    ![](./media/adm-cop-7.7-g4.png)

### Optional Task: Create an eDiscovery hold

After creating an eDiscovery case, you can place a hold (also called an **eDiscovery hold**) on content locations to preserve content that may be relevant to your investigation. Content locations include Exchange mailboxes, SharePoint sites, OneDrive accounts, and the mailboxes and sites associated with Microsoft Teams and Microsoft 365 Groups, along with **Microsoft 365 Copilot** data.

You can preserve all content in specific locations, or create a query-based hold to preserve only the content that matches your hold query. Another benefit of creating a hold is that you can quickly search the content locations on hold when running searches later.

>**Note:** After you create an eDiscovery hold, it may take up to 24 hours for the hold to take effect.

Follow the steps below to create an eDiscovery hold associated with your case:

1. Select **Hold policies (1)**, and then choose **New policy (2)**.

    ![](./media/adm-cop-7.7-g5.png)

1. Enter the following name in the **Policy name (1)** field, and then select **Create (2)**.

    ```
    CopilotHoldPolicy
    ```

    ![](./media/adm-cop-4.6-g14.png)

1. On the **Choose locations** wizard page, choose the content locations that you want to place on hold.

    - **Exchange mailboxes:** Set the toggle to **On** and then select **Choose users, groups, or teams** to specify the mailboxes to place on hold. Use the search box to find user mailboxes and distribution groups.

    - **SharePoint sites:** Set the toggle to **On** and then select **Choose sites** to specify SharePoint sites and OneDrive accounts to place on hold. Type the URL for each site you want to place on hold.

    - **Exchange public folders:** You can keep this toggle **Off** unless you need to hold public folders.

    >**Note:** When adding Exchange mailboxes or SharePoint sites to a hold, you must select at least one specific mailbox or site. If you set the toggle to **On** but do not select any items, the hold will be created without any content locations.

    Select **Next**.

1. To create a query-based hold for **Microsoft 365 Copilot** interactions, complete the following:

    - In the **Keywords** box, type a query to preserve only the content that matches the query criteria. You can specify keywords, email message properties, or site properties such as file names. You can also use Boolean operators such as **AND**, **OR**, or **NOT**.

    - Select **Add condition** to narrow the query. Each condition adds a clause to the search query. For example, you can specify a date range to preserve only content created within that range.

    - Since Copilot prompts and responses are stored in a user's mailbox, you can retrieve this data by selecting **Add condition > Type > Copilot interactions**.

    Select **Next**.

1. Review your settings, and then select **Submit**.

1. After some time, your eDiscovery hold will be created. Select **Done** and return to the **Hold** page.

1. Select your newly created hold and verify it was created correctly.

## Conclusion

In this exercise, you created an eDiscovery case in **Microsoft Purview** and placed a hold on content locations to preserve Copilot interaction data. You learned how to configure a query-based hold to target Copilot interactions specifically, and how to use eDiscovery to search for and preserve prompts and responses stored in user mailboxes.

## **Congratulations! you have successfully completed this exercise, please click on next**
