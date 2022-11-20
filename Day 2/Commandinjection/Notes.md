### Vulnerable Code 
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
