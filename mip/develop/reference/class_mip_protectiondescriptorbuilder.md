---
title: class mip::ProtectionDescriptorBuilder 
description: Documents the mip::protectiondescriptorbuilder class of the Microsoft Information Protection (MIP) SDK.
author: msmbaldwin
ms.service: information-protection
ms.topic: reference
ms.author: mbaldwin
ms.date: 10/29/2019
---

# class mip::ProtectionDescriptorBuilder 
Constructs a ProtectionDescriptor that describes protection associated with a piece of content.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
public MIP_API std::shared_ptr\<ProtectionDescriptor\> Build()  |  Creates a ProtectionDescriptor whose access permissions are defined by this ProtectionDescriptorBuilder instance.
public void SetName(const std::string& value)  |  Sets protection policy name.
public void SetDescription(const std::string& value)  |  Sets protection policy description.
public void SetContentValidUntil(const std::chrono::time_point\<std::chrono::system_clock\>& value)  |  Sets protection policy expiration time.
public void SetAllowOfflineAccess(bool value)  |  Sets if protection policy allows offline content access or not.
public void SetReferrer(const std::string& uri)  |  Sets protection policy referrer address.
public void SetEncryptedAppData(const std::map\<std::string, std::string\>& value)  |  Sets app-specific data that should be encrypted.
public void SetSignedAppData(const std::map\<std::string, std::string\>& value)  |  Sets app-specific data that should be signed.
public virtual ~ProtectionDescriptorBuilder()  | Not yet documented.
public static MIP_API std::shared_ptr&lt;ProtectionDescriptorBuilder&gt; mip::ProtectionDescriptorBuilder::CreateFromUserRights | Creates a ProtectionDescriptorBuilder whose access permissions are defined by users and rights.
public static MIP_API std::shared_ptr&lt;ProtectionDescriptorBuilder&gt; mip::ProtectionDescriptorBuilder::CreateFromUserRoles | Creates a ProtectionDescriptorBuilder whose access permissions are defined by users and roles.
public static MIP_API std::shared_ptr&lt;ProtectionDescriptorBuilder&gt; mip::ProtectionDescriptorBuilder::CreateFromTemplate | Creates a ProtectionDescriptorBuilder whose access permissions are defined by the protection template. 

## Members
  
### Build function
Creates a ProtectionDescriptor whose access permissions are defined by this ProtectionDescriptorBuilder instance.

  
**Returns**: New ProtectionDescriptor instance
  
### SetName function
Sets protection policy name.

Parameters:  
* **value**: Protection policy name


  
### SetDescription function
Sets protection policy description.

Parameters:  
* **value**: Policy description


  
### SetContentValidUntil function
Sets protection policy expiration time.

Parameters:  
* **value**: Policy expiration time


  
### SetAllowOfflineAccess function
Sets if protection policy allows offline content access or not.

Parameters:  
* **value**: If policy allows offline content access or not


  
### SetReferrer function
Sets protection policy referrer address.

Parameters:  
* **uri**: Policy referrer address


The referrer is a URI that can be displayed to the user upon failed protection policy acquisition that contains information on how that user can gain permission to access the content.
  
### SetEncryptedAppData function
Sets app-specific data that should be encrypted.

Parameters:  
* **value**: App-specific data


An application can specify a dictionary of app-specific data that will be encrypted by the protection service. This encrypted data is independent of the signed data set by SetSignedAppData.
  
### SetSignedAppData function
Sets app-specific data that should be signed.

Parameters:  
* **value**: App-specific data


An application can specify a dictionary of app-specific data that will be signed by the protection service. This signed data is independent of the encrypted data set by SetEncryptedAppData.
  
### ~ProtectionDescriptorBuilder function
_Not documented yet._

### CreateFromUserRights function
Creates a ProtectionDescriptorBuilder whose access permissions are defined by users and rights.

Parameters:
* **usersAndRights**: Collection of users-to-rights mappings.

**Returns**: New [ProtectionDescriptor](class_mip_protectiondescriptor.md) instance 

### CreateFromUserRoles function
Creates a ProtectionDescriptorBuilder whose access permissions are defined by users and roles.

Parameters:
* **usersAndRoles**: Collection of users-to-roles mappings.

**Returns**: Creates a [ProtectionDescriptor](class_mip_protectiondescriptor.md) whose access permissions are defined by users and roles.

### CreateFromTemplate function
Creates a ProtectionDescriptorBuilder whose access permissions are defined by the protection template. 

Parameters:
* **templateId**: A protection template ID.

**Returns**: A new [ProtectionDescriptor](class_mip_protectiondescriptor.md) instance.