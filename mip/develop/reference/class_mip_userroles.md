# class mip::UserRoles 
Represents a group of users and the roles associated with them.
  
## Summary
 Members                        | Descriptions                                
--------------------------------|---------------------------------------------
public UserRoles(const std::vector<std::string>& users, const std::vector<std::string>& roles)  |  [UserRoles](class_mip_userroles.md) constructor.
public const std::vector<std::string>& Users() const  |  Gets users associated with a set of roles.
public const std::vector<std::string>& Roles() const  |  Gets roles associated with a group of users.
  
## Members
  
### UserRoles
[UserRoles](class_mip_userroles.md) constructor.

Parameters:  
* **users**: Group of users that share the same roles 


* **roles**: Roles shared by group of users


  
### Users
Gets users associated with a set of roles.

  
**Returns**: Users associated with a set of roles
  
### Roles
Gets roles associated with a group of users.

  
**Returns**: Roles associated with a group of users