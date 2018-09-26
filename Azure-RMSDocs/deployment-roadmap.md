---
# required metadata

title: Azure Information Protection deployment roadmap
description: Use these steps to prepare for, implement, and manage Azure Information Protection for your organization.
author: cabailey
ms.author: cabailey
manager: mbaldwin
ms.date: 03/05/2018
ms.topic: conceptual
ms.service: information-protection
ms.assetid: 086600c2-c5d8-47ec-a4c0-c782e1797486

# optional metadata

#ROBOTS:
#audience:
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Azure Information Protection deployment roadmap

>*Applies to: [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection), [Office 365](http://download.microsoft.com/download/E/C/F/ECF42E71-4EC0-48FF-AA00-577AC14D5B5C/Azure_Information_Protection_licensing_datasheet_EN-US.pdf)*

Use the following steps as recommendations to help you prepare for, implement, and manage Azure Information Protection for your organization.

However, if you just want to quickly try Azure Information Protection for yourself, rather than roll it out in a production environment, see [Quick start tutorial for Azure Information Protection](./infoprotect-quick-start-tutorial.md).

> [!IMPORTANT]
> Before you do the following steps, make sure that you have reviewed [Requirements for Azure Information Protection](./requirements.md).

Choose the deployment roadmap that's applicable for your organization and that matches the [subscription functionality and features](https://azure.microsoft.com/pricing/details/information-protection/) that you need:

- [Use classification, labeling, and protection](#deployment-roadmap-for-classification-labeling-and-protection)

- [Use data protection only](#deployment-roadmap-for-data-protection-only)


## Deployment roadmap for classification, labeling, and protection

> [!NOTE]
> Already using the protection functionality from Azure Information Protection? You can skip many of these steps and focus on steps 3 and 5.1.

### Step 1: Confirm your subscription and assign user licenses
Review the subscription information and feature list from the [Azure Information Protection Pricing](https://azure.microsoft.com/pricing/details/information-protection) page to confirm that your organization has a subscription that includes the functionality and features that you expect. Then, assign a license from this subscription to each user in your organization who will classify, label, and protect documents and emails.

Note: Do not manually assign user licenses from the free RMS for individuals subscription and do not use this license to administer the Azure Rights Management service for your organization. These licenses display as **Rights Management Adhoc** in the Office 365 admin center, and **RIGHTSMANAGEMENT_ADHOC** when you run the Azure AD PowerShell cmdlet, [Get-MsolAccountSku](https://msdn.microsoft.com/library/azure/dn194118.aspx). For more information about how the RMS for individuals subscription is automatically granted and assigned to users, see [RMS for individuals and Azure Information Protection](./rms-for-individuals.md).


### Step 2: Prepare your tenant to use Azure Information Protection
Before you begin using Azure Information Protection, do the following preparation:

- Make sure that you have user accounts and groups in Office 365 or Azure Active Directory that will be used by Azure Information Protection to authenticate and authorize users from your organization. If necessary, create these account and groups, or synchronize them from your on-premises directory. For more information, see [Preparing users and groups for Azure Information Protection](prepare.md).

### Step 3: Configure and deploy classification and labeling

If you do not already have a classification strategy, review the [default Azure Information Protection policy](./configure-policy-default.md) and use this as the basis for deciding what classification labels to assign to your organization data. You can customize these to meet your business requirements. 

Reconfigure the default Azure Information Protection labels to make any changes you need to support your classification decisions. Configure the policy for manual labeling by users, and write user guidance that explains which label to apply and when. If your default policy was created with labels that automatically apply protection, remove the protection settings or disable the label. For more information about how to configure Azure Information Protection policy, see [Configuring Azure Information Protection policy](./configure-policy.md).

Then deploy the Azure Information Protection client for users, and support it by providing user training and your instructions for when to select the labels. For more information about installing and supporting the client, see the [Azure Information Protection client administrator guide](./rms-client/client-admin-guide.md).

After a period of time, when users are comfortable labeling their documents and emails, introduce more advanced configurations. These might include the following:

- Apply a default label

- Prompt users for justification if they chose a label with a lower classification level

- Mandate that all documents and emails have a label

- Customized headers, footers, or watermarks

- Conditions to support recommendations and automatic labeling

At this stage, do not select the option to protect documents and emails.

### Step 4: Prepare for data protection

When users are comfortable labeling documents and emails, you're ready to start introducing data protection for your most sensitive data. This stage requires the following preparation:

1. Decide whether you want Microsoft to manage your tenant key (the default), or generate and manage your tenant key yourself (known as bring your own key, or BYOK). For more information, see [Planning and implementing your Azure Information Protection tenant key](plan-implement-tenant-key.md).

2. Install the PowerShell module for AADRM on at least one computer that has Internet access. You can do this step now, or later. For more information, see [Installing the AADRM PowerShell module](./install-powershell.md).

3. If you are currently using AD RMS: Perform a migration to move the keys, templates, and URLs to the cloud. For more information, see [Migrating from AD RMS to Information Protection](migrate-from-ad-rms-to-azure-rms.md).

4. Make sure that the protection service is activated so that you can begin to protect documents and emails. If a phased deployment is required, configure user onboarding controls to restrict usage to specific users. For more information, see [Activating Azure Rights Management](./activate-service.md).

Optionally, consider configuring the following:

-   Custom templates for protection settings if the default templates are not sufficient for your organization. You can do this step now, or later. For more information, see [Configuring and managing templates for Azure Information Protection](./configure-policy-templates.md).

-   Usage logging so that you can monitor how your organization is using the protection service. You can do this step now, or later. For more information, see [Logging and analyzing usage of the Azure Rights Management service](./log-analyze-usage.md).

### Step 5: Configure your Azure Information Protection policy, applications, and services for data protection

1. Update your Azure Information Protection policy to apply data protection
    
    Modify your Azure Information Protection policy so that one or more labels apply protection. For more information, see [How to configure a label for Rights Management protection](./configure-policy-protection.md).
    
    Note that users can apply labels in Outlook that apply Rights Management protection even if Exchange is not configured for information rights management (IRM). However, until Exchange is configured for IRM or [Office 365 Message Encryption with new capabilities](https://support.office.com/article/7ff0c040-b25c-4378-9904-b1b50210d00e), your organization will not get the full functionality of using Azure Rights Management protection with Exchange. This additional configuration is included in the following list (2 for Exchange Online, and 5 for Exchange on-premises). 

2. Configure Office applications and services
    
    Configure Office applications and services for the information rights management (IRM) features in SharePoint Online or Exchange Online. For more information, see [Configuring applications for Azure Rights Management](./configure-applications.md).

3. Configure the super user feature for data recovery
    
    If you have existing IT services that need to inspect files that Azure Information Protection will protect—such as data leak prevention (DLP) solutions, content encryption gateways (CEG), and anti-malware products—configure the service accounts to be super users for Azure Rights Management. For more information, see [Configuring super users for Azure Rights Management and discovery services or data recovery](./configure-super-users.md).

4. Classify and protect files in bulk - as needed
    
    The PowerShell cmdlets that let you classify and protect files, as well as remove classification and protection, are automatically installed with the Azure Information Protection client. For more information, see [Using PowerShell with the Azure Information Protection client](./rms-client/client-admin-guide-powershell.md) from the admin guide.

6. Deploy the connector for on-premises servers
    
    If you have on-premises services that you want to use with the protection service, install and configure the Rights Management connector. For more information, see [Deploying the Azure Rights Management connector](./deploy-rms-connector.md).

### Step 6: Use and monitor your data protection solutions
You’re now ready to protect your data, and log how your company is using the labels that you've configured and the data protection. For addition information to support this deployment phase, see the following:

- [Reporting for Azure Information Protection](reports-aip.md)

- [Helping users to protect files by using the Azure Rights Management service](./help-users.md)

- [Logging and analyzing usage of the Azure Rights Management service](./log-analyze-usage.md)

- [Client files and usage logging](./rms-client/client-admin-guide-files-and-logging.md)

If you're interested in automatically protecting files using File Classification Infrastructure on a Windows-based file server, see [RMS protection with Windows Server File Classification Infrastructure (FCI)](./rms-client/configure-fci.md).

### Step 7: Administer the protection service for your tenant account as needed
As you begin to use the protection service, you might find PowerShell useful to help script or automate administrative changes. For more information, see [Administering the Azure Rights Management service by using Windows PowerShell](./administer-powershell.md).


## Deployment roadmap for data protection only

### Step 1: Confirm that you have a subscription that includes the protection service from Azure Information Protection
Review the subscription information and feature list from the [Azure Information Protection Pricing](https://azure.microsoft.com/pricing/details/information-protection) page to confirm that your organization has a subscription that includes the functionality and features that you expect. Then, assign a license from this subscription to each user in your organization who will protect documents and emails.

Note: Do not manually assign user licenses from the free RMS for individuals subscription and do not use this license to administer the Azure Rights Management service for your organization. These licenses display as **Rights Management Adhoc** in the Office 365 admin center, and **RIGHTSMANAGEMENT_ADHOC** when you run the Azure AD PowerShell cmdlet, [Get-MsolAccountSku](https://msdn.microsoft.com/library/azure/dn194118.aspx). For more information about how the RMS for individuals subscription is automatically granted and assigned to users, see [RMS for individuals and Azure Information Protection](./rms-for-individuals.md).


### Step 2: Prepare your tenant to use Azure Information Protection
Before you begin using the protection service from Azure Information Protection, do the following preparation:

1.  Make sure that your Office 365 tenant contains the user accounts and groups that will be used by Azure Information Protection to authenticate and authorize users from your organization. If necessary, create these account and groups, or synchronize them from your on-premises directory. For more information, see [Preparing users and groups for Azure Information Protection](prepare.md).

2. Decide whether you want Microsoft to manage your tenant key (the default), or generate and manage your tenant key yourself (known as bring your own key, or BYOK). For more information, see [Planning and implementing your Azure Information Protection tenant key](plan-implement-tenant-key.md).

3. Install the PowerShell module for AADRM on at least one computer that has Internet access. You can do this step now, or later. For more information, see [Installing the AADRM PowerShell module](./install-powershell.md).

4. If you are currently using AD RMS: Perform a migration to move the keys, templates, and URLs to the cloud. For more information, see [Migrating from AD RMS to Azure Information Protection](migrate-from-ad-rms-to-azure-rms.md).

5. Make sure that the protection service is activated so that you can begin to protect documents and emails. If a phased deployment is required, configure user onboarding controls to restrict usage to specific users. For more information, see [Activating Azure Rights Management](./activate-service.md).

Optionally, consider configuring the following:

-   Custom templates for protection settings if the default templates are not sufficient for your organization. You can do this step now, or later. For more information, see [Configuring and managing templates for Azure Information Protection](./configure-policy-templates.md).

- Usage logging so that you can monitor how your organization is using the protection service. You can do this step now, or later. For more information, see [Logging and analyzing usage of the Azure Rights Management service](./log-analyze-usage.md).

### Step 3: Install the client and configure applications and services for Rights Management

1. Deploy the Azure Information Protection client
    
    Install the Azure Information Protection for users, to support Office 2010, to protect files other than Office documents and emails, and to track protected documents. Provide user training for this client. For more information, see [Azure Information Protection client for Windows](./rms-client/aip-client.md).

2. Configure Office applications and services
    
    Configure Office applications and services for the information rights management (IRM) features in SharePoint Online or Exchange Online. For more information, see [Configuring applications for Azure Rights Management](./configure-applications.md).

3. Configure the super user feature for data recovery
    
    If you have existing IT services that need to inspect files that Azure Information Protection will protect—such as data leak prevention (DLP) solutions, content encryption gateways (CEG), and anti-malware products—configure the service accounts to be super users for Azure Rights Management. For more information, see [Configuring super users for Azure Rights Management and discovery services or data recovery](./configure-super-users.md).

4. Protect files in bulk - as needed 
    
    The PowerShell cmdlets that let you bulk protect or bulk unprotect multiple file types are automatically installed with the Azure Information Protection client. For more information, see [Using PowerShell with the Azure Information Protection client](./rms-client/client-admin-guide-powershell.md) from the admin guide.

5. Deploy the connector for on-premises servers
    
    If you have on-premises services that you want to use with the protection service, install and configure the Rights Management connector. For more information, see [Deploying the Azure Rights Management connector](./deploy-rms-connector.md).


### Step 4: Use and monitor your data protection solutions
You’re now ready to protect your data, and log how your company is using the protection service. For addition information to support this deployment phase, see [Helping users to protect files by using the Azure Rights Management service](./help-users.md) and [Logging and analyzing usage of the Azure Rights Management service](./log-analyze-usage.md).

If you're interested in automatically protecting files using File Classification Infrastructure on a Windows-based file server, see [RMS protection with Windows Server File Classification Infrastructure (FCI)](./rms-client/configure-fci.md).

### Step 5: Administer the protection service for your tenant account as needed
As you begin to use the protection service, you might find PowerShell useful to help script or automate administrative changes. For more information, see [Administering the Azure Rights Management service by using Windows PowerShell](./administer-powershell.md).

