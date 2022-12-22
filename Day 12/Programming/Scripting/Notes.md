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
