---
layout: page
title: Archive
---

{% for post in site.posts %}
*[ {{ post.title }} ]({{ post.url }}) &raquo; {{ post.date | date_to_string }}
{% endfor %}

<hr>

I had the pleasure of being interviewed by *Det Kreativa Facket* about using open source software in the NGO world - [Filosofi ner på kodnivå](http://www.dik.se/nyheter/2014/okt/filosofi-ner-paa-kodnivaa/) *("Philosophy Down to the Code Level" in Swedish)*.

You can also visit [@robsafar on Medium](http://medium.com/@robsafar) to read other blog posts penned by my good self.


<div id="feed"><h2>Elsewhereof:</h2></div>

<!-- Get the RSS API from the horse's mouth: https://developers.google.com/feed/v1/devguide -->
<script type="text/javascript" src="https://www.google.com/jsapi"></script>
<script type="text/javascript">
google.load("feeds", "1");
function initialize() {
var feed = new google.feeds.Feed("http://medium.com/feed/@robsafar");
feed.load(function(result) {
if (!result.error) {
var container = document.getElementById("feed");
for (var i = 0; i < result.feed.entries.length; i++) {
var entry = result.feed.entries[i];
var div = document.createElement("div");
div.className = "feedMedium";
var link = div.appendChild(document.createElement("a"));
link.href = entry.link;
link.appendChild(document.createTextNode(entry.title));
var span = div.appendChild(document.createElement("span"));
var info = entry.contentSnippet.replace("Continue reading on Medium", "");
span.innerHTML = ' - ' + info;
container.appendChild(div);
}
}
});
}
google.setOnLoadCallback(initialize);
</script>