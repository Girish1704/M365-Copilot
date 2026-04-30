# Exercise 4.1: Reviewing Security and Compliance in Copilot using Sensitivity Labels

## Introduction

In this exercise, you will review how sensitivity labels are created and published in **Microsoft Purview**. You will also learn how **Microsoft 365 Copilot** recognizes and respects these labels to protect your organization's data. Sensitivity labels help you classify and secure content based on how sensitive it is, and Copilot uses these labels to control access to protected information.

## Task 1: Implementing Sensitivity Labels with Purview 

Sensitivity labels allow you to categorize and protect your data based on its level of confidentiality. You can apply metadata tags, encryption settings, and content markings to your files and emails using these labels. **Microsoft Purview** is the service that helps you manage and govern data protection across your organization.

When a sensitivity label is applied to content, it stays with that content regardless of where it is stored or with whom it is shared. Copilot works with these labels to classify and protect sensitive information, and can trigger protective actions like encryption or visual markings.

### Understanding Sensitivity labels

Sensitivity labels in Microsoft 365 allow you to classify and protect sensitive content. Below is an overview of the common label types:

- **Confidential:**
This label is used for information that should be restricted to a specific group of people within your organization. Examples include employee records, internal policies, or strategic plans. Unauthorized disclosure of this information could cause damage to your organization.

- **Highly Confidential:**
This label is assigned to the most sensitive information. If disclosed, it could result in severe harm to your organization. Examples include trade secrets, legal documents, or personally identifiable information (PII) such as social security numbers or credit card details. Extra security measures like encryption are often applied to these documents.

- **Internal:**
This label is used for information that is not intended for public view but does not contain highly sensitive data. Examples include internal newsletters, meeting minutes, or project plans. This label reminds you that the information should not be shared outside your organization.

- **Public:**
This label is applied to information that can be freely shared both inside and outside your organization. Examples include press releases, marketing materials, or public-facing reports.

   >**Note:** Sensitivity labels are a tool for managing and protecting data, but they work best when combined with user education about data handling and security best practices.

### Task 1: How sensitivity labels are created in Microsoft Purview

In this task, you will create a sensitivity label in **Microsoft Purview** for your data assets.

1. In a new browser tab, navigate to the **Microsoft 365 admin center** using the following URL:

   ```
   https://admin.microsoft.com/
   ```

1. From the left navigation pane of the **Microsoft 365 admin center**, select **Show all**.

   ![](./media/L1-P1-T1-S7.png)

1. Under Admin centers, select **Microsoft Purview**. A new browser page will open and navigate you to the Microsoft Purview welcome page.  

   ![](./media/mp-07.png)
   
1. If the **Welcome to the New Microsoft Purview portal** popup appears, click on **Get started.**

   ![](./media/ex1-se-app-def-g1.png)

1. From the left navigation pane of **Microsoft Purview**, click on **Solutions (1)**,and select **Information protection (2)**

   ![](./media/adm-cop-3.1-g12.png)
   
1. Under the **Information protection** panel, select **Sensitivity labels (1)**, and select **Turn on now (2)** in the **yellow** information box that indicates **Your organization has not turned on the ability to process content in Office online files that have encrypted sensitivity labels applied and are stored in OneDrive and SharePoint**. Once you do this, there can be a delay for the setting to propagate through the system.

   ![](./media/ex2-se-ap2-def-g3.png)

1. In the **Information Protection** pane, select **Sensitivity labels (1)**, expand **Create (2)**, and then select **Label (3)**.

   ![](./media/adm-cop-3.1-g13.png)

1. Provide a name and description for your label. Select **Next (4)** at the bottom of the page.

   | Setting | Action |
   | -- | -- |
   | **Name** | Enter **Confidential-Finance (1)** |
   | **Display name** | Enter **Confidential-Finance (2)** |
   | **Label priority** | Select **Highest (3)** |
   | **Description for users** | Enter **Confidential-Finance Demo (4)** | 
   
   ![](./media/ex2-se-ap2-def-g4.png)

