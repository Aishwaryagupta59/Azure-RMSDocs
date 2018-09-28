---
title: class mip AddWatermarkAction 
description: Reference for class mip AddWatermarkAction 
author: BryanLa
ms.service: information-protection
ms.topic: reference
ms.date: 09/27/2018
ms.author: bryanla
---
# class mip::AddWatermarkAction 
An action class that specifies adding watermark.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
 public const std::string& GetUIElementName()  |  An API used to mark the watermark element.
 public WatermarkLayout GetLayout() const  |  An API used to get the water mark layout.
 public const std::string& GetText() const  |  Get the text that is meant to go into the watermark.
 public const std::string& GetFontName() const  |  Get the font name used to display the watermark.
 public int GetFontSize() const  |  Get the font size used to display the watermark.
 public const std::string& GetFontColor() const  |  Get the font color used to display the watermark.
 public ActionType GetType() const  |  Get the type of [Action](class_mip_action.md).
  
## Members
  
### GetUIElementName
An API used to mark the watermark element.

  
**Returns**: The name that should be used for the UI element that holds the watermark. The same name will be returned in RemoveWatermarkingAction in case the watermark needs to be removed.
  
### GetLayout
An API used to get the water mark layout.

  
**Returns**: WatermarkLayout the watermarking layout in th form of an enum HORIZONTAL|DIAGONAL. ,
  
### GetText
Get the text that is meant to go into the watermark.

  
**Returns**: Content header text.
  
### GetFontName
Get the font name used to display the watermark.

  
**Returns**: Font name. Default value is Calibri if nothing is set by the policy.
  
### GetFontSize
Get the font size used to display the watermark.

  
**Returns**: Font size as an integer.
  
### GetFontColor
Get the font color used to display the watermark.

  
**Returns**: Font color as a string (for example, "#000000").
  
### ActionType
Get the type of [Action](class_mip_action.md).

  
**Returns**: ActionType The type of derived action this base class can be cast to.