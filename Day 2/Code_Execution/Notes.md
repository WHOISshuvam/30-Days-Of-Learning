### PHP Code Execution via eval() function
```
In the vulnerable code below eval() function is used without any input validation. This
allows user  to control the value passed via name paramater allowing attacker to execute system commands.

```

```
<?php
  if (!isset($_GET["name"])) {
    header("Location: /?name=fucche");
    die();
  }
?>

<?php 
  $str="echo \"Hello ".$_GET['name']."!!!\";";

  eval($str);
?>
```

#### Exploit 
![Screenshot at 2022-11-20 12-54-23](https://user-images.githubusercontent.com/85208639/202890506-4fa06e60-4e3e-4e6e-a675-a6c9b714283f.png)

### PHP Code Execution via preg_replace() function [ Works in Older Version of PHP (<= 5.5.5) ]
```
preg_replace is a function in php that is used to replace a string with another string based on pattern. In older version of php if we add full controller pattern we can add modifier and  after replacement we can use modifier to eval result as a php code.
```
#### Vulnerable Code

```
<?php
  if (!isset($_GET["new"])) {
    header("Location: /?new=test&pattern=/user/&base=Hello user");
    die();
  }
?>

<?php
  echo preg_replace($_GET["pattern"], $_GET["new"], $_GET["base"]); 
?>
```



