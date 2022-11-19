### Account Takeover Via  case-insensitive comparison in MYSQL (with the type VARCHAR) 
Application doesnot properly check if user with username exist in the database allowing attacker to create same user via case conversion.

##### admin > exist
##### Admin > Can be registered

### Bypass 
##### admin    > User Exist
##### Admin%20 > Can be registered
