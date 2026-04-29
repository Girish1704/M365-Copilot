# Exercise 4.1: Reviewing Security and Compliance in Copilot using Sensitivity Labels

## Introduction

**Microsoft Copilot** is designed with security and compliance in mind. It does not store or share any of the user's data. It only uses the data or information that the user explicitly provides as input or context. It also respects the user's privacy and preferences, and does not collect any personal or sensitive information by itself.

Given below are the capabilities from Microsoft Purview which strengthen your data security and compliance for **Microsoft Copilot for Microsoft 365**:

## Task 1: Implementing Sensitivity Labels with Purview 

Sensitivity labels are a way of categorizing and protecting your data based on its level of confidentiality and the impact to your business if it is leaked or misused. You can use sensitivity labels to apply metadata tags and encryption settings to your data sources, columns, tables, and files. Purview is a service that helps you manage and govern your data across your organization.

CoPilot is a system that aids in the management and control of data within an organization. It can work in conjunction with Sensitivity Labels to classify and protect sensitive information. Sensitivity Labels are attributes that can be applied to documents and emails to classify them based on the content sensitivity. These labels can trigger protective actions like encryption or visual markings. Once a sensitivity label is applied to content, it stays with the content regardless of where it's stored or with whom it's shared.

### Understanding Sensitivity labels

Sensitivity labels in Microsoft 365 allow organizations to classify and protect their sensitive content. Here's some information on what these labels represent in Contoso Ltd:

- **Confidential:**
The **Confidential** sensitivity label is used when information is meant to be restricted to a specific group of people within an organization. This label is typically used for data such as employee records, internal policies, or strategic plans. Unauthorized disclosure of this information can lead to potential damage to the organization, but not to the same extent as that classified as **Highly Confidential**.

- **Highly Confidential:**
The **Highly Confidential** sensitivity label is assigned to the most sensitive information that, if disclosed, could result in severe harm to the organization. This might include trade secrets, legal documents, or personally identifiable information (PII) such as social security numbers, credit card information, or health records. Extra security measures, like encryption, are often applied to these documents to prevent unauthorized access or sharing.

- **Internal:**
The **Internal** sensitivity label is used for information that is not intended for public view but doesn't necessarily contain sensitive data. This could include internal newsletters, meeting minutes, or project plans. This label serves as a reminder to employees that the information should not be shared outside the organization, though its disclosure wouldn't cause significant harm.

- **Public**
The **Public** sensitivity label is applied to information that can be freely shared both inside and outside the organization. This information poses no risk if disclosed and is often intended for public consumption. Examples could include press releases, marketing materials, or public-facing reports.

   >**Note:** Remember, sensitivity labels are a tool for managing and protecting data, but they are most effective when combined with user education about data handling and security best practices.

   >**Note:** Your access has been set to Global Reader, meaning you won't be able to make changes. These instructions are for viewing only, reflecting the read-only access granted in your environment.


### Task 1: How are sensitivity labels created in Microsoft Purview (Read Only)

In this task, you will learn how Purview is used to implement sensitivity labels for your data assets.

>**Note:** You are not expected to perform the following steps. This information is provided solely to give you an understanding of the process of creating and publishing Sensitivity Labels in the Purview portal.

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

### Task 2: Publish sensitivity label (Read Only)

The task aims to provide a streamlined method for publishing sensitivity labels to users. Users are guided through a series of steps within Microsoft Purview, specifically under Label policies. The objective is to make the selected labels, such as Confidential-Finance and Highly-Confidential, available to all users, ensuring consistent and standardized data protection measures.

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

This task has provided a clear walkthrough for implementing sensitivity labels in Microsoft Purview, enabling users to categorize and safeguard data based on confidentiality. The guided steps cover label creation, encryption configuration, content marking, and automated labeling, fostering a strong understanding of data protection. Customization options for watermarks, headers, and footers enhance security measures. Demonstrating practical application, the task integrates sensitivity labels seamlessly into Word documents, emphasizing their importance in real-world scenarios. The subsequent label publishing and application steps ensure consistent and standardized data protection, contributing to a robust organizational data governance framework.


## Using Sensitivity Labels in Microsoft 365 Copilot

**Sensitivity labels** from Microsoft Purview Information Protection let you classify and protect your organization's data, while making sure that user productivity and their ability to collaborate isn't hindered.

Sensitivity labels offer the following capabilities:

1. **Customiable:** Specific to your organization and business needs, you can create categories for different levels of sensitive content in your organization. For example, Personal, Public, General, Confidential, and Highly Confidential.

1. **Clear Text:** Because a label is stored in clear text in the metadata for files and emails, third-party apps and services can read it and then apply their own protective actions, if required.

1. **Persistent**: Because the label is stored in metadata for files and emails, the label stays with the content, no matter where it's saved or stored. The label identification that's unique to your organization becomes the basis for applying and enforcing policies that you configure.

The sensitivity labels that you use to protect your organization's data are recognized and used by **Microsoft Copilot for Microsoft 365** to provide an extra layer of protection. For example, in Microsoft Copilot Graph-grounded chat conversations that can reference data from different types of items, the sensitivity label with the highest priority (typically, the most restrictive label) is visible to users. Similarly, when sensitivity label inheritance is supported by Copilot, the sensitivity label with the highest priority is selected.

If the labels applied encryption from Microsoft Purview Information Protection, Copilot checks the usage rights for the user. Only if the user is granted permissions to copy (the **EXTRACT** usage right) from an item, is data from that item returned by Copilot.

In short, the user that uses **Microsoft Copilot**, cannot access labeled documents where he/she has not been added to the permissions for the label. When the user has been added to the permissions, with either Reviewer or Viewer permission, then the document can also not be accessed.

In summary, **Microsoft 365 Copilot** is more stringent when handling encrypted documents with a sensitivity label. As you will need either custom permissions or at least the Co-author role, sensitive information is safeguarded. Provided, of course, that:

1. you have sensitivity labels employed within the enterprise;
1. you have set the right level of permissions to the labels;
1. you are protecting your most sensitive information using labels.

## Conclusion

In conclusion, the integration of **Sensitivity Labels in Microsoft Copilot** for **Microsoft 365** significantly enhances security and compliance measures. **Sensitivity Labels**, being customizable, allow organizations to tailor categories for different levels of sensitive content, ensuring alignment with specific business needs. The clear text storage of labels in metadata facilitates interoperability with third-party apps and services, enabling them to apply their protective actions if necessary.

In the context of **Microsoft Copilot**, Sensitivity Labels play a crucial role in providing an extra layer of protection. The visibility of the sensitivity label with the highest priority to users in Graph-grounded chat conversations ensures that the most restrictive label is appropriately acknowledged. To maximize the effectiveness of **Microsoft 365 Copilot** in safeguarding sensitive information, it is imperative for organizations to implement sensitivity labels, establish appropriate permissions, and protect their most sensitive data using these labels. This integrated approach ensures a robust security posture and compliance adherence within the **Microsoft 365** environment.


## **Congratulations! you have successfully completed this exercise, please click on next**
