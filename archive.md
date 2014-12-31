---
layout: page
title: Archive
---

I had the pleasure of being interviewed by *Det Kreativa Facket* about using open source software in the NGO world - [Filosofi ner på kodnivå](http://www.dik.se/nyheter/2014/okt/filosofi-ner-paa-kodnivaa/) *("Philosophy Down to the Code Level" in Swedish)*.

<hr>


<ul>
  {% for post in site.posts %}

    {% unless post.next %}
      <h3>{{ post.date | date: '%Y' }}</h3>
    {% else %}
      {% capture year %}{{ post.date | date: '%Y' }}{% endcapture %}
      {% capture nyear %}{{ post.next.date | date: '%Y' }}{% endcapture %}
      {% if year != nyear %}
        <h3>{{ post.date | date: '%Y' }}</h3>
      {% endif %}
    {% endunless %}

    <li>{{ post.date | date:"%d %b" }} &raquo; <a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>


