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
