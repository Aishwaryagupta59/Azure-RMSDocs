# class mip::FileProfile::Observer 
[Observer](class_mip_fileprofile_observer.md) interface for clients to get notifications for profile related events.
If an *Error event occurs, error object holds inside [mip::Error](class_mip_error.md) class. 
Client should not call the engine back on the thread that calls the observer.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
 public virtual ~Observer()  | _Not yet documented._
public virtual void OnLoadSuccess(const std::shared_ptr<mip::FileProfile>& profile, const std::shared_ptr<void>& context)  |  Called when profile was loaded successfully.
public virtual void OnLoadFailure(const std::exception_ptr& error, const std::shared_ptr<void>& context)  |  Called when loading a profile caused an error.
public virtual void OnListEnginesSuccess(const std::vector<std::string>& engineIds, const std::shared_ptr<void>& context)  |  Called when list of engines was generated successfully.
public virtual void OnListEnginesError(const std::exception_ptr& error, const std::shared_ptr<void>& context)  |  Called when listing engines caused an error.
public virtual void OnUnloadEngineSuccess(const std::shared_ptr<void>& context)  |  Called when an engine was unloaded successfully.
public virtual void OnUnloadEngineError(const std::exception_ptr& error, const std::shared_ptr<void>& context)  |  Called when unloading an engine caused an error.
public virtual void OnAddEngineSuccess(const std::shared_ptr<mip::FileEngine>& engine, const std::shared_ptr<void>& context)  |  Called when a new engine was added successfully.
public virtual void OnAddEngineError(const std::exception_ptr& error, const std::shared_ptr<void>& context)  |  Called when adding a new engine caused an error.
public virtual void OnDeleteEngineSuccess(const std::shared_ptr<void>& context)  |  Called when an engine was deleted successfully.
public virtual void OnDeleteEngineError(const std::exception_ptr& error, const std::shared_ptr<void>& context)  |  Called when deleting an engine caused an error.
 public virtual void OnPolicyChanged(const std::string& engineId)  |  Called when the policy has changed for the engine with the given id.
 protected Observer()  | _Not yet documented._
  
## Members
  
### ~Observer
_Not documented yet._

  
### OnLoadSuccess
Called when profile was loaded successfully.
  
### OnLoadFailure
Called when loading a profile caused an error.
  
### OnListEnginesSuccess
Called when list of engines was generated successfully.
  
### OnListEnginesError
Called when listing engines caused an error.
  
### OnUnloadEngineSuccess
Called when an engine was unloaded successfully.
  
### OnUnloadEngineError
Called when unloading an engine caused an error.
  
### OnAddEngineSuccess
Called when a new engine was added successfully.
  
### OnAddEngineError
Called when adding a new engine caused an error.
  
### OnDeleteEngineSuccess
Called when an engine was deleted successfully.
  
### OnDeleteEngineError
Called when deleting an engine caused an error.
  
### OnPolicyChanged
Called when the policy has changed for the engine with the given id.
  
### Observer
_Not documented yet._
