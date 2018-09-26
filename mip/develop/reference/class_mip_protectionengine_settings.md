# class mip::ProtectionEngine::Settings 
[Settings](class_mip_protectionengine_settings.md) used by [ProtectionEngine](class_mip_protectionengine.md) during its creation and throughout its lifetime.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
 public Settings(const Identity& identity, const std::string& clientData, const std::string& locale)  |  [ProtectionEngine::Settings](class_mip_protectionengine_settings.md) constructor for creating a new engine.
 public Settings(const std::string& engineId, const std::string& clientData, const std::string& locale)  |  [ProtectionEngine::Settings](class_mip_protectionengine_settings.md) constructor for loading an existing engine.
 public const std::string& GetEngineId() const  |  Gets the engine Id.
 public void SetEngineId(const std::string& engineId)  |  Sets the engine id.
 public const Identity& GetIdentity() const  |  Gets the user Identity associated with the engine.
 public void SetIdentity(const Identity& identity)  |  Sets the user Identity associated with the engine.
 public const std::string& GetClientData() const  |  Gets custom data specified by client.
 public void SetClientData(const std::string& clientData)  |  Sets custom data specified by client.
 public const std::string& GetLocale() const  |  Gets the locale in which engine data will be written.
public void SetCustomSettings(const std::vector<std::pair<std::string, std::string>>& value)  |  Sets name/value pairs used for testing and experimentation.
public const std::vector<std::pair<std::string, std::string>>& GetCustomSettings() const  |  Gets name/value pairs used for testing and experimentation.
 public void SetSessionId(const std::string& sessionId)  |  Sets the engine session id, used for correlation of logging/telemetry.
 public const std::string& GetSessionId() const  |  Gets the engine session id.
 public void SetCloudEndpointBaseUrl(const std::string& cloudEndpointBaseUrl)  |  Sets the cloud endpoint base url, used to specify cloud instance. if not set it will be default value.
 public const std::string& GetCloudEndpointBaseUrl() const  |  Base url associated with protection endpoints.
  
## Members
  
### Settings
[ProtectionEngine::Settings](class_mip_protectionengine_settings.md) constructor for creating a new engine.

Parameters:  
* **identity**: Identity which will be associated with [ProtectionEngine](class_mip_protectionengine.md)


* **clientData**: customizable client data that can be stored with the engine when unloaded and can be retrieved from a loaded engine. 


* **locale**: Engine output will be provided in this locale.


  
### Settings
[ProtectionEngine::Settings](class_mip_protectionengine_settings.md) constructor for loading an existing engine.

Parameters:  
* **engineId**: Unique identifier of engine which will be loaded 


* **clientData**: customizable client data that can be stored with the engine when unloaded and can be retrieved from a loaded engine. 


* **locale**: Engine output will be provided in this locale.


  
### GetEngineId
Gets the engine Id.

  
**Returns**: Engine id
  
### SetEngineId
Sets the engine id.

Parameters:  
* **engineId**: engine id.


  
### GetIdentity
Gets the user Identity associated with the engine.

  
**Returns**: User Identity associated with the engine
  
### SetIdentity
Sets the user Identity associated with the engine.

Parameters:  
* **identity**: User Identity associated with the engine


  
### GetClientData
Gets custom data specified by client.

  
**Returns**: Custom data specified by client
  
### SetClientData
Sets custom data specified by client.

Parameters:  
* **Custom**: data specified by client


  
### GetLocale
Gets the locale in which engine data will be written.

  
**Returns**: Locale in which engine data will be written
  
### SetCustomSettings
Sets name/value pairs used for testing and experimentation.

Parameters:  
* **customSettings**: Name/value pairs used for testing and experimentation


  
### GetCustomSettings
Gets name/value pairs used for testing and experimentation.

  
**Returns**: Name/value pairs used for testing and experimentation
  
### SetSessionId
Sets the engine session id, used for correlation of logging/telemetry.

Parameters:  
* **sessionId**: Engine session id, used for correlation of logging/telemetry


  
### GetSessionId
Gets the engine session id.

  
**Returns**: Engine session id
  
### SetCloudEndpointBaseUrl
Sets the cloud endpoint base url, used to specify cloud instance. if not set it will be default value.

Parameters:  
* **cloudEndpointBaseUrl**: **represents** the cloud instance to request as there can be other cloud instances of Service


  
### GetCloudEndpointBaseUrl
Base url associated with protection endpoints.

  
**Returns**: CloudEndpointBaseUrl