# OJS Example Lando Dev Environment

## Description

This is a rough, but ultimately _working_ example of a Lando dev environment for OJS.
It's a good starting point, but might need further tweaking to get just right.

## How to use:

You'll need to clone the [OJS project](https://github.com/pkp/ojs/), and then update all the submodules that OJS uses (oh, yeah, that)
```
git clone https://github.com/pkp/OJS.git
git submodule update --init --recursive

```
## Tooling

Some helpful tooling for this project includes:

```
  lando composer          Runs composer commands
  lando npm               Runs npm commands
  lando php               Runs php commands
```

## Initial setup steps
1. ensure you have cloned OJS to this project folder, and updated the submodules (see above)
2. find the `config.TEMPLATE.inc.php` file and copy it to `config.inc.php`
3. set up the configuration file for values appropriate to your Lando dev environment (see example [included here](config.inc.php) but be sure to set the base_url to match the domain in your .lando.yml file proxy config)
4. `lando rebuild -y`
5. point your browser at the OJS installation running in lando (`lando info` will tell you where to look), and play with your new OJS installation (it'll start with installation process)
6. you'll need a file upload folder (OJS will tell you this during the installation process). Making a new files folder in your project works fine, but it's up to you.

## Installation state is maintained in `config.inc.php`
If you destroy your environment in order to do a full rebuild, you'll have to re-install OJS. The config.inc.php file contains a line that keeps track of whether to re-install, you'll need to change it to:

`installed = Off`

Then you'll be able to re-install the database stuff.
