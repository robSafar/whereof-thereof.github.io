---
layout: page
title: Archive
---

{% for post in site.posts %}
* {{ post.date | date_to_string }} &raquo; [ {{ post.title }} ]({{ post.url }})
{% endfor %}

I had the pleasure of being interviewed by *Det Kreativa Facket* about using open source software in the NGO world - [Filosofi ner på kodnivå](http://www.dik.se/nyheter/2014/okt/filosofi-ner-paa-kodnivaa/) *("Philosophy Down to the Code Level" in Swedish)*.

You can also visit [@robsafar on Medium](http://medium.com/@robsafar) to read other blog posts penned by my good self.
