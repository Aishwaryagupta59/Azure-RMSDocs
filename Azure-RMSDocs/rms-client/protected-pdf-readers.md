---
# required metadata

title: Protected PDF readers for Microsoft Information Protection
description: Install a reader for PDF documents that are labeled for classification and protection
author: cabailey
ms.author: cabailey
manager: barbkess
ms.date: 12/05/2019
ms.topic: conceptual
ms.collection: M365-security-compliance
ms.service: information-protection
ms.assetid: aab59e02-930b-4a17-8442-2d5d081fe1a6

# optional metadata

#audience:
#ms.devlang:
ms.reviewer: kartikka
ms.suite: ems
#ms.tgt_pltfrm:
ms.custom: user
search.appverid:
- MET150

---

# PDF readers that support Microsoft Information Protection

If you need to open a PDF document that's been protected by Microsoft Information Protection, use the following links and information.

This protection encrypts the document, and verifies that you have been granted permissions to open it.

## Install PDF readers for your device

Select the device you're using to install a PDF reader that can open protected PDF documents. All these readers can open protected documents that adhere to the ISO standard for PDF encryption:

- **Computers**: [Windows](protected-pdf-readers-windows.md) | [MacOS](protected-pdf-readers-mac.md)

- **Mobile devices**: [Android](protected-pdf-readers-android.md) | [iOS](protected-pdf-readers-ios.md)

### Support for previous formats

The PDF readers in the following table support protected PDF documents that have a .ppdf file name extension, and older formats that have a .pdf file name extension. 

Currently, SharePoint Online and SharePoint on-premises use an older format for PDF documents in IRM-protected libraries.


|Operating system|Supported readers|
|----------------|-----------------------------------|
|Windows 10 and previous versions<br />through Windows 7 Service Pack 1|Azure Information Protection viewer<br /><br />Gaaiho Doc<br /><br />GigaTrust Desktop PDF Client for Adobe<br /><br />Foxit Reader<br /><br />Nitro PDF Reader<br /><br /> Nuance Power PDF|
|Android|Azure Information Protection app<br /><br />Foxit MobilePDF with RMS<br /><br />GigaTrust App for Android|
|iOS|Azure Information Protection app<br /><br />Foxit MobilePDF with RMS<br /><br />TITUS Docs|

## Using Adobe Acrobat Reader with the Adobe plug-in

A collaboration between Microsoft and Adobe gives you a more simplified and consistent experience for PDF documents that have been classified and optionally, protected. This collaboration provides support for Adobe Acrobat native integration with Microsoft Information Protection solutions, such as [Azure Information Protection](../what-is-information-protection.md). 

This native integration has the following benefits:

- You can view PDF documents that have been protected because they contain sensitive information.

- You can see the classification value for your organization's label that has been applied to the document.

- Support for the ISO standard for PDF encryption.
    
    Unless this capability has been [disabled by an administrator](client-admin-guide-customizations.md#dont-protect-pdf-files-by-using-the-iso-standard-for-pdf-encryption), this protected PDF file format is enabled by default for the Azure Information Protection client (classic) and is always used by the Azure Information Protection unified labeling client.

You can use the Adobe plug with [Windows](protected-pdf-readers-windows.md) and [MacOS](protected-pdf-readers-mac.md).

For more information, see the following blog posts: 

- [General Availability of Adobe Acrobat Reader Integration with Microsoft Information Protection](https://techcommunity.microsoft.com/t5/Azure-Information-Protection/General-Availability-of-Adobe-Acrobat-Reader-Integration-with/ba-p/298396)

- [Adobe reader and Microsoft Information Protection integration FAQs](https://techcommunity.microsoft.com/t5/Microsoft-Information-Protection/Adobe-reader-and-Microsoft-Information-Protection-integration/ba-p/482219)

## Next steps

Use the links from this page to install a PDF reader so that you can open protected PDF documents.

If you need help using the reader after it's installed, use the instructions and documentation that accompanies that reader. For example, for the Azure Information Protection viewer for Windows, see [User Guide: View protected files with the Azure Information Protection unified labeling client](clientv2-view-use-files.md).
