# Geotrellis Documentation #

This repository contains the source for the Geotrellis documentation website.

## Dependencies ##

### Unix ###

Jekyll is required. Follow the install instructions at the Jekyll [wiki](https://github.com/mojombo/jekyll/wiki/Install). In most cases, you can install via RubyGems: 

    gem install jekyll

OSX users might need to update RubyGems:

    sudo gem update --system

### Windows ###

Grab the [RubyInstaller](http://rubyinstaller.org/downloads). Try release 1.8.x if you experience unicode problems with 1.9.x.

Follow the instructions for [RubyInstaller DevKit](https://github.com/oneclick/rubyinstaller/wiki/Development-Kit).

Install Jekyll using the gem package manager:

    gem install jekyll

## Building & Viewing ##

Checkout the gh-pages branch, and build by:

    jekyll --server

The generated site is available at `http://localhost:4000`

If you get `incompatible encoding` errors when generating the site under Windows, then ensure that the
console in which you are running jekyll can work with UTF-8 characters. As described in the blog
[Solving UTF problem with Jekyll on Windows](http://joseoncode.com/2011/11/27/solving-utf-problem-with-jekyll-on-windows/)
you have to execute `chcp 65001`. This command is best added to the `jekyll.bat`-script.

## Markdown ##

The markdown used in this site uses [Maruku](http://maruku.rubyforge.org/maruku.html) extensions.

### Markdwn Editor for OSX ###

There exists a free markdown editor for OSX called [Mou](http://mouapp.com/). It's quite convenient to work with, and it generates the translated Markdown in real-time alongside of your editor window, as can be seen here:

![Mou Screen Shot](http://mouapp.com/images/Mou_Screenshot_1.png)

