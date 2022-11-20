### PHP Command Injection
```
⋅⋅⋅In the vulnerable code below eval() function is used without any input validation. This allows user  to control the value passed via name
paramater allowing attacker to execute system commands.⋅⋅⋅

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
