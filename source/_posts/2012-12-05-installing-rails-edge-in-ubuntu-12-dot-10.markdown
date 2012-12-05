---
layout: post
title: "Installing Rails Edge (4.0.0.beta)"
date: 2012-12-05 12:46
comments: true
categories: [Ruby, Rails, Ubuntu]
---
These are the steps I had to follow to get Rails Edge (4.0.0.beta at the moment of writing) in my Ubuntu 12.10 box.
<!-- More -->

## Create a new gemset

```bash
$ mkdir rails_edge && cd rails_edge
/rails_edge$ echo 'rvm gemset use rails_edge --create' > .rvmrc
/rails_edge$ cd .. && cd rails_edge
```
At this point __rvm__ is going to ask you if you trust the `.rvmrc` file, just say __*yes*__

## Clone Rails

```bash
/rails_edge$ git clone https://github.com/rails/rails.git
```
## Install required gems

```bash
/rails_edge$ gem install i18n thor
```

## Create a dummy Rails app

```bash
 /rails_edge$ ruby rails/railties/bin/rails new dummy_app --edge --skip-bundle && rm -rf rails/
```
## Extract the generated Gemfile

```bash
 /rails_edge$ mv dummy_app/Gemfile . && rm -rf dummy_app/
```

## Install Rails Edge

```bash
 /rails_edge$ bundle install --binstubs
 /rails_edge$ rails -v
 Rails 4.0.0.beta
```

## Install a JavaScript runtime:

__NOTE:__ This step is the only one that's specific to Ubuntu

In this case we are going to install __node.js__

```bash
/rails_edge$ sudo apt-get install python-software-properties
/rails_edge$ sudo add-apt-repository ppa:chris-lea/node.js
/rails_edge$ sudo apt-get update
/rails_edge$ sudo apt-get install nodejs npm
```

## Create a Rails Edge app

```bash
 /rails_edge$ rails new rails_4_app --edge --skip-bundle && cd rails_4_app/
 /rails_edge/rails_4_app$ bundle install --binstubs
 /rails_edge/rails_4_app$ rails s
=> Booting WEBrick
=> Rails 4.0.0.beta application starting in development on http://0.0.0.0:3000
=> Call with -d to detach
=> Ctrl-C to shutdown server
[2012-12-05 13:58:18] INFO  WEBrick 1.3.1
[2012-12-05 13:58:18] INFO  ruby 1.9.3 (2012-11-10) [i686-linux]
[2012-12-05 13:58:18] INFO  WEBrick::HTTPServer#start: pid=32414 port=3000
```
And you should be __Riding Rails 4.0.0.beta__ by now.






