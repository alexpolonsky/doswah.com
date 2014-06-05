---
layout: post
title: Using a Git Hook for Deploying Static Websites
description: "Making local edits to websites and pushing to a remote WebFaction app thorough git."
tags: [WebDev, code, git, WebFaction]
comments: true
---

Having [Kenny](http://blog.kennyluong.com) tell me about his ability to make local edits to his personal websites and remotely push his changes to his Webfaction server through git, I thought I would give it a try for my [personal website](http://joshuatrivera.com). With help from [Totoid](http://toroid.org/ams/git-website-howto), I was able to implement this time-saving tool to make git pushes into a remote repository with a detached work tree where a <i>post-receive</i> hook runs a `git checkout -f`.

### Setup On Your Local Computer

First I created a local respository titled `joshuatrivera` and initalized a git repository with a `index.html` file.

    {% highlight css %}
    $ mkdir joshuatrivera && cd joshuatrivera
    $ git init
    $ echo "Hello, world!" > index.html
    $ git add index.html
    $ git commit -m "First commit"
    {% endhighlight %}

### Performing the Web Host Setup

In webfaction, I needed to create two applications: a git app and a app to hold my website source code.

#### 1. Setting Up Applications In WebFaction

Under applications I created an Application named `Git` with the App Category `Git` and App type set to the default `Git 1.7.4.1`. Next I create an Application for my personal website `joshuatrivera` with the App Category set to `PHP` and App type to the default `Static/CGI/PHP-5.5`.

#### 2. Creating The post-receive Hook In The Git App

When I ssh into my WebFaction and visit the `webapps` folder,  I see the two applications I created `Git` and `joshuatrivera`. Then I created a bare .git folder within the git app to generate the post-receive files used to update files in `joshuatrivera`.

    {% raw %}
    $ cd git/reps
    $ mkdir joshuatrivera.git && cd joshuatrivera.git
    $ git init --bare
    {% endraw %}

This creates the necessary files and folders for our git setup. Inside the `joshuatrivera.git` folder we just created, there is a `hooks` folder where you will create a file named `post-receive` where the scripts will go.

    {% raw %}
    $ cd hooks
    $ vi post-receive
    {% endraw %}

I added these lines in the `post-receive` file I just created and opened

    {% highlight html linenos %}
    #!/bin/sh
GIT_WORK_TREE=/path/to/webapp git checkout -f master
    {% endhighlight %}

For my case, `path/to/webapp` for me was `/home/doswah/webapps/joshuatrivera`. Then I needed to provide the necessary permissions so the post-receive script can write to the appropriate file. So after creating the `post-receive` file, type

    {% raw %}
    $ chmod +x post-receive
    {% endraw %}

### Connect To Post-Receive File Through SSH

After that setup in our WebFaction setup, now we need to create the functionality I wanted on my local machine. I created a remote to the .git repository I made in WebFaction.

    {% raw %}
    $ git remote add joshuatrivera ssh://<webfaction_login>/home/doswah/webapps/git/repos/joshuatrivera.git
    $ git push joshuatrivera +master:refs/heads/master
    {% endraw %}

In my case, my `<webfaction_login>` is `doswah@web351.webfaction.com` . Now the files I push through the git push command will appear in the `joshuatrivera` application.

### Updating My Website

Finally. Now when I make changes on my local machine, to update this to the WebFaction server I can just run

    {% raw %}
    $ git push joshuatrivera
    {% endraw %}
 
This transfers any pushed commits from my local repository where the `post-receive` hook will update `joshuatrivera` for me!

### GitHub Setup

I then setup a GitHub repository then added a remote. Since I created a commit already, I made a commit to the master.

    {% raw %}
    $ git remote add origin git@github.com:Doswah/joshuatrivera.com.git
    $ git push -u origin master
    {% endraw %}
