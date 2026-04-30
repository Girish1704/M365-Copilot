# Exercise 4.6: Reviewing Security and Compliance in Copilot Using Content Search

## Introduction

In this exercise, you will use the **Content Search** eDiscovery tool in **Microsoft Purview** to search for Copilot interaction data stored in your organization. You will assign the required role group permissions, create and run a content search filtered for Copilot activity, and export the results.

## Using Content Search in Microsoft 365 Copilot

You can use the Content search eDiscovery tool in the **Microsoft Purview compliance portal** to search for in-place content such as email, documents, and instant messaging conversations including the responses with **M365 Copilot** in your organization.

After you run a search, the number of content locations and an estimated number of search results are displayed on the search flyout page. You can quickly view statistics, such as the content locations that have the most items that match the search query. After you run a search, you can preview the results or export them to a local computer.

When a user interacts with **Microsoft Copilot for Microsoft 365** apps (such as Word, PowerPoint, Excel, OneNote, Loop, or Whiteboard), data about these interactions is stored. The stored data includes the user's prompt, how Copilot responded, and information used to ground Copilot's response. **For example**, this stored data provides users with Copilot interaction history in Microsoft Copilot with Graph-grounded chat and meetings in Microsoft Teams. This data is processed and stored in alignment with contractual commitments with your organization’s other content in Microsoft 365. The data is encrypted while it's stored and isn't used to train foundation LLMs, including those used by **Microsoft Copilot for Microsoft 365**.

### Task 1: Assign role permissions and run a Content Search

In this task, you will assign the required role group permissions to your user account, then create and run a content search to find Copilot activity data.

1. Navigate to the Microsoft Purview portal:

   ```
   https://purview.microsoft.com/
   ```

1. In the **Microsoft Purview** portal, in the left navigation pane, click on **Settings (1)**, expand **Roles & scopes (2)** and select **Roles groups (3)**

    ![](./media/d1-e1-seco-g6.png)

1. On **Role groups for Microsoft Purview solutions** window, search and select **Security Administrator (1)** then at the top select **Edit (2)**.

    ![](./media/d1-e1-seco-g7.png)

1. On the **Edit members of the role group** window, select **Choose users (1)**. On the **Choose users** blade, select **<inject key="AzureAdUserEmail"></inject> (2)** and then click **Select (3)**.

     ![](./media/ex1-se-app-def-g13.png)
    
1. On the **Edit members of the role group** page, verify that **ODL_User <inject key="DeploymentID" enableCopy="false"/> (1)** is selected, and then select **Next (2)**.

    ![](./media/d1-e1-seco-g8.png)

1. On the **Review the role group and finish** page, review the details, and then select **Save**.

    ![](./media/d1-e1-seco-g9.png) 

1. On the **You successfully updated the role group** page, select **Done**.

    ![](./media/d1-e1-seco-g10.png) 

1.  Repeat the above **steps 2-7** to assign the following **Role Group** permissions to your user:

    - eDiscovery Manager
    - Compliance Administrator
    - Security Reader
    - Information Protection
    - Information Protection Investigators
    - Information Protection Analysts
    - Information Protection Admins

1. In the **Microsoft Purview** portal, select **Solutions (1)** from the left navigation pane, and then choose **eDiscovery (2)**.

    ![](./media/adm-cop-7.7-g1.png)

1. Select **Content Search (1)**, and then choose **Create a search (2)**.

    ![](./media/adm-cop-7.7-g2.png)

1. Enter the following name in the **Search name (1)** field, and then select **Create (2)**.

    ```
    CopilotSearch
    ```

    ![](./media/adm-cop-4.6-g1.png)

1. In the **Data sources** section, select **Add tenant-wide sources**.

    ![](./media/adm-cop-4.6-g2.png)

1. In the **Manage sources** pane, select all options under **Name (1)**, and then select **Save (2)**.

    ![](./media/adm-cop-4.6-g3.png)

1. In the **Condition builder**, select the **Delete** icon next to the existing keyword condition.

    ![](./media/adm-cop-4.6-g4.png)

1. In the **Condition builder**, select **Add conditions (1)**, and then choose **Item class (2)**.

    ![](./media/adm-cop-4.6-g5.png)

1. In the **Condition builder**, set **Contains any of (1)**, enter **Copilot activity (2)**, and then select the suggested **Copilot activity (3)**.

    ![](./media/adm-cop-4.6-g6.png)

1. In the **Query** pane, select **Run query**.

    ![](./media/adm-cop-4.6-g7.png)

1. In the **Choose search results** pane, select **Statistics (1)**, and then select **Run query (2)**.

    ![](./media/adm-cop-4.6-g8.png)

1. Wait for the search to complete, and then review the results in the **Statistics** tab.

    ![](./media/adm-cop-4.6-g9.png)

    > **Note:** The search may take 5 to 10 minutes to complete.

### Task 2: Export and download the report

After a content search is successfully run, you can export the search report to your local computer. The report files are downloaded to a folder with the same name as the content search, appended with **_ReportsOnly**.

Follow the steps below to export and download the content search report:

1. In the **CopilotSearch** page, select **Export**.

    ![](./media/adm-cop-4.6-g10.png)

1. In the **Export** pane, enter **CopilotActivityExport** in **Export name (1)**, keep the default options, and then select **Export (2)**.

    ![](./media/adm-cop-4.6-g11.png)

1. In the **Exports** tab, select **CopilotActivityExport (2)**.

    ![](./media/adm-cop-4.6-g12.png)

1. In the **CopilotActivityExport** pane, select **Download**.

    ![](./media/adm-cop-4.6-g13.png)

## Conclusion

In this exercise, you assigned the required role group permissions, created a content search in **Microsoft Purview** to find Copilot interaction data, and exported the results. Content Search allows you to locate and review Copilot prompts and responses stored across your Microsoft 365 environment, helping you meet compliance and investigation requirements.

## **Congratulations! you have successfully completed this exercise, please click on next**
