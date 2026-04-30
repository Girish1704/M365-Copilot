# Exercise 4.4: Reviewing Security and Compliance in Copilot Using Communication Compliance

## Introduction

In this exercise, you will create a **Communication Compliance** policy in **Microsoft Purview** to detect and monitor interactions with **Microsoft Copilot for Microsoft 365**. You will configure the policy with trainable classifiers and test it to verify that it can identify potentially inappropriate or risky messages.

## Communication Compliance in Microsoft 365 Copilot

**Communication Compliance** is an insider risk solution in Microsoft Purview that helps you detect, capture, and act on potentially inappropriate messages in your organization. You can use pre-defined and custom policies to check internal and external communications for policy matches. Designated reviewers can then investigate flagged messages in email, Microsoft Teams, Microsoft Copilot for Microsoft 365, Viva Engage, or third-party communications and take appropriate actions.

Communication compliance policies help you address challenges such as:

- Monitoring an increasing number of communication channels
- Managing a growing volume of message data
- Meeting regulatory requirements and avoiding fines

### Scenarios for Communication Compliance

Communication compliance policies can help you review messages in several important areas:

- **Corporate policies**: You can check communications for violations of acceptable use, ethical standards, and other corporate policies. For example, you can monitor for harassment or the use of inappropriate language.

- **Risk management**: You can identify and manage potential legal exposure and risk before they affect your operations. For example, you can check messages for unauthorized communications about confidential projects such as upcoming acquisitions or mergers.

- **Regulatory compliance**: You can meet regulatory requirements that require oversight of messaging in your industry. For example, the **Financial Industry Regulatory Authority (FINRA) Rule 3110** requires organizations to have procedures to check user communications.

Communication compliance policies provide a process to analyze and report on corporate communications to help your organization meet these requirements.

### Microsoft Copilot for Microsoft 365

Communication compliance supports **Microsoft Copilot for Microsoft 365**. You can use it to analyze prompts and responses entered into Copilot to detect inappropriate or risky interactions, or the sharing of confidential information.

The following **Copilot apps** are supported:

- Teams (chats/channels/meetings) Copilot
- Word Copilot
- PowerPoint Copilot
- Excel Copilot
- OneNote Copilot
- Loop Copilot
- Whiteboard Copilot
- Microsoft 365 Chat in Teams
- Microsoft 365 Chat in Bing

Any prompt or response entered into a supported Copilot app that matches a communication compliance policy is displayed as a policy match on the **Policies** page under the **Pending** tab. Prompts and responses are shown as separate entries. If only the prompt or only the response matches a policy, an item is created on the **Pending** tab for that match only. You can remediate policy matches for Copilot the same way you remediate any other policy match.

![](./media/communication-compliance.png)

The following information is displayed for each item on the **Pending** tab for Copilot policy matches:

- **Copilot icon:** The Copilot icon identifies the policy match as a Copilot interaction.
- **Subject column:** The value in this column identifies the policy match as a Copilot interaction and lists the name of the app that was used. For example: "Copilot in Excel".
- **Sender column:** Sender of the message. If the policy match is a response from Copilot, the value is "Copilot".
- **Recipient column:** Recipients included in the message. If the policy match is a prompt to Copilot, the value is "Copilot".
- **Message text:** The message text that the user entered (the text that caused the policy match) is shown on the right side of the screen in its entirety.

### Task 1: Create a Communication Compliance policy for Microsoft Copilot

In this task, you will create a communication compliance policy to detect Microsoft Copilot interactions. Follow the steps below:

1. In the **Microsoft Purview** portal, in the left navigation pane, select **Solutions (1)**, and then choose **Communication Compliance (2)**.

    ![](./media/adm-cop-7.3-g4.png)

1. In the **Communication Compliance** page, select **Policies (1)**, and then choose **Create policy (2)**.

    ![](./media/adm-cop-7.3-g5.png)

1. From the **Create policy** dropdown, select **Detect Microsoft Copilot interactions**.

    ![](./media/adm-cop-7.3-g6.png)

1. In the **Detect Microsoft Copilot interactions** page, select **All users (1)**, enter **ODL_User <inject key="DeploymentID" enableCopy="false"/> (2)** under Reviewers, and then select the suggested user **(3)**.

    ![](./media/adm-cop-7.3-g7.png)

1. In the **Detect Microsoft Copilot interactions** page, verify the **Reviewers** field, and then select **Add trainable classifiers**.

    ![](./media/adm-cop-7.3-g8.png)

1. In the **Add trainable classifiers** pane, select all classifiers using the checkbox **(1)**, and then choose **Add (2)**.

    ![](./media/adm-cop-7.3-g9.png)

1. In the **Detect Microsoft Copilot interactions** page, review the selected classifiers, and then select **Create policy**.

    ![](./media/adm-cop-7.3-g10.png)

1. On the **Your policy was created** page, select **Close**.

    ![](./media/adm-cop-7.3-g11.png)

    >**Note:** It might take upto 24 hours to activate your policy.

1. In the **Policies** list, select the **More actions (1)** icon for your policy, and then choose **Test policy conditions (2)**.

    ![](./media/adm-cop-7.3-g12.png)

1. In the **Test policy conditions** pane, select **Enter messages to test (1)**, enter the following message **(2)**, and then choose **Test (3)**.

    ```
    Let’s coordinate buying shares to push the stock price up, Spread positive rumors to influence investor behavior, Plan to sell once the price is artificially inflated, Work together to manipulate trading volume for quick gains.
    ```

    ![](./media/adm-cop-7.3-g13.png)

1. Note that the policy results may not appear immediately, as newly created policies can take up to 24 hours to start detecting and displaying matches.

## Conclusion

In this exercise, you created a **Communication Compliance** policy in **Microsoft Purview** to detect interactions with **Microsoft Copilot for Microsoft 365**. You configured trainable classifiers to identify potentially risky messages and tested the policy conditions to verify that it works as expected. Communication compliance helps you monitor Copilot interactions across supported apps and take corrective actions when policy violations are detected.


## **Congratulations! you have successfully completed this exercise, please click on next**
