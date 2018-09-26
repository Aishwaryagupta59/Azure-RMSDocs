# class mip::HttpRequest 
Interface that describes a single http request.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
 public HttpRequestType GetRequestType() const  |  Get request type.
 public const std::string& GetUrl() const  |  Get request url.
 public const std::string& GetBody() const  |  Get request body.
public const std::map<std::string, std::string, CaseInsensitiveComparator>& GetHeaders() const  |  Get request headers.
  
## Members
  
### HttpRequestType
Get request type.

  
**Returns**: Request type
  
### GetUrl
Get request url.

  
**Returns**: Request url
  
### GetBody
Get request body.

  
**Returns**: Request body
  
### GetHeaders
Get request headers.

  
**Returns**: Request headers