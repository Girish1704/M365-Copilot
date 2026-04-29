# Exercise 4.2: Reviewing Security and Compliance in Copilot Using Data Classification (Read Only)

## Introduction

**Microsoft Copilot** is designed with security and compliance in mind. It does not store or share any of the user's data. It only uses the data or information that the user explicitly provides as input or context. It also respects the user's privacy and preferences, and does not collect any personal or sensitive information by itself.

Given below are the capabilities from Microsoft Purview whcih strengthen your data security and compliance for Microsoft Copilot for Microsoft 365:

## Using Data Classification in Microsoft 365 Copilot

**Data classification** plays a critical role in helping businesses organize and safeguard their data. Sorting information by its level of sensitivity — like personally identifiable information or confidential records — lets organizations put in place tailored security measures against unauthorized intrusion and data leaks. Additionally, data classification enables businesses to comply with industry regulations and legal requirements by helping ensure that sensitive information is handled appropriately.

**Data classification** forms the foundation needed for Copilot to function efficiently. By accurately categorizing data, Copilot can provide more precise recommendations, making the classification process faster and more reliable. **Copilot** uses AI and ML technologies to make the categorization of data automated and more efficient. By integrating with existing data management systems, such as SharePoint or OneDrive, Copilot analyses the content of documents and automatically assigns appropriate classification labels. This automation eliminates the need for manual classification, saving time and reducing the risk of human error.

One of the key benefits of Copilot is its ability to learn from user interactions. As users review and validate the classification suggestions Copilot provides, the system becomes more accurate over time, resulting in improved classification outcomes. This iterative learning process ensures that the system aligns with each organization's specific needs and requirements, making it an asset for data management.

### Preparing your data for Copilot

Before deploying Copilot, it is essential to prepare your data to maximize its effectiveness. Consider the following guidelines for effective preparation:

- **Data inventory and analysis:** Conduct a comprehensive inventory of your data and analyze its content to identify patterns and commonalities. This step will help in defining appropriate classification categories and labels.

- **Data cleansing and normalization:** Cleanse and normalize your data by removing duplicates, standardizing formats, removing old or legacy versions and ensuring consistency. This process will improve classification accuracy and optimize Copilot's performance by enabling it to surface accurate data.

- **Engage stakeholders:** Involve key stakeholders, such as legal, compliance and IT teams, in the data preparation process. Their input will ensure the classification process aligns with regulatory requirements and organizational policies.

- **Training and awareness:** Provide training and awareness sessions to users and administrators about the importance of data classification and how to effectively use Copilot. This approach will facilitate a smooth transition and increase user adoption. In addition, utilize organizational change management strategies to champion the process and educate the workforce on how data classification and sanitization can expedite Copilot’s ingestion of the data.

>**Note:** You are not expected to perform the following steps. This information is provided solely to give you an understanding of the process of Data Classification in the Purview portal. Your access has been set to Global Reader, meaning you won't be able to make changes. These instructions are for viewing only, reflecting the read-only access granted in your environment.

### Task 1: Exploring Classifiers in Microsoft Purview

Data classification in Microsoft Purview is organized under the **Information Protection** solution. In this task, you will explore the **Classifiers** page, which is where you can view and manage the different types of classifiers your organization uses to identify sensitive content.

>**Note:** Data classification scans your sensitive content and labeled content before you create any policies. This is called **zero change management**. This lets you see the impact that all the retention and sensitivity labels are having in your environment and helps you start assessing your protection and governance policy needs.

1. Navigate to `https://purview.microsoft.com/` and sign in using the **CloudLabs provided credentials**.

1. In the left navigation pane of the Microsoft Purview portal, expand **Information Protection** **(1)** and select **Classifiers** **(2)**.

    <!-- ![](../labguide/media/purview-classifiers-nav.png) -->

1. On the **Classifiers** page, you will see multiple tabs across the top. Select the **Sensitive info types** tab. This page lists all the sensitive information types available in your tenant — both **built-in** (provided by Microsoft) and any **custom** types created by your organization.

1. Scroll through the list to review common sensitive information types such as **U.S. Social Security Number (SSN)**, and **International Banking Account Number (IBAN)**. Each entry displays the **name**, **publisher** (Microsoft or Custom), and whether it is currently used in any **policies**.

    >**Note:** These sensitive information types are what Copilot and other Microsoft 365 services use behind the scenes to detect and protect sensitive data in your organization's emails, documents, and chats.

