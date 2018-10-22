---
title: class mip MetadataAction 
description: Reference for class mip MetadataAction 
author: BryanLa
ms.service: information-protection
ms.topic: reference
ms.date: 09/27/2018
ms.author: bryanla
---
# class mip::MetadataAction 
An [Action](class_mip_action.md) that adds metadata information to the content.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
public const std::vector<std::string>& GetMetadataToRemove() const  |  Get the list of names of metadata that should be removed from content.
public const std::vector<std::pair<std::string, std::string>>& GetMetadataToAdd() const  |  Get the metadata name/value pairs that should be added to the content.
 public ActionType GetType() const  |  Get the type of [Action](class_mip_action.md).
  
## Members
  
### GetMetadataToRemove
Get the list of names of metadata that should be removed from content.

  
**Returns**: A vector of strings to remove. 
Removing metadata should be done before adding metadata.
  
### GetMetadataToAdd
Get the metadata name/value pairs that should be added to the content.

  
**Returns**: Const std::vector<std::pair<std::string, std::string>>& 
Removing metadata should be done before adding metadata.
  
### ActionType
Get the type of [Action](class_mip_action.md).

  
**Returns**: ActionType The type of derived action this base class can be cast to.