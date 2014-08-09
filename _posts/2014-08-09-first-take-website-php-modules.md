---
layout: post
title: "First Take: Webpage PHP Modules"
description: "Interweaving PHP and HTML for modular headers and footers."
modified: 2014-08-09 00:31:48 -1000
category: []
tags: []
image:
  feature: 
  credit: 
  creditlink: 
comments: 
share: 
---

After a few months of developing my web development skills, I slowly realized
how messy and intricate webpage files can get. This fueled to my desire toward 
finding cool ways to manage a webpage's organization.
<br><br>
Now each webpage consists of multiple modules such as the navigation bar, header wraps, various content, and 
the footer: 
<figure>
	<img src="/images/website_organization.jpg">
</figure>

I discovered from a [blog post by Kenny Luong](http://blog.kennyluong.com/php/) that creating 
PHP modules allows pages to utilize modules that have one dependency. 
I use this method on my personal site [joshuatrivera.com](http"//joshuatrivera.com)
by converting pages from .html to .php
<br><br> 
Here is a snippet of my *cumbersome* navigation bar at the beginning of all my pages.

{% highlight html %}
    <div class="navbar navbar-default navbar-fixed-top" role="navigation">
      <div class="container">
        <div class="navbar-header">
          <button type="button" class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">
            <span class="sr-only">Toggle navigation</span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
            <span class="icon-bar"></span>
          </button>
          <a class="navbar-brand" href="index.php">JTR</a>
        </div>
        <div class="navbar-collapse collapse navbar-right">
          <ul class="nav navbar-nav">
            <li class="active"><a href="index.php">HOME</a></li>
            <li><a href="resume.php">RESUME</a></li>
    		<li><a href="http://doswah.com">BLOG</a></li>       
            <li class="dropdown">
              <a href="#" class="dropdown-toggle" data-toggle="dropdown">PROJECTS <b class="caret"></b></a>
              <ul class="dropdown-menu">
                <li><a href="micromouse.php">MICROMOUSE</a></li>
              </ul>
            </li>
          </ul>
        </div>
       </div>
      </div>

{% endhighlight %}

I placed this snippet as a .php file in a folder of modules. 
Now to include the navigation bar in my index.php page, I just need to have:

{% highlight css %}
    <?php include('modules/menubar.php'); ?>
{% endhighlight %}

That's it. Pretty awesome right? This method helps my pages become modular and makes reading my webpage code easier for me.

**Remember!** Rename *both* your module snippet and webpage to a .php file
{: .notice}
