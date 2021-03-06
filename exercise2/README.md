# Exercise 2: Omeka-S
### Let's use a recipe

1. starting up
```
cd exercise2
lando init
? From where should we get your app's codebase? (Use arrow keys)
❯ remote git repo or archive
? From where should we get your app's codebase? remote git repo or archive
? Please enter the URL of the git repo or tar archive containing your application code 
  https://github.com/omeka/omeka-s/releases/download/v3.0.1/omeka-s-3.0.1.zip
? What recipe do you want to use? (Use arrow keys)
❯ lamp
? Where is your webroot relative to the init destination? .
? What do you want to call this app? omeka
```
2. Read the [Omeka-S install docs](https://github.com/omeka/omeka-s#installing-from-released-zip-file)
3. Find the credentials the recipe used:
```
lando info
```
4. Edit `config/database.ini` entering credentials (hint:`lamp` for everything except host, which is `database`)
5. `lando restart`
6. visit the URL that Lando says your app is running at (`lando info` will tell you)
7. finish the install steps from the Omeka-S instructions
8. enjoy your new Omeka-S playground 

**Extra Credit:** try to do a *real* dev environment for Omeka-S where you can work on the Omeka-S source code instead of just use it. Warning: you'll need to install Node.js on the Python appserver image. Here's [an example of how](https://github.com/eScholarship/jschol/blob/master/.lando.yml#L29-L35). The Lando devs promise that Lando 4.0 will make this kind of thing easier. Lando 4.0 will be out in the third quarter of 2021, according to the Lando developers.