1. Note the scope of this label. The scope is set to **Files and other data assets**, **Emails** and **Meetings**. Read the description, but don’t change anything. Select **Next** at the bottom of the page.

   ![](./media/cor-se-apt-def-g3.png)

1. On the **Choose protection settings** page, select **Apply content marking (1)** and then click **Next (2)** to continue.

   ![](./media/cor-se-apt-def-g4.png)

   > **Note:** The **Control access** option is not selected in this lab because it requires **Rights Management (Azure RMS / Microsoft Purview Information Protection)** to be enabled and fully configured in the organization. Since RM services may not be activated in the newly created lab tenant, this option is intentionally skipped to avoid configuration or policy enforcement issues. 

1. On the **Content marking** page, take note of the information box at the top of the page. Turn on the **Content marking (1)** and select the check box for **Add a watermark (2)**, **Add a header (3)** and **Add a footer (4)**.

   ![](./media/lab1-image10.png)

1. Under **Add a watermark**, click on **Customize text (1)**. Under **Watermark text**, type **Confidential watermark text (2)** and click on **Save (3)**.

   ![](./media/cor-se-apt-def-g6.png)
  
1. Under **Add a header**, click on **Customize text (1)**. Under **Header text**, type **Confidential Document (2)** and click on **Save (3)**.

   ![](./media/ex2-se-ap2-def-g5.png)

1. Under **Add a footer**, click on **Customize text (1)**. Under **Footer text**, type **Confidential Document (2)** and click on **Save (3)**.

   ![](./media/cor-se-apt-def-g7.png)

   >**Note:** Content markings will be applied to documents, but only headers and footers will be applied to email messages. In other words, watermarks are not applied to emails.

1. The content marking associated with this label includes a watermark. Select **Next** at the bottom of the page.

   ![](./media/L1-P1-T1-S25.png)

1. On the **Auto-labelling for files and emails** page, complete the following:

   - Turn on **Auto-labelling for files and emails (1)**.
   - Select **+ Add condition (2)** and choose **Content contains (3)**.
   - Under **Group name**, select **Add (4)** and choose **Sensitive info type**.
   - In the **Sensitive info type (5)** window, search for **Credit (6)** and select **Credit card number (7)**.
   - Select **Add (8)**, and then choose **Next (9)**.

      ![](./media/autolabeling.png)

      ![](./media/content.png)

      ![](./media/creditcardnumber.png)

      ![](./media/next.png)

      >**Note:** If you did not find sensitive info type groups as mentioned, navigate back to the labels page and ensure that the features have been enabled as specified.

1. This next window defines protection settings for groups and sites to which this label applied. Select **Next** at the bottom of the page.

   ![](./media/ex2-se-ap2-def-g6.png)

1. Review the settings and click on the **Create label**.

   ![](./media/adm-cop-3.1-g14.png)

1. On the **Your sensitivity label that was created** blade, select **Don't create a policy yet (1)** and click **Done (2)**.

   ![](./media/cor-se-apt-def-g5.png)

1. Back on the **labels** blade, notice the newly created sensitivity labels.

   ![](./media/L1-P1-T1-S31.png)

### Task 2: Publish sensitivity label

In this task, you will review the steps to publish a sensitivity label to users. By publishing a label through a label policy in **Microsoft Purview**, you make it available to all users in your organization. This ensures that data protection is applied consistently.

1. In the **Microsoft Purview portal**, under **Sensitivity labels** from the panel and click on **Publish label**.

   ![](./media/adm-cop-3.1-g15.png)

1. On the **Create policy** page, select **Choose sensitivity labels to publish**, and then select the required labels.

   ![](./media/adm-cop-3.1-g16.png)

1. In the **Sensitivity labels to publish** pane, select **Confidential-Finance (1)**, and then click **Add (2)**.

   ![](./media/adm-cop-3.1-g17.png)

1. Back on **Choose sensitivity labels to publish** blade, click on **Next**.

   ![](./media/adm-cop-3.1-g18.png) 

