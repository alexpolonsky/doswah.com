---
layout: about-page
permalink: /about/
tagline: Get to know me before I get to know you.
tags: [about, doswah, Jekyll, theme, responsive]
modified: 5-29-2014
comments: false
image:
  feature:
  credit: 
  creditlink:
---
<div class="post">
	<div style="float:left;width:200px;padding-right:30px">
		<img src="/images/about/aloha.png" style="max-width:100%; max-height:100%">
	</div>

	<div>
		<br>
		<b>dos·wah</b>
		<br>[doss waah]<br>
		<i>NOUN</i><br><br>
		   1. The name Joshua pronounced in a filipino accent. <br>2. <a href="https://www.instagram.com/doswah/">Let me show you</a> (with Instagram).
	</div>

</div>


<div class="post">
	<br><br><br>
	<hr>

	
	<h3>Let's Connect</h3>

	<div style="float:left;width:25%">
	<b style="padding-bottom:10px">Coding</b>
	{% if site.owner.github %}<a href="http://github.com/{{ site.owner.github }}" class="author-social" target="_blank"><i class="icon-github"></i> Github</a>{% endif %}
	</div>

	<div style="width:50%; padding 0px 100px 5px 100px; margin: 0px">
	<b style="padding:1px">Professional</b>
	{% if site.owner.linkedin %}<a href="http://linkedin.com/pub/{{ site.owner.linkedin }}" class="author-social" target="_blank"><i class="icon-linkedin"></i> LinkedIn</a>{% endif %}
	</div>

	<br>

	<div style="float:left;width:25%">
	<b style="padding:1px">Social</b>
	{% if site.owner.twitter %}<a href="http://twitter.com/{{ site.owner.twitter }}" class="author-social" target="_blank"><i class="icon-twitter"></i> Twitter</a>{% endif %}
	{% if site.owner.facebook %}<a href="http://facebook.com/{{ site.owner.facebook }}" class="author-social" target="_blank"><i class="icon-facebook"></i> Facebook</a>{% endif %}
	{% if site.owner.instagram %}<a href="http://instagram.com/{{ site.owner.instagram }}" class="author-social" target="_blank"><i class="icon-instagram"></i> Instagram</a>{% endif %}
	</div>

	<div style="width:50%; padding 0px 100px 5px 100px; margin: 0px">
	<br>
	{% if site.owner.pinterest %}<a href="http://www.pinterest.com/{{ site.owner.pinterest }}" class="author-social" target="_blank"><i class="icon-pinterest"></i> Pinterest</a>{% endif %}
	{% if site.owner.tumblr %}<a href="http://{{ site.owner.tumblr }}.tumblr.com" class="author-social" target="_blank"><i class="icon-tumblr"></i> Tumblr</a>{% endif %}
	{% if site.owner.stackoverflow %}<a href="http://stackoverflow.com/users/{{ site.owner.stackoverflow }}" class="author-social" target="_blank"><i class="icon-stackoverflow"></i> Stackoverflow</a>{% endif %}
	</div>
<!--
<div style="float:right;width:20%">
<br>

{% if site.owner.pinterest %}<a href="http://www.pinterest.com/{{ site.owner.pinterest }}" class="author-social" target="_blank"><i class="icon-pinterest"></i> Pinterest</a>{% endif %}
{% if site.owner.tumblr %}<a href="http://{{ site.owner.tumblr }}.tumblr.com" class="author-social" target="_blank"><i class="icon-tumblr"></i> Tumblr</a>{% endif %}
{% if site.owner.stackoverflow %}<a href="http://stackoverflow.com/users/{{ site.owner.stackoverflow }}" class="author-social" target="_blank"><i class="icon-stackoverflow"></i> Stackoverflow</a>{% endif %}
</div>

-->
</div>
