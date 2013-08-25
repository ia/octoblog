---
layout: post
title: "Hello, octopress"
date: 2013-08-26 00:33
comments: true
categories: txt
---

# zero post #

## octopress fast setup (ubuntu 13.04)##

 (epigraph) Yo dawg! I heard that you like octopress,  
 so I put instruction for install octopress in my octopress blog  
 so you can install your octopress using mine.

Create a repo @ github.com using web interface,  
call it something like octopress (I use "octoblog" for this) first.  
Then run the following commands, one by one:

	$ sudo apt-get install rubygems ruby-bundler rake ruby1.9.3 ruby1.9.1-dev ruby1.8-dev
	$ mkdir octopress
	$ cd octopress
	$ git init
	$ git remote add octopress git://github.com/imathis/octopress.git
	$ git pull octopress master
	$ git checkout -b source
	$ git remote add origin git@github.com:$(GITHUB_USER)/octoblog.git
	$ git push origin source
	$ bundle install
	$ rake setup_github_pages
	git@github.com:ia/octoblog.git
	$ rake install

Open _config.yml for edit, find lines like these:

	# If publishing to a subdirectory as in http://site.com/project set 'root: /project'
	root: /

and add octopress to / in root line like this:

	# If publishing to a subdirectory as in http://site.com/project set 'root: /project'
	root: /octoblog

save changes, close file, and run:

	$ rake generate
	$ rake deploy
	$ rake new_post
	Hello, world
	$ edit source/_posts/2013-NN-MM-hello-world.markdown

Write something, save, and post:

	$ rake generate
	$ rake deploy

