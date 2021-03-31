# Learning as We Go: Decomposing Dev Environments with Lando

## [Code4Lib 2021 Post-conference workshop, March 26, 2021 9am EST](https://2021.code4lib.org/workshops/Learning-as-We-Go-Decomposing-Dev-Environments-with-Lando)

Workshop recording: [https://vimeo.com/531093418](https://vimeo.com/531093418)
Identifier: [DOI 10.17605/OSF.IO/5KP4G](https://doi.org/10.17605/OSF.IO/5KP4G)

## Presented by

[Hardy Pottinger](https://github.com/hardyoyo/info)

## Abstract
Things have gotten better: most projects know that getting new developers up to speed is important.
We keep notes on the hard stuff. But, typing long lists of mysterious commands, and keeping track 
of all the details, is still something many of us expect of new collaborators. We can do better. 
Lando is one tool that can help.

Lando is a way to bootstrap a useable development environment. It's built on Docker, and is like 
Docker-Compose, but much more transparent. It handles the boring details and helps you actually 
start developing: with code in your favorite IDE, and all the services you need in Docker. It's 
all about making the life of a developer easier. It won't give you an application container you 
can deploy. But you will develop a deeper understanding of how all the pieces fit together. And 
you'll have a tool which can deploy those pieces to dev/stage/prod if you wish.

The first part of this session will be an introduction to Lando. We'll set up a MySQL database 
and play with it. We'll build an Omeka-S webapp as a sandbox. We'll build a Django project and 
app, and then kick off a debugger.

We'll end with some live coding: the entire group will collaborate on a Lando-based development 
environment for a project of our choosing.

After completing this workshop, attendees should come away able to use Lando to build a new 
development environment for any coding project.

## Preparing for the Workshop

The format of this workshop will be "keep up if you can", so following allong with the code
is not necessary. However, if you *do* wish to follow along, here's what you'll need to do
(preferrably before the day of the workshop).

1. [install Lando](https://docs.lando.dev/basics/installation.html)
2. clone this project
3. cd to the prep folder and run `lando rebuild`

After step 3 is completed, you will have all the required software and Docker images downloaded,
and you'll be ready to play on March 26.

## I want to start working now!

Cool! Grab the [slide deck](LearningAsWeGo-DecomposingDevEnvironmentsWithLando.pdf) (it's a work in progress) and skip to the "extra credit" slide
which is towards the end. Or just go to the [Lando 101](https://docs.lando.dev/guides/lando-101/lando-overview.html) course and start following it.

You might also want to look at the [Lando Cheat Sheet](LandoCheatSheet.pdf) I made, it might come in handy.

## Read the Docs!

There is a ton of great [documentation on Lando](https://docs.lando.dev/), it's all worth reading.

## This is cool and fun, but, OMG, you filled my Hard Drive!

Eh, it happens. Docker is a space hog. If you're done tinkering with Lando and/or want to slim down your Docker space usage, here are some commands that will
throw away all the container images you've downloaded (which is safe, you'll be able to download them again if you need them):

```
docker system prune -af
docker rm $(docker ps -a -q)
docker rmi $(docker images -q -f dangling=true)
```

> 🛑 **warning**
If you are in the process of creating a custom Docker image, don't run those commands above or you'll be sad.

## Contributing

1. Fork it!
2. Create your feature branch: `git checkout -b my-new-feature`
3. Commit your changes: `git commit -am 'Add some feature'`
4. Push to the branch: `git push origin my-new-feature`
5. Submit a pull request :D
## Credits

Much thanks are owed to the entire [Lando community](https://github.com/sponsors/lando), for their continued support and for sharing such a great tool with the rest of us.

Thanks to [MySQLtutorial.org](https://www.mysqltutorial.org/about-us/) for use of their sample database in exercise 1.
## License

[MIT](LICENSE)