1. Click on **Next** on the Assign Admin Units page.

   ![](./media/cor-se-apt-def-g11.png) 

1. Read the description under **Publish to users and groups**. Notice that this label is available to all users; don’t change any settings. Select **Next** at the bottom of the page.

   ![](./media/cor-se-apt-def-g12.png)  

1. Under the policy settings, don’t change any settings. Select **Next** at the bottom of the page.

   ![](./media/cor-se-apt-def-g13.png) 

1. Under the **Apply a Default label to documents**, don’t change any settings. Select **Next** at the bottom of the page.

   ![](./media/cor-se-apt-def-g14.png) 

1. Under the **Apply a Default label to emails**, don’t change any settings. Select **Next** at the bottom of the page.

   ![](./media/cor-se-apt-def-g15.png)  

1. Under the **Apply a default label to meetings and calendar events**, don’t change any settings. Select **Next** at the bottom of the page.    

   ![](./media/cor-se-apt-def-g16.png)   

1. Under the **Apply a default label to Fabric and Power BI content**, don’t change any settings. Select **Next** at the bottom of the page.

   ![](./media/cor-se-apt-def-g17.png) 

1. The last configuration option is to name your policy. Enter the policy name as **Confidential-Policy (1)**. Select **Next (2)** at the bottom of the page to complete the policy configuration and return to the Information Protection page.

   ![](./media/cor-se-apt-def-g18.png)  

1. Review the settings, click on **Submit**, and then select **Done**.

   ![](./media/adm-cop-3.1-g19.png)   
    
   ![](./media/cor-se-apt-def-g19.png) 

1. In the **Label publishing policies (1)** section under **Policies**, notice the **newly published label policy**.

   ![](./media/mp-09.png) 

In these tasks, you reviewed the process of creating a sensitivity label in Microsoft Purview with content markings (watermark, header, footer) and auto-labeling for credit card numbers. You also reviewed how to publish the label through a label policy to make it available to all users.

## How Sensitivity Labels work with Microsoft 365 Copilot

**Sensitivity labels** from Microsoft Purview Information Protection allow you to classify and protect your organization's data without blocking productivity or collaboration.

Sensitivity labels offer the following capabilities:

1. **Customizable:** You can create categories for different levels of sensitive content based on your organization's needs. For example, Personal, Public, General, Confidential, and Highly Confidential.

1. **Clear Text:** Labels are stored in clear text in the metadata for files and emails. This means third-party apps and services can read the label and apply their own protective actions if needed.

1. **Persistent:** Labels stay with the content no matter where it is saved or stored. The label that is unique to your organization becomes the basis for applying and enforcing the policies you configure.

**Microsoft Copilot for Microsoft 365** recognizes and uses these sensitivity labels to provide an extra layer of protection. For example, in Copilot Graph-grounded chat conversations that reference data from different items, the sensitivity label with the highest priority (the most restrictive label) is visible to you. When sensitivity label inheritance is supported by Copilot, the label with the highest priority is selected.

If a label applies encryption from Microsoft Purview Information Protection, Copilot checks your usage rights. Only if you have permissions to copy (the **EXTRACT** usage right) from an item, will Copilot return data from that item.

This means you cannot access labeled documents through Copilot if you have not been added to the permissions for that label. Even if you have Reviewer or Viewer permission, Copilot will not return the content. You need at least the **Co-author** role or custom permissions for Copilot to access encrypted documents.

To make the most of sensitivity labels with Copilot, make sure that:

1. You have sensitivity labels set up in your organization.
1. You have assigned the correct level of permissions to the labels.
1. You are protecting your most sensitive information using labels.

## Conclusion

In this exercise, you reviewed how sensitivity labels are created and published in **Microsoft Purview**. You learned about the different label types (Confidential, Highly Confidential, Internal, and Public) and how content markings such as watermarks, headers, and footers can be applied. You also learned how **Microsoft 365 Copilot** recognizes sensitivity labels and enforces access controls, ensuring that protected content is only accessible to users with the correct permissions.


## **Congratulations! you have successfully completed this exercise, please click on next**