1. Use the **Search** bar at the top of the list to search for a specific sensitive information type. For example, type **Credit Card** and observe how the list filters to show matching results.

1. Select any sensitive information type (e.g., **Credit Card Number**) to open its detail panel. Here you can review:

   - **Description** — What the sensitive information type detects.
   - **Patterns** — The detection rules and confidence levels used to identify the data.
   - **Associated policies** — Any DLP or auto-labeling policies currently using this type.

1. Close the detail panel and select the **Trainable classifiers** tab. Trainable classifiers use machine learning to identify content by learning from examples rather than relying on fixed patterns. You will see a list of **built-in classifiers** provided by Microsoft, such as:

   - **Resumes** — Detects resume/CV documents.
   - **Source Code** — Identifies files containing programming source code.
   - **Harassment** — Detects potentially harassing language in communications.
   - **Threat** — Identifies threatening language.

1. Select any trainable classifier to view its details, including the **description** and **status** (e.g., Ready to use). These classifiers can be used in DLP policies, auto-labeling policies, and communication compliance policies.

    >**Note:** In addition to built-in classifiers, organizations can create **custom trainable classifiers** by providing sample content for the classifier to learn from. You will not be creating one in this exercise.

1. Now that you've explored the classifiers, you'll move on to the **Explorers** section to see how classified and labeled content appears across your organization.

### Task 2: Exploring Data Explorer

**Data explorer** gives you a real-time snapshot of all the content in your organization that has been classified — whether through sensitivity labels, retention labels, or sensitive information type detection. This is where you can drill down into specific locations (Exchange, SharePoint, OneDrive, Teams) to see exactly which files and emails have been flagged.

>**Note:** Microsoft has introduced **Data explorer** as the updated experience. The older **Content explorer (classic)** is still available under the Explorers section but may be retired in the future.

1. In the Microsoft Purview portal, expand **Information Protection** **(1)** in the left navigation pane, then select **Explorers** **(2)**, and choose **Data explorer** **(3)**.

    <!-- ![](../labguide/media/purview-data-explorer-nav.png) -->

1. On the Data explorer page, you will see a left pane that organizes content into categories. Expand the following sections to explore what's available:

   - **Sensitive info types** — Lists all sensitive information types that have been detected in your organization's content. Each type shows a **count** of how many items matched. For example, expanding **Credit Card Number** will show you how many documents/emails contain credit card data.

   - **Sensitivity labels** — Lists all sensitivity labels that have been applied to content. For example, you may see labels like **Confidential**, **Highly Confidential**, or **Public**. Expanding a label shows the count of items with that label.

   - **Retention labels** — Lists all retention labels applied to content. These control how long content is retained and when it should be disposed of.

   - **Trainable classifiers** — Lists items detected by trainable classifiers (e.g., resumes, source code).

1. Select any category (e.g., expand **Sensitive info types** > **Credit Card Number**). In the right pane, you will see the **data sources** where matching content was found, such as **Exchange**, **SharePoint**, and **OneDrive**.

1. Select a data source (e.g., **SharePoint**) and drill down through the folder structure. You can navigate through sites, libraries, and folders to locate specific files that were classified.

1. Once you find a file, **double-click** on it to preview its content natively within Data explorer. This allows you to verify that the classification is accurate without needing to download or open the file separately.

    >**Note:** If a document is encrypted, the preview will be disabled to mitigate security risks.

1. At the top of the right pane, notice the **Filter** option. When you're inside a specific location (e.g., a SharePoint site), you can use the filter to search by:

   - **Full site name** (e.g., `https://contoso.onmicrosoft.com/sites/sitename`)
   - **File name** (e.g., `Report_2024.docx`)
   - **File extension** (e.g., `pdf`, `xlsx`)

1. To export a summary of the content currently displayed, select the **Export** button at the top of the pane. This generates a **.csv file** listing all items shown in the current view — useful for compliance auditing or reporting.

    >**Note:** It can take up to **seven days** for counts to be updated in Data explorer, and up to **fourteen days** for files in SharePoint.

### Task 3: Monitoring Labeled Content with Activity Explorer

