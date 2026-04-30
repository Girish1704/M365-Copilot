# Exercise 3.4: Administering M365 Copilot

This exercise is designed to provide a comprehensive understanding of how to effectively administer and manage the AI-powered **Microsoft Copilot** in a **Microsoft 365** environment through the **Microsoft 365 Admin Center**. Understanding these operations is crucial for the efficient utilization and management of Copilot in your organization. You will delve into the administrative side of **Microsoft Copilot**, exploring how to configure, manage, and optimize it for an organization's specific needs, equipping you with the knowledge and skills needed to maximize the benefits of this powerful tool in your organization.

## Change update channel of Microsoft 365 Apps to enable Copilot

One of the benefits of Microsoft 365 Apps is that Microsoft provides new (and updated) features for Office apps, such as Excel and Word, regularly. You can control how often the users in your organization get these new features by specifying the update channel. In addition to new features, update channels provide, as needed, security and non-security updates regularly, every month. Non-security updates provide fixes for known issues and provide stability or performance improvements for Office.

**Contoso Ltd**, a leading IT Consultancy firm, has decided to opt for the Monthly Enterprise Channel for their **Microsoft 365 Apps**. This decision was taken after a thorough assessment of the company’s needs and understanding the benefits of the Monthly Enterprise Channel. **Contoso Ltd.** is a dynamic organization that requires regular updates to keep their operations running smoothly and securely, but also needs stability and predictability in their software environment. The Monthly Enterprise Channel perfectly fits their needs as it provides new features, security and non-security updates on a predictable monthly schedule. Contoso appreciates the fact that these updates occur only once a month, allowing their IT team to plan and manage these updates efficiently. Furthermore, the Monthly Enterprise Channel offers Contoso a good balance between receiving the latest updates and having a stable, secure software environment.

In addition to the Monthly Enterprise Channel, Contoso Ltd has also decided to utilize Cloud updates as its management solution. This strategic decision is aimed at maximizing the benefits of cloud-based technologies in their software management processes. With Cloud updates, Contoso can enjoy a more streamlined, efficient, and automated update process. This solution reduces the manual intervention required from the IT team, freeing them up to focus on more strategic tasks. Cloud updates provide real-time access to the latest updates, ensuring that Contoso's Microsoft 365 Apps are always up-to-date with the latest features and security patches. Moreover, the cloud-based solution allows Contoso to manage updates across multiple devices and locations seamlessly, a feature that is particularly beneficial for a global corporation like Contoso Ltd.

### Task 1: Enable Cloud Update

1. A Microsoft Entra ID security group is required to target the channel change. In this lab, a security group named **Copilot Users** has already been created for you.

1. Navigate to the **Microsoft 365 Apps admin center** using the URL below and sign in with your admin credentials.

    ```
    https://config.office.com
    ```

1. You should land on the **Home** page automatically. On the **Recommendation based on your tenant** card, select **Enable cloud**.

    ![](../labguide/media/channel1.1.png)

1. Wait a moment and refresh the page. Verify that the **Monthly Enterprise** entry is listed under the **Cloud Update** navigation on the left.

1. Navigate back to the **Home** page and select **Finish enabling cloud** to activate the **Current Channel** profile as well.

1. Wait a moment and refresh the page again. Verify that both the **Monthly Enterprise** entry and the **Current** entry are listed under the **Cloud Update** navigation.

    ![](../labguide/media/channel1.2.png)

### Task 2: Initiate a channel change

1. While staying in the **Microsoft 365 Apps admin center**, navigate to **Inventory** and select **Show all devices**.

    ![](../labguide/media/channel1.3.png)

1. Select the **Switch device update channel** button at the top. You can enter device names or Microsoft Entra ID groups, or a mix of both. In this case, select your security group **Copilot Users**.

    ![](../labguide/media/channel1.4.png)

1. Select **Move devices** to initiate the channel change.

    ![](../labguide/media/channel1.5.png)

    >**Note:** It might take up to 24 hours for the channel change to be completed on the device, assuming devices are online and can connect to the service. A channel change is a one-time activity. If you add devices or users to the group after initiating the change, those devices will not be moved automatically and you will need to initiate the channel change again.

## Conclusion

In this exercise, you enabled **Cloud Update** in the **Microsoft 365 Apps admin center** and initiated a channel change for your devices. Cloud Update provides an automated update experience that keeps your Microsoft 365 Apps on a supported update channel for **Microsoft 365 Copilot**. You also learned that the channel change can target individual devices or Microsoft Entra ID security groups.

## **Congratulations! you have successfully completed this exercise, please click on next**
