#### Find Historic Information from github
```
Clone the repo &  use command 'git log' alternative tig tool. 
```
![Screenshot at 2022-11-27 16-45-21](https://user-images.githubusercontent.com/85208639/204132027-56564b15-5807-4c21-b384-957b75248d48.png)

#### AWS Misconfiguration

Developers most of the time use the AWS bucket name same as the server name with poor IAM. This may allow any logged in user to view, read files from the AWS account.

```
aws s3 ls s3://assets.suvam.com/secret.txt
```

```
aws s3 cp s3://assets.suvam.com/secret.txt secret1.txt
```
