# Example Hyrax environment, built with Lando 

This example sets up the prerequisites and tooling for building a new Hyrax-based application.

### Tooling
```
  lando bundle            Runs bundle commands on the Hyrax appserver
  lando gem               Runs gem commands on the Hyrax appserver
  lando node              Runs node commands on the Hyrax appserver
  lando npm               Runs npm commands on the Hyrax appserver
  lando rails             Runs rails commands on the Hyrax appserver
  lando ruby              Runs ruby commands on the Hyrax appserver
  lando yarn              Runs yarn commands on the Hyrax appserver
```

### How to use

Follow the [Creating a Hyrax-based app](https://github.com/samvera/hyrax/blob/master/documentation/developing-your-hyrax-based-app.md#creating-a-hyrax-based-app) guide, using Lando tooling provided by this environment.

For example, this command will generate a new application based on the Hyrax 3.0.0 template:
```
lando rails _5.2.4.4_ new testapp -m https://raw.githubusercontent.com/samvera/hyrax/v3.0.0/template.rb --database=mysql --skip-spring
```
