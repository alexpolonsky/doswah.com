---
layout: post
title: "Updating a Jekyll Blog on Webfaction"
description: "Generating a local site then using rsync to update a static-only site."
modified: 2014-06-02 12:26:59 -1000
tags: [jekyll, blog, webfaction, git]
image:
  feature: 
  credit: 
  creditlink: 
comments: true
share: true
---

After assembling [joshuatrivera.com](http://joshuatrivera.com) I figured it would be a good idea to figure out the best way to operate a blogging site using a git hook like in my [earlier post](http://doswha.com/git-hook-static-websites).
<br><br>
After several searches I discovered Jekyll was a great option when it comes to creative website control, because *everyone* likes control. Since I host on WebFaction, I needed a smart way to deploy a Jekyll Blog. After hours of scratching my head, I stubmled upon this [tutorial from Guillermo Garron](http://www.garron.me/en/blog/host-your-jekyll-blog-on-webfaction.html). 
<br><br>
Essentially this process is to generate my site locally then rsync to a static-only site created on WebFaction. I performed the following instruction to install the software on the WebFaction servers by installing the gems and updating the path through the bashrc file:

**Important!** In the tutorial, it is not mentioned to install the 'therubyracer' gem. But you do need to install it.
{: .notice }

{% highlight html %}
$ export GEM_HOME=$HOME/gems
$ source ./bashrc
$ gem2.0 install jekyll
$ gem2.0 install RedCloth
$ gem2.0 install therubyracer
$ export PATH=$HOME/gems/bin:$PATH
$ source .bashrc
{% endhighlight %}

Next I set up a bare git repository where we will put our git hook as seen here.

{% highlight html %}
$ cd webapps/git/repos/
$ mkdir doswah.git
$ cd doswah.git
$ git init bare
{% endhighlight %}

Afterwards, I created a 'post-update' file in the hooks folder.

{% highlight html %}
$ cd hooks
$ vi post-update
{% endhighlight %}

It should have these following lines. For your specific project you will need to edit line 3 and change the path of 'REPOSITORY_DIR' to your project .git folder you just created. On line 12, you must edit the last path to where your web application is. In my case, it is in the 'webapps' folder. In all other instances you see 'doswah' change it to your username.

{% highlight html linenos %}
#!/bin/bash
# Declare variables
REPOSITORY_DIR="/home/doswah/git/repos/doswah.git"
DEPLOY_FIR="/home/doswah/tmp/jekyll-tmp"
DEPLOY_TMP_DIR=$(mktemp /home/doswah/tmp/jekyll.deploy.XXXXX)
rm -f $DEPLOY_TMP_DIR
git clone $REPOSITORY_DIR $DEPLOY_TMP_DIR
cd $DEPLOY_TMP_DIR
jekyll build -d $DEPLOY_DIR
rm -rf $DEPLOY_TMP_DIR
cd /
rsync -vrz -checksum -e ssh -delete $DEPLOY_DIR /home/doswah/webapps/doswah
{% endhighlight %}

After that is done. You can create your git remote on your machine locally.

{% highlight html %}
$ git remote add webfaction doswah@web351.webfaction.com:/home/doswah/git/repos/doswah.git
$ git push doswah
{% endhighlight %}



