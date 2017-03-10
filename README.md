# DynamoDB Dump & Restore
A couple of very simple bash scripts designed and export tables from DynamoDB to S3, and back again.

## Requirements
https://stedolan.github.io/jq/  
https://aws.amazon.com/cli/

## dynamodb-dump
Requires the S3 bucket+folder path to backup to and n number of table names

``` bash
# ./dynamodb-dump <s3-folder> <table-name> ...
./dynamodb-dump dynamodb-backup/staging app-users app-groups app-permissions
```

## dynamodb-restore
Requires the exact S3 bucket+folder. Doesn't need table name because it's encoded in the dumps.

``` bash
# ./dynamodb-restore <s3-folder>
./dynamodb-restore dynamodb-backup/staging/2017-03-09-15-45-12
```