While Data explorer shows you *what* content is classified, **Activity explorer** shows you *what's happening* to that content — who is interacting with labeled files, what actions they're taking, and whether any policy violations have occurred. It pulls from the Microsoft 365 unified audit logs and presents up to **30 days** of historical activity data.

>**Note:** Make sure **Audit** is turned on before using this in your account. If it's not, you will see a banner at the top of the page with an option to **Turn Audit ON**.

1. In the Microsoft Purview portal, expand **Information Protection** **(1)** in the left navigation pane, then select **Explorers** **(2)**, and choose **Activity explorer** **(3)**.

    <!-- ![](../labguide/media/purview-activity-explorer-nav.png) -->

1. On the Activity explorer page, you will see a chart at the top showing activity volume over time, and a detailed activity list below it. Each entry in the list represents an action taken on labeled or sensitive content.

1. Review the **columns** displayed in the activity list. Key columns include:

   - **Date** — When the activity occurred.
   - **Activity type** — What action was taken (e.g., Label applied, Label changed, File read, File copied).
   - **User** — Who performed the action.
   - **Item** — The file or email that was affected.
   - **Location** — Where the item resides (Exchange, SharePoint, OneDrive, Teams, or Endpoint devices).
   - **Sensitivity label** — The label on the item at the time of the action.

1. Select the **Filter** button to open the filter pane. Activity explorer offers approximately **50 different filters**. Explore some of the most useful ones:

   - **Activity type** — Filter by specific actions such as **Label applied**, **Label removed**, **Label downgraded**, **File copied to clipboard**, **File printed**, or **DLP policy matched**.
   - **Sensitivity label** — Filter to see activity only on items with a specific label (e.g., **Highly Confidential**).
   - **User** — Filter to see all activity performed by a specific user.
   - **Location** — Filter by service (e.g., only SharePoint or only Endpoint devices).
   - **Date range** — Narrow down to a specific time period.

1. In addition to individual filters, Activity explorer provides **predefined filter sets** for common scenarios. Look for these at the top of the filter pane:

   - **Endpoint DLP activities** — Shows all activities detected on endpoint devices (e.g., file copied, file printed, file uploaded).
   - **Sensitivity labels applied, changed, or removed** — Quickly view all labeling actions.
   - **Egress activities** — Shows data leaving the organization (e.g., files copied to USB, uploaded to cloud, sent via email).
   - **DLP policies that detected activities** — Shows all events where a DLP policy was triggered.

    >**Note:** You can also create and save your own **custom filter sets** for scenarios you frequently investigate.

1. Select any individual activity entry in the list to open its **detail panel**. Here you can review the full context of the event, including:

   - The **exact file path** or email subject.
   - The **old and new label** (if a label was changed or downgraded).
   - The **DLP policy** that was matched (if applicable).
   - The **device name** (for endpoint activities).

1. Understanding the types of activities that are tracked helps you assess whether your organization's data protection policies are working effectively. Common activities captured include:

   | Activity Type | Description |
   |---|---|
   | **Label applied** | A sensitivity or retention label was applied to a document or email. |
   | **Label changed** | A label was upgraded, downgraded, or removed. |
   | **Auto-labeling simulation** | An auto-labeling policy simulated what labels would be applied. |
   | **File read** | A labeled file was opened or accessed. |
   | **DLP policy matched** | Content triggered a Data Loss Prevention policy rule. |
   | **File copied to clipboard** | A labeled file's content was copied (endpoint activity). |
   | **File printed** | A labeled document was sent to a printer (endpoint activity). |
   | **File copied to network share** | A labeled file was copied to a network location (endpoint activity). |

    >**Note:** Activity explorer does not monitor retention activities for Exchange. Also, it may take some time for recent activities to appear in the explorer.

## Conclusion

In conclusion, understanding and leveraging the capabilities of **Microsoft Copilot** within the Microsoft 365 ecosystem are crucial steps towards enhancing data security and compliance for organizations. The emphasis on **data classification** forms a cornerstone for efficient functioning of Copilot, enabling it to provide accurate recommendations and automate the categorization process.

By embracing the security and compliance features of **Microsoft Copilot**, organizations can not only streamline data management processes but also adhere to industry regulations and legal requirements. This, in turn, fosters a secure digital environment, safeguarding sensitive information and reinforcing trust in the organization's commitment to privacy and data protection.


## **Congratulations! you have successfully completed this exercise, please click on next**
