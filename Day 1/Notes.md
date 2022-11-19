
## Day 1
#### find /dir -type f-name name -exec grep -H '^keyword' {} \;

### Decompressing files
#### tar -xjf file.tbz
#### tar -xzf file.tgz
#### bunzip2 file.bz2

### Encrypting and Decrypting files with openssl
https://robertheaton.com/2013/07/29/padding-oracle-attack/
#### openssl enc -d -aes256 -k KEY -in enc.tgz.enc -out out.tgz


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

### Create wordlist for testing opensource projects
#### find | sed 's/\.//g' > ffufwordlist.txt

