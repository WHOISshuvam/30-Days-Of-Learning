### Vulnerable Code 1
```
index.php
<?php
$site = " Open Redirect ";
?>
<a href="/redirect.php?uri=/">Click Me</a>
```
```
redirect.php
<?php

if (isset($_GET["uri"])) {
return header("Location: ".$_GET["uri"]);
} else {
return header("Location: /");
}
die();
?>
```
Here the application is checking if the uri is set if so application redirects user to the supplied url while if its not set the application redirects user to /. Validation of of user's input is not performed before passing to header location.
