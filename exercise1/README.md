# Exercise 1: MySQL
### Let's make a database and import a backup from prod

1. starting up
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
3. `lando poweroff` just in case
4. `lando rebuild` build this server
5. use the `lando db-import` tooling
6. use the `lando mysql` client tooling
7. run a destructive query
8. blow it all away and start from scratch
9. enjoy your all-purpose MySQL workbench

### Extra Credit
* Add the [PhpMyAdmin service](https://docs.lando.dev/config/phpmyadmin.html) to this workspace