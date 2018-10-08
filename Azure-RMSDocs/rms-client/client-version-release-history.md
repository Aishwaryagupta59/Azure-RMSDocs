---
# required metadata

title: Azure Information Protection client - Version release history and support policy
description: See what's new or changed in a release of the Azure Information Protection client for Windows, and understand the lifecycle policy for support. 
author: cabailey
ms.author: cabailey
manager: mbaldwin
ms.date: 10/07/2018
ms.topic: conceptual
ms.service: information-protection
ms.assetid: 6ebd0ca3-1864-4b3d-bb3e-a168eee5eb1d

# optional metadata

#ROBOTS:
#audience:git
#ms.devlang:
ms.reviewer: esaggese
ms.suite: ems
#ms.tgt_pltfrm:
#ms.custom:

---

# Azure Information Protection client: Version release history and support policy

>*Applies to: Active Directory Rights Management Services, [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection), Windows 10, Windows 8.1, Windows 8, Windows 7 with SP1, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, Windows Server 2008 R2*

The Azure Information Protection team regularly updates the Azure Information Protection client for fixes and new functionality. 

You can download the latest general availability release version and the current preview version (if available) from the [Microsoft Download Center](https://www.microsoft.com/en-us/download/details.aspx?id=53018). The general availability version is also included in the Microsoft Update Catalog (category: **Azure Information Protection**), so that you can upgrade the client by using WSUS or Configuration Manager, or other software deployment mechanisms that use Microsoft Update.

For more information, see [Upgrading and maintaining the Azure Information Protection client](client-admin-guide.md#upgrading-and-maintaining-the-azure-information-protection-client).

### Servicing information and timelines

Each general availability (GA) version of the Azure Information Protection client is supported for up to six months after the release of the subsequent GA version. Unsupported versions of the client are not included on this page. Fixes and new functionality are always applied to the latest GA version and will not be applied to older GA versions.

Preview versions should not be deployed for end users on production networks. Instead, use the latest preview version to see and try new functionality or fixes that are coming in the next GA version. Preview versions that are not current are not supported.

### Release history

Use the following information to see what’s new or changed for a supported release of the Azure Information Protection client for Windows. The most current release is listed first. 

> [!NOTE]
> Minor fixes are not listed so if you experience a problem with the Azure Information Protection client, we recommend that you check whether it is fixed with the latest GA release. If the problem remains, check the current preview version.
>  
> For technical support, see the [Support options and community resources](../information-support.md#support-options-and-community-resources) information. We also invite you to engage with the Azure Information Protection team, on their [Yammer site](https://www.yammer.com/askipteam/).

## Versions later than 1.37.19.0

If you have a version 1 of the client that is later than 1.37.19.0, it is a preview build for testing and evaluation purposes.

**Released**: 09/20/2018

**New features:**

- Support for [central reporting](../reports-aip.md) for the Azure Information Protection analytics feature announced at Microsoft Ignite.

**Additional:**

Just for this preview version, to use the scanner, you must follow these steps:

1. Install the current GA version (1.37.19.0) of the client.
2. Install and configure the scanner.
3. Start the scanner.
4. Upgrade the Azure Information Protection client to this preview version.
5. Start the scanner.

If you need instructions to install, configure, and start the scanner, see [Deploying the Azure Information Protection scanner to automatically classify and protect files](../deploy-aip-scanner.md).

## Version 1.37.19.0

**Released**: 09/17/2018

This version includes the MSIPC version 1.0.3592.627 of the RMS client.

**New features**: 

- Support for the ISO standard for PDF encryption, by configuring a new [advanced client configuration](client-admin-guide-customizations.md#protect-pdf-files-by-using-the-iso-standard-for-pdf-encryption). When this option is configured, PDF documents that you protect retain their .pdf file name extension (rather than change to .ppdf) and can be opened by PDF readers that support this ISO standard. Currently, you must instruct users to open these protected PDFs manually by using the Azure Information Protection viewer. To help users do this, when they open one of these protected PDFs, they see a page with icons to select for their operating system.

- Support for new sensitive information types to help you classify documents that contain personal information. [More information](../configure-policy-classification.md#sensitive-information-types-that-require-a-minimum-version-of-the-client) 

- Labels that apply protection now display in Office 2016 apps (minimum version 1805, build 9330.2078) when the user is assigned a license for Azure Rights Management (also known as Azure Information Protection for Office 365).

- Labeling support for **Strict Open XML Document** format in Word, Excel, and PowerPoint files. For more information about the Open XML formats, see the Office blog post, [New file format options in the new Office](https://www.microsoft.com/en-us/microsoft-365/blog/2012/08/13/new-file-format-options-in-the-new-office/). 

- Support for files that have been protected by Secure Islands when those files are other than PDF and Office documents. For example, protected text and picture files. Or, files that have a .pfile file name extension. This support enables new scenarios, such as the Azure Information Protection scanner being able to inspect these files for sensitive information, and automatically relabeling them for Azure Information Protection. [More information](client-admin-guide-customizations.md#support-for-files-protected-by-secure-islands)

- New advanced client settings to remove headers and footers that have been applied to documents by other labeling solutions. [More information](client-admin-guide-customizations.md#remove-headers-and-footers-from-other-labeling-solutions)

- For the Azure Information Protection scanner:

    - New cmdlet, [Update-AIPScanner](/powershell/module/azureinformationprotection/Update-AIPScanner): Required to run once after upgrading from the previous GA version (1.29.5.0) or earlier.
    
    - New cmdlet, [Get-AIPScannerStatus](/powershell/module/azureinformationprotection/Get-AIPScannerStatus): Gets the current status of the service for the scanner.  
    
    - New cmdlet, [Start-AIPScan](/powershell/module/azureinformationprotection/Start-AIPScan): Instructs the scanner to start a one time scan cycle when the schedule is set to manual.
    
    - SharePoint Server 2010 is supported for customers who have [extended support for this version of SharePoint](https://support.microsoft.com/lifecycle/search?alpha=SharePoint%20Server%202010).
    
**Fixes**

- For the Azure Information Protection scanner:
    
    - For documents that are protected in SharePoint libraries, if the *DefaultOwner* parameter is not used for the data repository, the SharePoint Editor value is now used as the default value instead of the Author value.
    
    - Scanner reports include "Last modified by" for Office documents.
    
    - You can now protect all file types by using the `*` wildcard when you edit the registry as described in the [File API configuration](../develop/file-api-configuration.md) instructions.

- When you classify and protect by using PowerShell or the scanner, the Office document metadata is not removed or encrypted.

- Viewing emails by using the Next Item and Previous Item arrow icons on the Quick Access toolbar shows the correct label for each email.

- Custom permissions supports recipient email addresses that contain an apostrophe.

- The computer environment will successfully initialize (bootstrap) when this action is initiated by opening a protected document that's stored in SharePoint Online.

- When you use the client for right-click in File Explorer, PowerShell, or the scanner, labeling is blocked for files in WebDav locations because this is an unsupported scenario.

- The Delete Label icon does not display in client apps (Word, Excel, PowerPoint, and Outlook) when you configure the [policy setting](../configure-policy-settings.md) of **All documents and emails must have a label**.

**Additional changes**:

- For [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Set-AIPScannerConfiguration):
    
    - Values for the *Schedule* parameter are no longer **OneTime**, **Continuous**, and **Never**, but now **Manual** and **Always**.
        
    - The *Type* parameter is removed, so it is also removed from the output when you run [Get-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Get-AIPScannerConfiguration). By default, only new or modified files are inspected after the first scan cycle. If you previously set the *Type* parameter to **Full** to rescan all files, now run [Start-AIPScan](/powershell/module/azureinformationprotection/Start-AIPScan) with the *Reset* parameter. The scanner must also be configured for a manual schedule, which requires the *Schedule* parameter to be set to **Manual** with [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Set-AIPScannerConfiguration).
    
- The default exclusion list for the client and scanner now includes .msg, .rar, and .zip files. The scanner also excludes .rtf files. [More information](client-admin-guide-file-types.md#file-types-that-are-excluded-from-classification-and-protection)

- The policy version is changed to 1.4. Identifying the version number is required for [configuring disconnected computers](client-admin-guide-customizations.md#support-for-disconnected-computers).

- The **Send Us Feedback** link in the **Help and Feedback** dialog box is removed. It was temporarily replaced with **Report an Issue**, but this link now displays in preview versions only. By default, this option sends an email to Microsoft but you can change this email address to an HTTP string that you specify. For example, a customized web page that you have for users to report issues, or an email address that goes to your help desk. To modify this address, use an [advanced client setting](client-admin-guide-customizations.md#modify-the-email-address-for-the-report-an-issue-link).

## Version 1.29.5.0 

**Released**: 06/26/2018

This version includes the MSIPC version 1.0.3403.1224 of the RMS client.

**Fixes**:

- For Outlook versions 16.0.9324.1000 and later (Click-to-Run), the Azure Information Protection bar supports the latest monitor display options that previously might result in the bar displaying outside the Outlook application.

- Visual markings that you configure [per Office application type](../configure-policy-markings.md#setting-different-visual-markings-for-word-excel-powerpoint-and-outlook) now replace a header or footer that was previously applied by an Azure Information Protection label.

- When an Excel file is already labeled and the label applies visual markings, a new sheet now also has the label's visual markings applied.

- When you use the advanced client setting to [label an Office document by using an existing custom property](client-admin-guide-customizations.md#label-an-office-document-by-using-an-existing-custom-property), automatic labeling doesn't override manual labeling.

## Version 1.27.48.0

**Released**: 05/30/2018

This version includes the MSIPC version 1.0.3403.1224 of the RMS client.

**New features**: 

- For the Azure Information Protection scanner:
    
    - You can specify a file types list to include or exclude from scanning. To specify this list, use [Set-AIPScannerScannedFileTypes](/powershell/module/azureinformationprotection/Set-AIPScannerScannedFileTypes). After you have specified your file types list, you can add a new file type to the list by using [Add-AIPScannerScannedFileTypes](/powershell/module/azureinformationprotection/Add-AIPScannerScannedFileTypes), and remove a file type from the list by using [Remove-AIPScannerScannedFileTypes](/powershell/module/azureinformationprotection/Remove-AIPScannerScannedFileTypes).
    
    - You can label files without inspecting the contents by applying a default label. Use the [Set-AIPScannerRepository](/powershell/module/azureinformationprotection/Set-AIPScannerRepository) cmdlet, and set the *MatchPolicy* parameter to **Off**. 
    
    - You can discover files with sensitive information types without configuring labels for automatic classification. use the [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Set-AIPScannerConfiguration) cmdlet, and set the *DiscoverInformationTypes* parameter to **All**
    
    - By default, only Office document types are protected. Other file types can be protected when you define them in the registry. For instructions, see [File API configuration](../develop/file-api-configuration.md) from the developer guidance.
    
    - By default, the scanner now runs with a low integrity level for higher security in case you run the scanner with an account that has privileged rights. When the service account that runs the scanner has only the rights documented in the [scanner prerequisites](../deploy-aip-scanner.md#prerequisites-for-the-azure-information-protection-scanner), the low integrity level is not necessary and is not recommended because it negatively affects performance. You can use an advanced client setting to disable the low integrity level. [More information](client-admin-guide-customizations.md#disable-the-low-integrity-level-for-the-scanner) 
    
- For [Get-AIPFileStatus](/powershell/module/azureinformationprotection/Get-AIPFileStatus), the output now includes the Rights Management owner and Rights Management issuer, and the date that the content was protected.
 
**Additional changes**:

- For the Azure Information Protection scanner: 
    
    - If you installed a previous version of the scanner, rerun the scanner installation command with [Install-AIPScanner](/powershell/module/azureinformationprotection/Install-AIPScanner) after you have upgraded the Azure Information Protection client. Your configuration settings for the scanner and repositories will be retained. Reinstalling the scanner grants the scanner service account delete permissions for the scanner database, which will be required for reports.    
    
    - The *ScanMode* parameter from [Set-AIPScannerConfiguration](/powershell/module/azureinformationprotection/Set-AIPScannerConfiguration) is renamed to **Enforce**, with values of Off and On.
    
    - To use a default label, you no longer need to configure a default label as a policy setting. Instead, just specify this default label with the repository configuration. 

- Removed the "Congratulations!" welcome page and "What's new in Azure Information Protection" page, which displayed for first-time use in Office applications.

## Version 1.26.6.0

**Released**: 04/17/2018

This version includes the MSIPC version 1.0.3403.1224 of the RMS client.

**New features**:

- The Azure Information Protection scanner: The PowerShell module that is included with the client has new cmdlets to install and configure the scanner so that you can discover, classify, and protect files on your on-premises data stores. For instructions, see [Deploying the Azure Information Protection scanner to automatically classify and protect files](../deploy-aip-scanner.md). 
- You can now set different visual markings for Word, Excel, PowerPoint, and Outlook by using an "If.App" variable statement in the text string, and identify the application type. [More information]configure-policy-markings.md#setting-different-visual-markings-for-word-excel-powerpoint-and-outlook)

- Support for the [policy setting](../configure-policy-settings.md), **Display the Information Protection bar in Office apps**. When this setting is off, users select labels from the **Protect** button on the ribbon.

- A new advanced client setting (still in preview) to turn on classification to run continuously in the background. When this setting is enabled, for Office apps, automatic and recommended classification runs continuously in the background, instead of running when documents are saved. With this change in behavior, you can now apply automatic and recommended classification to documents that are stored in SharePoint Online. [More information](client-admin-guide-customizations.md#turn-on-classification-to-run-continuously-in-the-background)

- A new advanced client setting so that Outlook doesn't apply the default label that is configured in the Azure Information Protection policy. Instead, Outlook can apply a different default label, or no label. [More information](client-admin-guide-customizations.md#set-a-different-default-label-for-outlook) 

- For Office apps, when you specify custom permissions, you can now browse and select users from an address book icon. This option brings parity to the user experience when you specify custom permissions by using File Explorer.

- Support for a completely non-interactive authentication method, for service accounts that use PowerShell and that cannot be granted the **Log on locally** right. This authentication method requires you to use the new *Token* parameter with [Set-AIPAuthentication](/powershell/module/azureinformationprotection/Set-AIPAuthentication), and run a PowerShell script as a task. [More information](client-admin-guide-powershell.md#specify-and-use-the-token-parameter-for-set-aipauthentication)

- New parameter, *IntegratedAuth* for [Set-RMSServerAuthentication](/powershell/module/azureinformationprotection/set-rmsserverauthentication). This parameter supports server mode for AD RMS, which is needed for AD RMS to support Windows Server FCI.


**Fixes**:

Fixes for stability and for specific scenarios that include:

- For Office versions 16.0.8628.2010 and later (Click-to-Run), the Azure Information Protection bar supports the latest monitor display options that previously might result in the bar displaying outside Office applications.

- When two organization using Azure Information Protection share labeled documents and emails, their own labels are retained and not replaced by the other organization's labels.

- For Excel:
        
    - Support for changing Office themes or Windows themes, which previously caused Excel to not display any data after the theme was changed.
        
    - Support for cells that contain cross-references, which previously caused text corruption in that cell.
    
    - Support for typing Japanese, Chinese, or Korean characters, which previously closed a window so these characters couldn't be selected.
    
    - Support for comments, which previously closed the comment while it was being typed.

- For PowerPoint: Support for coauthoring, which previously could cause data loss.

- Files that have a .xml file name extension can now be inspected for recommended or automatic classification.

- The viewer can now open protected text-based files (.ptxt and .pxml) larger than 20 MB. 
- Prevent Outlook hanging when Outlook reminders are used.

- Bootstrap succeeds in Office 64-bit, so that you can protect documents and emails.

- You can now configure a label for user-defined permissions for Word, Excel, PowerPoint, and File Explorer and also use the advanced client setting to hide the custom permissions options. [More information](client-admin-guide-customizations.md#make-the-custom-permissions-options-available-or-unavailable-to-users) 

- Fall back to the Calibri font if visual markers in the Azure Information Protection policy are configured for a font name that is not installed on the client.

- Prevent Office crashes after the Azure Information Protection client is upgraded.

- For Office apps, improve performance and memory consumption.

- When you configure a label for user-defined permissions and HYOK (AD RMS) protection, the protection no longer incorrectly uses the Azure Rights Management service.

- For a more consistent management experience, sublabels no longer inherit visual markings and protection settings from their parent label.

**Additional changes**:

- For [client usage logging](client-admin-guide-files-and-logging.md#usage-logging-for-the-azure-information-protection-client ): Event ID 102 and ID 103 are replaced with event ID 101.

## Version 1.10.56.0

**Released**: 09/18/2017

This version includes the MSIPC version 1.0.3219.0619 of the RMS client.

**New features**:

- Support for the new Office 365 DLP conditions that you can configure for a label. For more information, see [Configure conditions for an Azure Information Protection label](../configure-policy-classification.md).

- Support for labels that are configured for user-defined actions. For Outlook, this label automatically applies the Outlook Do Not Forward option. For Word, Excel, PowerPoint, and File Explorer, this label prompts the user to specify custom permissions. For more information, see [Configure an Azure Information Protection label for protection](../configure-policy-protection.md).

- Labels support multiple languages. Beginning with August 30, 2017, the [default policy](../configure-policy-default.md) includes support for multiple languages that this version of the client displays to users. For users to see labels in their preferred language from a default policy before this date, and for labels that you configure, see [How to configure labels for different languages in Azure Information Protection]configure-policy-languages.md).

- Labels are displayed from the **Protect** button on the Office ribbon, in addition to displaying on the Information Protection bar. 

- Native protection for the following Visio file types: .vsdm, .vsdx, .vssm, .vssx, .vstm, .vstx

- Support for advanced client configurations that you configure in the Azure portal. These configurations include the following:
    
    - [Hide or show the Do Not Forward button in Outlook](client-admin-guide-customizations.md#hide-or-show-the-do-not-forward-button-in-outlook)
    
    - [Make the custom permissions options available or unavailable to users](client-admin-guide-customizations.md#make-the-custom-permissions-options-available-or-unavailable-to-users)
    
    - [Permanently hide the Azure Information Protection bar](client-admin-guide-customizations.md#permanently-hide-the-azure-information-protection-bar)
    
    - [Enable recommended classification in Outlook](client-admin-guide-customizations.md#enable-recommended-classification-in-outlook)

- For PowerShell, support to label files non-interactively by using the new PowerShell cmdlets, [Set-AIPAuthentication](/powershell/module/azureinformationprotection/set-aipauthentication) and [Clear-AIPAuthentication](/powershell/module/azureinformationprotection/clear-aipauthentication). For more information how to use these cmdlets, see the [PowerShell section](client-admin-guide-powershell.md#how-to-label-files-non-interactively-for-azure-information-protection) of the admin guide.

- For the PowerShell cmdlets, [Set-AIPFileLabel](/powershell/module/azureinformationprotection/set-aipfilelabel) and [Set-AIPFileClassification](/powershell/module/azureinformationprotection/set-aipfileclassification), there are new parameters: **Owner** and **PreserveFileDetails**. These parameters let you specify an email address for the Owner custom property, and leave the date unchanged for documents that you label.

**Fixes**:

Fixes for stability and for specific scenarios that include:

- Support for generically protecting large files that previously could cause corruption if larger than 1 GB. Now, the file size is limited only by available hard disk space and available memory. For more information about file size limitations, see [File sizes supported for protection](client-admin-guide-file-types.md#file-sizes-supported-for-protection) from the admin guide.

- The Azure Information Protection client viewer opens protected PDF (.ppdf) files as view-only.

- Support for labeling and protection of files stored on SharePoint Server.

- Watermarks now support multiple lines. In addition, visual markings are now applied to a document on the [first save only]configure-policy-markings.md#when-visual-markings-are-applied) rather than every time a document is saved.

- The **Run Diagnostics** option in the **Help and Feedback** dialog box is replaced with **Reset Settings**. The behavior for this action has changed to include signing out the user and deleting the Azure Information Protection policy. For more information, see [More information about the Reset Settings option](..\rms-client\client-admin-guide.md#more-information-about-the-reset-settings-option) from the admin guide.

- Support for proxy authentication.

Fixes for a better user experience, that include:

- Email validation when users specify custom permissions. Also, multiple email addresses can now be specified by pressing Enter.

- The parent label is not displayed when all its sublabels are configured for protection and the client does not have an edition of Office that supports protection. 

## Next steps

For more information about installing and using the client: 

- For users: [Download and install the client](install-client-app.md)

- For admins: [Azure Information Protection client administrator guide](client-admin-guide.md)


