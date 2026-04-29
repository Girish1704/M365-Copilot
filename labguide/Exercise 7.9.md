# Exercise 4.8: Reviewing Security and Compliance in Copilot using Retention Policies (Read Only)

## Introduction

**Microsoft Copilot** is designed with security and compliance in mind. It does not store or share any of the user's data. It only uses the data or information that the user explicitly provides as input or context. It also respects the user's privacy and preferences, and does not collect any personal or sensitive information by itself.

Given below are the capabilities from Microsoft Purview which strengthen your data security and compliance for Microsoft Copilot for Microsoft 365:

## Retention and Deletion in Microsoft 365 Copilot

You can use a retention policy to retain data from messages in **Microsoft Copilot for Microsoft 365**, and delete those messages. Behind the scenes, Exchange mailboxes are used to store data copied from these messages. Data from **Copilot** messages is stored in a hidden folder in the mailbox of the user who runs **Copilot**. This hidden folder isn't designed to be directly accessible to users or administrators, but instead, store data that compliance administrators can search with **eDiscovery tools**.

The Exchange mailbox for retaining **Microsoft Copilot for Microsoft 365** messages has the RecipientTypeDetails attribute of **UserMailbox**, which also stores message data for **Teams** private channels and cloud-based **Teams** users. The copy is retained in a hidden folder named **SubstrateHolds** as a subfolder in the Exchange **Recoverable Items** folder.

After a retention policy is configured for **Microsoft Copilot for Microsoft 365** interactions, a timer job from the Exchange service periodically evaluates items in the hidden mailbox folder where these messages are stored. The timer job typically takes **1-7 days** to run. When these items have expired their retention period, they're moved to the SubstrateHolds folder—another hidden folder that's in every user mailbox to store "soft-deleted" items before they're permanently deleted. After a **retention policy** is configured for **Microsoft Copilot for Microsoft 365**, the paths the content takes depend on whether the retention policy is to retain and then delete, to retain only, or delete only.

The following diagram represents the flow in details:

![](./media/copilotretentionlifecycle.png)

For the two paths in the diagram:

1. **If messages are removed from Copilot**, the message is moved to the SubstrateHolds folder where it remains for at least 1 day. When the retention period expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).

1. **If messages remain in Copilot** after the retention period expires, the message is copied to the SubstrateHolds folder. This action typically takes between 1-7 days from the expiry date. When the message is in the SubstrateHolds folder, it's stored there for at least 1 day, and then the message is permanently deleted the next time the timer job runs (typically between 1-7 days).

>**Note:** Messages stored in mailboxes, including the hidden folders, are searchable by **eDiscovery tools**. Until messages are permanently deleted from the SubstrateHolds folder, they remain searchable by **eDiscovery tools**.

When the retention period expires and copies a message to the SubstrateHolds folder, a delete operation is communicated to the backend service for Copilot, that then relays the same operation to the user app with Copilot. Delays in this communication or caching can explain why, for a short period of time, users continue to see these messages in Copilot.

### Content paths for retain-only retention policy

1. **If messages are removed from Copilot** the message is moved to the SubstrateHolds folder after the retention period expires. This action typically takes between 1-7 days from the expiry date. If the retention policy is configured to retain forever, the item remains there. If the retention policy has an end date for the retention period and it expires, the message is permanently deleted the next time the timer job runs (typically between 1-7 days).

1. **If messages remain in Copilot** after the retention period expires, nothing happens before and after the retention period; the message remains in its original location.

### Content paths for delete-only retention policy

1. **If messages are removed from Copilot** during the retention period, the message is moved to the SubstrateHolds folder. The message is stored in the SubstrateHolds folder for at least 1 day and permanently deleted the next time the timer job runs (typically between 1-7 days).

1. **If messages remain in Copilot** after the retention period expires, the message is copied to the SubstrateHolds folder. This action typically takes between 1-7 days from the expiry date. The message is retained there for at least 1 day and then permanently deleted the next time the timer job runs (typically between 1-7 days).

### Task 1: Creating and Configuring Retenetion Policies

>**Note:** You are not expected to perform the following steps. This information is provided solely to give you an understanding of the process of creating and using Retention Policies in the Purview portal.  Your access has been set to Global Reader, meaning you won't be able to make changes. These instructions are for viewing only, reflecting the read-only access granted in your environment.

A **retention policy** lets you manage the data for your organization by deciding proactively whether to retain content, delete content, or retain and then delete the content very efficiently by assigning the same retention settings at the container level to be automatically inherited by content in that container. For example, retention policies for the location **Teams chats and Copilot interactions** include user prompts to **Microsoft Copilot for Microsoft 365**, and the Copilot responses to users. These messages can be retained and deleted for compliance reasons.

To create a retention policy to for all the interactions with **Microsoft 365 Copilot**, follow the given steps:

1. In the **Microsoft Purview** portal, select **Solutions (1)** from the left navigation pane, and then choose **Data Lifecycle Management (2)**.

    ![](./media/adm-cop-7.7-g7.png)

1. Expand **Policies (1)**, and then select **Retention policies (2)**.

    ![](./media/adm-cop-7.7-g8.png)

1. Select **New retention policy**.

    ![](./media/adm-cop-7.7-g9.png)

1. Enter the following name in the **Name (1)** field, and then select **Next (2)**.

    ```
    CopilotRetentionPolicy
    ```

    ![](./media/adm-cop-7.7-g10.png)

1. On the **Administrative Units** page, click **Next** by keeping the default of **Full directory**.

    ![](./media/adm-cop-7.7-g11.png)

1. On the **Choose the type of retention policy to create** page, select **Static (1)**, and then choose **Next (2)**.

    ![](./media/adm-cop-7.7-g12.png)

1. Deselect all locations, enable **Teams chats (1)** only, and then select **Next (2)**.

    ![](./media/adm-cop-7.7-g14.png)

    >**Note:** By default, all teams and all users are selected, but you can refine this by selecting the **Choose** and **Exclude** options.

1. In the **Retain items for a specific period (1)** dropdown, select **Custom (2)**.

    ![](./media/adm-cop-7.7-g15.png)

1. Set **years (1)** to **1**, select **Delete items automatically (2)**, and then choose **Next (3)**.

    ![](./media/adm-cop-7.7-g16.png)

1. On the **Review and finish** page, review the settings, and then select **Submit**.

    ![](./media/adm-cop-7.7-g17.png)

1. Select **Done**.

    ![](./media/adm-cop-7.7-g18.png)

    >**Note:** When you create and submit a retention policy, it can take up to seven days for the retention policy to be applied.

## Conclusion

In conclusion, the integration of **Retention Policies with Microsoft Copilot for Microsoft 365** plays a crucial role in enhancing security and compliance measures. By utilizing retention policies, organizations can retain, delete, or apply a combination of retention and deletion to Copilot messages. The detailed content paths for various scenarios, such as messages being removed or remaining in Copilot after the retention period, provided clarity on the lifecycle of Copilot messages.

By completing this lab, users are now equipped with the knowledge and skills to leverage retention policies effectively in the context of **Microsoft Copilot**. This ensures that organizations can meet compliance requirements, manage data lifecycle efficiently, and uphold the highest standards of security and privacy within the **Microsoft 365** environment.

## **Congratulations! you have successfully completed this exercise, please click on next**
