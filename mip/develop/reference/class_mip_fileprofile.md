---
title: class mip FileProfile 
description: Reference for class mip FileProfile 
author: BryanLa
ms.service: information-protection
ms.topic: reference
ms.date: 09/27/2018
ms.author: bryanla
---
# class mip::FileProfile 
[FileProfile](class_mip_fileprofile.md) class is the root class for using the Microsoft Information Protection operations.
A typical application will only need one Profile.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
 public const Settings& GetSettings() const  |  Returns the profile settings.
public void ListEnginesAsync(const std::shared_ptr<void>& context)  |  Starts list engines operation.
public void UnloadEngineAsync(const std::string& id, const std::shared_ptr<void>& context)  |  Starts unloading the file engine with the given ID.
public void AddEngineAsync(const FileEngine::Settings& settings, const std::shared_ptr<void>& context)  |  Starts adding a new file engine to the profile.
public void DeleteEngineAsync(const std::string& id, const std::shared_ptr<void>& context)  |  Starts deleting the file engine with the given ID. All data for the given profile will be deleted.
  
## Members
  
### Settings
Returns the profile settings.
  
### ListEnginesAsync
Starts list engines operation.
[FileProfile::Observer](class_mip_fileprofile_observer.md) will be called upon success or failure.
  
### UnloadEngineAsync
Starts unloading the file engine with the given ID.
[FileProfile::Observer](class_mip_fileprofile_observer.md) will be called upon success or failure.
  
### AddEngineAsync
Starts adding a new file engine to the profile.
[FileProfile::Observer](class_mip_fileprofile_observer.md) will be called upon success or failure.
  
### DeleteEngineAsync
Starts deleting the file engine with the given ID. All data for the given profile will be deleted.
[FileProfile::Observer](class_mip_fileprofile_observer.md) will be called upon success or failure.