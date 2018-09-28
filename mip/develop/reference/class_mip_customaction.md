---
title: class mip CustomAction 
description: Reference for class mip CustomAction 
author: BryanLa
ms.service: information-protection
ms.topic: reference
ms.date: 09/27/2018
ms.author: bryanla
---
# class mip::CustomAction 
[CustomAction](class_mip_customaction.md) is a generic action class that captures all the sub-properties of the action as a property bag. The caller is responsible to understand the meaning of the action.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
 public const std::string& GetName() const  |  Get action name.
public const std::vector<std::pair<std::string, std::string>>& GetProperties() const  |  Get the properties key value pair list.
 public ActionType GetType() const  |  Get the type of [Action](class_mip_action.md).
  
## Members
  
### GetName
Get action name.

  
**Returns**: An action name if one exists else an empty string.
  
### GetProperties
Get the properties key value pair list.

  
**Returns**: A key value pair list.
  
### ActionType
Get the type of [Action](class_mip_action.md).

  
**Returns**: ActionType The type of derived action this base class can be cast to.