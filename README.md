# mysql-curl-support
Support on mysql 5.7.5 to libcurl

What is working?
 
mysql> load data infile 'http://localhost/file.csv'              into table file FIELDS TERMINATED BY ';';
mysql> load data infile 'https://localhost/file.csv'             into table file FIELDS TERMINATED BY ';';
mysql> load data infile 'http://teste:qwe123@localhost/file.csv' into table file FIELDS TERMINATED BY ';';
mysql> load data infile 'ftp://teste:qwe123@localhost/file.csv'  into table file FIELDS TERMINATED BY ';';
mysql> load data infile 's3://teste-mysql-s3/file.csv'           into table file FIELDS TERMINATED BY ';';
 
·         S3 funciona com ~/.aws/credentials e com ROLES
·         Ainda não tem suporte a enviar accesskey e secretkey
 

Bugs already detected?
 
mysql> load data infile 'sftp://teste:qwe123@arquivo.csv'           into table arquivo FIELDS TERMINATED BY ';';
 
TODO?

Support to parallel read/write (split) S3 files.
Support to read S3 files as stream.
Support on read/write S3 to send access_key and secret_key via URI, like user and password on HTTP support.
Masquerade access_key and secret_key on mysql logs.
After load the data, all temporary files must be removed. This requires create a "garbage collector".
