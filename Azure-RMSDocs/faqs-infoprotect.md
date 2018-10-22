---
# required metadata

title: FAQs for classification & labeling - AIP
description: Have a question that is specifically about classification and labeling using Azure Information Protection? See if it's answered here. 
author: cabailey
ms.author: cabailey
manager: mbaldwin
ms.date: 09/27/2018
ms.topic: conceptual
ms.service: information-protection
ms.assetid: 4b595b6a-7eb0-4438-b49a-686431f95ddd

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: adhall
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Frequently asked questions about classification and labeling in Azure Information Protection

>*Applies to: [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection), [Office 365](http://download.microsoft.com/download/E/C/F/ECF42E71-4EC0-48FF-AA00-577AC14D5B5C/Azure_Information_Protection_licensing_datasheet_EN-US.pdf)*

Have a question about Azure Information Protection that is specifically about classification and labeling?  See if it's answered here. 

## What can I do with the classification capabilities in Azure Information Protection?

Try our quick start tutorial to see this working in just a few minutes: [Quick start tutorial for Azure Information Protection](infoprotect-quick-start-tutorial.md).

Look out for announcements on the [Enterprise Mobility and Security Blog](https://cloudblogs.microsoft.com/enterprisemobility/?product=azure-information-protection) and our [Yammer site](https://www.yammer.com/askipteam/#/threads/inGroup?type=in_group&feedId=8652489&view=all) for when additional classification features and capabilities become available. There are a few limitations with the current release, which include the following:

- No labeling ability in the Office web apps (Office Online).

- No classification and labeling integration with Exchange Online or SharePoint Online.

> [!NOTE]
> **Now in preview**:
> - Centralized reporting for classification and labeling. For more information, see [Central reporting for Azure Information Protection](reports-aip.md).
> - Labeling ability in Office apps for mobile devices (iOS and Android) and Mac computers for customers who are opted-in to the [Office Insider program](https://support.office.com/article/what-is-office-insider-f4208185-b63a-4b68-9c7a-9a32d2411c16). For more information, see [Apply sensitivity labels to your documents and email within Office](https://aka.ms/officemipdocs).


Request new features and vote on requests by visiting the [UserVoice site](https://msip.uservoice.com/) for Azure Information Protection.

## Do I need to be a global admin to configure classification and labels?

With the newly introduced Information Protection Administrator role, this question is now answered on the main FAQ page: [Do you need to be a global admin to configure Azure Information Protection, or can I delegate to other administrators?](faqs.md#do-you-need-to-be-a-global-admin-to-configure-azure-information-protection-or-can-i-delegate-to-other-administrators)

If you select the option to install the demo policy when you install the [Azure Information Protection client](https://www.microsoft.com/en-us/download/details.aspx?id=53018), you don't need to sign in to the portal to see and try out the labeling functionality. The demo policy locally installs a default policy for Azure Information Protection, so you can try labeling documents and emails, but you can't change or add new labels without signing in to the Azure portal. 

## Can a file have more than one classification?

Users can select just one label at a time for each document or email, which often results in just one classification. However, if users select a sublabel, this actually applies two labels at the same time; a primary label and a secondary label. By using sublabels, a file can have two classifications that denote a parent\child relationship for an additional level of control.

For example, the label **Confidential** might contain sublabels such as **Legal** and **Finance**. You can apply different classification visual markings and different Rights Management templates to these sublabels. A user cannot select the **Confidential** label by itself; only one of its sublabels, such as **Legal**. As a result, the label that they see set is **Confidential \ Legal**. The metadata for that file includes one custom text property for **Confidential**, one custom text property for **Legal**, and another that contains both values (**Confidential Legal**). 

When you use sublabels, don't configure visual markings, protection, and conditions at the primary label. When you use sublevels, configure these setting on the sublabel only. If you configure these settings on the primary label and its sublabel, the settings at the sublabel take precedence.

## How do I prevent somebody from removing or changing a label?

Although there’s a [policy setting](configure-policy-settings.md) that requires users to state why they are lowering a classification label, removing a label, or removing protection, this setting does not prevent these actions. To prevent users from removing or changing a label, the content must already be protected and the protection permissions do not grant the user the Export or Full Control [usage right](configure-usage-rights.md). 

## When an email is labeled, do any attachments automatically get the same labeling?

No. When you label an email message that has attachments, those attachments do not inherit the same label. The attachments remain either without a label or retain a separately applied label. However, if the label for the email applies protection, that protection is applied to Office attachments.

## How can DLP solutions and other applications integrate with Azure Information Protection?

Because Azure Information Protection uses persistent metadata for classification, which includes a clear-text label, this information can be read by DLP solutions and other applications. 

For more information and examples of using this metadata with Exchange Online mail flow rules, see [Configuring Exchange Online mail flow rules for Azure Information Protection labels](configure-exo-rules.md).

## How is Azure Information Protection classification for emails different from Exchange message classification?

Exchange message classification is an older feature that can classify emails and it is implemented independently from Azure Information Protection classification. 

However, you can integrate the two solutions so that when users classify an email by using Outlook on the web and by using some mobile mail applications, the Azure Information Protection classification and corresponding label markings are automatically added. 

You can use this same technique to use your labels with Outlook on the web and these mobile mail applications.

For configuration steps, see [Integrate Exchange message classification with Azure Information Protection for a mobile device labeling solution](./rms-client/client-admin-guide-customizations.md#integration-with-exchange-message-classification-for-a-mobile-device-labeling-solution). 



