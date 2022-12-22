##### Types of Shell
* ksh
* zsh
* bash
* dash

##### Environment Variable : 
```
env > see env variables

>> - append
>  - overwrite
```

##### Conditional Statements
```
if [x]; then
 do command
 elif [y]; then
    do command
else
       dosomething else
fi           
```
> Reference: https://tldp.org/LDP/abs/html/why-shell.html

#### For Loop
```
#!/bin/bash
for i in $(ls); do
echo item: $i
done
```

#### cut command
```
file.txt
1234/tcp
6566/tcp
9000/tcp

cat file.txt | cut -d "/" -f 1
The -d delimeter will split the "1234/tcp" into 2 parts and the -f flag specifies which part to extract. Here we used 1 so port 1234 will be extracted.
```

##### Windows Command Line Location:
> C:\Windows\system32\cmd.exe

##### Manage Windows Environment Variable in Windows 10
```
Control Panel > System and Security > System > Advanced System Settings
```

##### Command Chaining
```
command1 & command2  - execute both regardless of result
command1 && command2 - execute 1st command and if it succeed, executes 2nd command

command1 | command2  - sends output from first command and send to another
command1 || command2 - executes the first command and if it fails, execute the second one
```
