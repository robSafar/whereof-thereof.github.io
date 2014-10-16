---
layout: page
title: Archive
---

* Visit [@robsafar on Medium](http://medium.com/@robsafar) to read other blog posts penned by my good self.
{% for post in site.posts %}
  * {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}