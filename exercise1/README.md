# Exercise 1: MySQL
### Let's make a database and import a backup

1. download a [sample database for MySQL](https://sp.mysqltutorial.org/wp-content/uploads/2018/03/mysqlsampledatabase.zip) into the exercize1 folder
```
cd exercise1 
wget https://sp.mysqltutorial.org/wp-content/uploads/2018/03/mysqlsampledatabase.zip
```
2. starting up
```
cd exercise1
lando init --full
? From where should we get your app's codebase? (Use arrow keys)
❯ current working directory
? What recipe do you want to use? (Use arrow keys)
❯ lamp # this is a lie, we'll delete PHP stuff soon
? Where is your webroot relative to the init destination? .
? What do you want to call this app? mydb
```
2. edit the `.lando.yml` file and delete the PHP stuff we won't use
```
# delete the recipe line
# delete the proxy lines
# delete the appserver lines
# delete the composer tooling
# delete the php tooling
```
3. change the portforward line to use port `3306` instead of `true`
4. `lando poweroff` just in case
5. `lando rebuild` build this server
6. use the `lando db-import` tooling
```
lando db-import mysqlsampledatabase.zip
```
7. use the `lando mysql` client tooling
```
lando mysql
mysql> show databases;
mysql> use classicmodels;
mysql> show tables;
select * from customers;
```
8. run a destructive query
```
mysql> select count(*) as total from customers;
mysql> SET FOREIGN_KEY_CHECKS=0; # I have a bad feeling about this...
mysql> delete from customers where addressLine2 is null;
mysql> select count(*) as total from customers; # Oh no!
```
9. blow it all away and start from scratch
```
lando destroy -y
lando rebuild -y
lando db-import mysqlsampledatabase.zip
```
10. enjoy your all-purpose MySQL workbench
  - if you're rusty with MySQL, [this is a nice tutorial](https://www.mysqltutorial.org/getting-started-with-mysql/)

### Extra Credit
* Add the [PhpMyAdmin service](https://docs.lando.dev/config/phpmyadmin.html) to this workspace