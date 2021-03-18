# Exercise 3: Django
### Let's play with Django!

Yes, I'm handing you a working environment, but I want to show you adding tooling.

1. starting up
```
cd exercise3
# review the .lando.yml file
lando rebuild
```
2. You're set for following the [Django tutorial](https://docs.djangoproject.com/en/3.0/intro/tutorial01/)
```
```
3. Add tooling to restart the Django dev server
```
tooling:
  restart-runserver:
    service: appserver
    description: Quickly restarts the Django runserver process, follows logs, and enables interactive debugging
    cmd: killall python || (cd /app/src && python /app/src/manage.py runserver 0.0.0.0:8000 -v 3)
    user: root
```
4. Play with debugging
  - set a breakpoint
  - trigger that breakpoint
  - explore a bit

**Extra Credit:** add tooling for running `pip` on the appserver
