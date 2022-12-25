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
