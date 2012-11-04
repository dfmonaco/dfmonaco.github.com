---
layout: post
title: "Ruby and Rails setup in Ubuntu 12.10"
date: 2012-11-03 12:35
comments: true
categories: [Ruby, Rails, Ubuntu]
---
Ok so you want to start development in Ubuntu with Ruby/Rails, follow the instructions below and you well be coding in ruby in a few minutes!

<!-- More -->

## Install RVM

__RVM__ stands for ___Ruby Version Manager___ and its going to be your best friend when managing ruby versions an gems.

First we are going to install _curl_ and then use it to install _rvm_:

```bash
$ sudo apt-get install curl
$ curl -L https://get.rvm.io | bash -s stable
```

To complete installation add the following line at the end of `.bashrc`:

```bash
[[ -s "$HOME/.rvm/scripts/rvm" ]] && source "$HOME/.rvm/scripts/rvm" # Load RVM into a shell session *as a function*
```

Close the current shell, open a new one and execute the following command, if installation was successful it should output: ___rvm is a function___

```bash
$ type rvm | head -n 1
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



