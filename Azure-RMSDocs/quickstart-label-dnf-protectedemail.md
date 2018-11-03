---
title: Quickstart - Configure a label for users to easily protect emails that contain sensitive information
description: Configure a label that protects an email for a user by automatically applying the Do Not Forward protection.
author: cabailey
author: cabailey
ms.author: cabailey
manager: mbaldwin
ms.date: 11/05/2018
ms.topic: quickstart
ms.service: information-protection

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
#ms.reviewer: demizets
#ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:
#Customer intent: As an administrator, I want to make it easy for users to protect their emails that contain sensitive information.
---

# Quickstart: Configure a label for users to easily protect emails that contain sensitive information

In this quickstart, you'll configure an existing label to automatically apply the Do Not Forward protection setting.

The current Azure Information Protection policy already contains two labels that have this configuration:

- **Confidential \ Recipients Only**

- **Highly Confidential \ Recipients Only**

However, if your policy is older, or if protection wasn't activated at the time your organization's policy was created, you won't have these labels. 

You can finish this configuration in 5 minutes.

## Prerequisites

To complete this quickstart, you need:

1. A subscription that includes Azure Information Protection Plan 1 or Plan 2.
    
    If you don't have one of these subscriptions, you can create a [free](https://portal.office.com/Signup/Signup.aspx?OfferId=87dd2714-d452-48a0-a809-d2f58c4f68b7) account for your organization.

2. You've added the Azure Information Protection blade to the Azure portal, and confirmed that the protection service is activated.

    If you need help with these actions, see [Quickstart: Get started in the Azure portal](quickstart-viewpolicy.md).

3. An existing Azure Information Protection label to configure. 
    
    You can use one of the default labels, or a label that you've created. If you need help creating a new label, see [Quickstart: Create a new Azure Information Protection label for specific users](quickstart-label-specificusers.md).

4. To test the new label: The Azure Information Protection client must be installed on computers for users. 
    
    To try the label for yourself, you can install the client by going to the [Microsoft download center](https://www.microsoft.com/en-us/download/details.aspx?id=53018) and download **AzInfoProtection.exe** from the Azure Information Protection page.

For a full list of prerequisites for the service, see [Requirements for Azure Information Protection](requirements.md).

## Configure an existing label to apply the Do Not Forward protection

1. Open a new browser window and [sign in to the Azure portal](https://portal.azure.com). Then navigate to **Azure Information Protection**. 
    
    For example, on the hub menu, click **All services** and start typing **Information** in the Filter box. Select **Azure Information Protection**.

2. From the **Classifications** > **Labels** menu option: On the **Azure Information Protection - Labels** blade, select the label you want to configure to apply the protection. 

3. On the **Label** blade, locate **Set permissions for documents and emails containing this label**. Select **Protect**, and then **Protection**:
    
    ![Configure protection for an Azure Information Protection label](./media/info-protect-protection-bar-configured.png).

4. On the **Protection** blade, make sure that **Azure (cloud key)** is selected.
    
5. Select **Set user-defined permissions (Preview)**.

6. Make sure that the following option is selected: **In Outlook apply Do Not Forward**.

7. If selected, clear the following option: **In Word, Excel, PowerPoint and File Explorer prompt user for custom permissions**.

8. Click **OK** on the **Protection** blade, and then click **Save** on the **Label** blade.

Your label is now configured to display in Outlook only, and apply the Do Not Forward protection to emails.

## Test your new label

Your configured label displays only in Outlook and is suitable for emails sent to any recipient outside your organization when Exchange Online is configured for the [new capabilities in Office 365 Message Encryption](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e).

1. On your computer, open Outlook and create a new email message. If Outlook is already open, restart it to force a policy refresh.

2. Specify the recipients, some text for the email message, and then apply the label that you just created. 
    
    The email message is classified according to the label name, and protected with the Do Not Forward restriction. 

3. Send the email. 

The result is that recipients cannot forward the email, or print it, copy from it, or save attachments, or save the email as a different name. The protected email message can be read by any user, on any device.

## Clean up resources

Do the following if you do not want to keep this configuration and return your label such that it doesn't apply protection:

1. From the **Classifications** > **Labels** menu option: On the **Azure Information Protection - Labels** blade, select the label you configured. 

3. On the **Label** blade, locate **Set permissions for documents and emails containing this label**, select **Not configured**, and select **Save**.

## Next steps

This quickstart includes the minimum options so that you can quickly configure a label that makes it easy for users to protect their emails. However, if the configuration is too restrictive, or not restrictive enough, see the other example configurations:

- [Label for protected email that supports less restrictive permissions than Do Not Forward](configure-policy-protection.md#example-4-label-for-protected-email-that-supports-less-restrictive-permissions-than-do-not-forward)

- [Label that encrypts content but doesn't restrict who can access it](configure-policy-protection.md#example-5-label-that-encrypts-content-but-doesnt-restrict-who-can-access-it)

For full instructions how to configure a label that applies protection, see [How to configure a label for Rights Management protection](configure-policy-protection.md). 
