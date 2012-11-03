---
layout: post
title: "Ruby and Rails setup in Ubuntu 12.10"
date: 2012-11-03 12:35
comments: true
categories: [Ruby, Rails, Ubuntu]
---
Ok so you want to start development in Ubuntu with Ruby/Rails, follow the instructions below and you well be coding in ruby in a few minutes!

## Install RVM

__RVM__ stands for ___Ruby Version Manager___ and its going to be your best friend when managing ruby versions an gems.

First we are going to install _curl_ and then use it to install _rvm_:

```bash
$ sudo apt-get install curl
$ curl -L https://get.rvm.io | bash -s stable
```
To complete installation put the following line at the end of `.bashrc`

```bash
[[ -s "$HOME/.rvm/scripts/rvm" ]] && . "$HOME/.rvm/scripts/rvm" # This loads RVM into a shell session.
```

Reload `.bashrc` and test installation, you should see _rvm_ version number.

```bash
$ source .bashrc
$ rvm -v
```


##  Install Ruby 1.9.3

First install required dependencies:

```bash
$ sudo apt-get install build-essential openssl libreadline6 libreadline6-dev git-core zlib1g zlib1g-dev libssl-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt-dev autoconf libc6-dev ncurses-dev automake libtool bison subversion pkg-config
```

And then install _ruby_:

```bash
$ rvm install 1.9.3
$ rvm --default use 1.9.3
```
## Install Rails

This is the easiest part:

```bash
$ gem install rails
```

And you are ready to go!

If you get into any trouble, feel free to ask for help in the comments below.



