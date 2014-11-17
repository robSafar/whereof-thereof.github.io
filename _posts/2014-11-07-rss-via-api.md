---
layout: post
title: "RSS via API"
permalink: rss-via-api
---

The latest addition to this site is another piece of rudimentary JavaScripting. The trouble with maintaining blogs with a particular remit is that it often makes sense to set up a new blog for every topic you want to write about. Sure - you can divide one blog into categories, but unless you're an organisation with so much content that it would be impossible to navigate otherwise, there are advantages to having one place where you talk about one thing, and so on. If someone lands on my site to read a post about Drupal, they're not really likely to then go on to read something I've written about technological determinism straight afterwards just because it's on the same domain. Whatever, I'm sure there are counter-arguments on either side, but I'm very much used to having my digital footprint spread over several different sites.

That said, I do see advantages to being able to tie all these things together into some slightly more consistent 'digital identity'. [My Twitter profile](http://twitter.com/robsafar), [my Google+ persona](http://plus.google.com/u/0/+RobSafar), [my Github account](http://github.com/whereof-thereof), [my Medium blogs](http://medium.com/@robsafar) and so on all link to `whereof.thereof.co.uk`, so it makes sense to have this as my *Rome*, where all roads lead. As I'm preparing to set up another blog (though I'm undecided which platform will be best suited to it) there's going to be a greater need to tie these things together.

I could just provide a link to my various other sites, which I do to some of my main social accounts in the footer, but when linking to other blogs it makes more sense to actually syndicate the content across. A reader is much more likely to want to click away to something else I've written if they know what it is, and RSS is pretty much the only way to get those details across platforms.

If you have [a wee Google around for embedding RSS feeds](http://lmgtfy.com/?q=embed+rss+feed), you'll find a host of 'widgets' (urgh) that will do the job for you, with varying amounts of customisability. By and large, they'll have their own styles that you can adapt, and some will even provide you with some naked HTML to shove wherever you like. I must say that none of these really appealed to me that much as it was still quite closed off - if I want to change the *text* of what comes through in the feed, I can't do that.

A notable illustration of this is the RSS feeds that Medium now provides - by using the url `http://medium.com/feed/[USERNAME]` you can draw a neat little feed from a Medium account or, I think, a collection. However, in the `<description>` markup every field ends with *"Continue reading on Medium"*, which I'd rather wasn't there, frankly. A by-the-numbers RSS widget won't grant me that control.

##Google's Feed API

Some further digging brought forward a forum post (possibly stackexchange, but it's lost to me now) that mentioned [Google's Feed API](https://developers.google.com/feed/v1/devguide) as a relatively light and simple solution. And it certainly is! Provided this API doesn't go the way of Google Reader (yes, I'm still upset about that, Currents was almost up to scratch and Play Newsstand is just not the same by any stretch) this solution should have some longevity.

Out of the box, you'll see that they provide [the code to load in the relevant XML](https://developers.google.com/feed/v1/devguide#usingApis) but that code will only display a list of titles. That's no good - but they do provide the [`json` values](https://developers.google.com/feed/v1/devguide#resultJson) for other elements in the RSS markup, which is what you'll need.

So what we're starting off with is:

{% highlight javascript %}
function initialize() {
var feed = new google.feeds.Feed("http://fastpshb.appspot.com/feed/1/fastpshb");
feed.load(function(result) {
if (!result.error) {
var container = document.getElementById("feed");
for (var i = 0; i < result.feed.entries.length; i++) {
var entry = result.feed.entries[i];
var div = document.createElement("div");
div.appendChild(document.createTextNode(entry.title));
container.appendChild(div);
}
}
});
}
{% endhighlight %}

Note that you'll need a somewhat dormant `<div id="feed"></div>` for this JS to populate, but it's also worth noting that if you have any contents in there already they won't be overwritten - the new content will be appended to the end.

I'm not going to note which feed url you need to switch out (c'mon), but I will provide the JS to have this render as a linked title followed by the post description. I'll also demonstrate what I needed to do to get rid of the afore-mentioned "Continue reading on Medium" text.

So firstly we want to wrap the inserted title with an `<a>` element so we can make it a link. You'll see above that the line `div.appendChild(document.createTextNode(entry.title));` adds the `title` to the `div`, which puts it at the top of that little hierarchy. Let's break that up a little. On the line above, we see that the entry's `<div>` is being created, so straight after that is where we want to insert our opening `<a>` with the following: `var link = div.appendChild(document.createElement("a"));`. All we need to do then is specify the address we want this `<a>` to direct towards, so we'll follow that line with `link.href = entry.link;`. All that's required now is to ensure that the title text is actually added inside the link rather than appended afterwards within the `<div>`, so we'll need to replace the 'entry.title' line as follows: `link.appendChild(document.createTextNode(entry.title));`.

You'll see in that last instance we only replaced the first variable, from `div.` to `link.`. That's it - you've turned the title into a link to that particular item. Now the last line in this code is only rounding off the entry, so just before that you'll want to add your description. I used the following:

{% highlight javascript %}
var span = div.appendChild(document.createElement("span"));
var info = entry.contentSnippet.replace("Continue reading on Medium", "");
span.innerHTML = ' - ' + info;
{% endhighlight %}

The second line here is what's cutting out that pesky 'read more' text, but looking at the first line you'll see that it's adding a `<span>` at the end of the `<div>`'s contents, and the last line specifies that the modified data from `entry.contentSnippet` should be inserted into that `<span>`.

The full code that I've used is this:

{% highlight javascript %}
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
{% endhighlight %}

I've also added a class to each entry-containing `<div>`, so I can style them a little easier. In my stylesheets, I've principally used a rule referring to `#feed div { }` to catch all feed entries in that space, but as I'll want to add other feeds in there in the future, this extra class will allow me to add styles for individual feeds/platforms.

And that's it! You should be able to see my version in action at the bottom of the [whereof.thereof homepage](http://whereof.thereof.co.uk) and on the [Archive](http://whereof.thereof.co.uk/archive). 

*postscript: I should also note that all of the above code works just fine in your `<body>` rather than in the `<head>` (as recommended on the [Feed API page](https://developers.google.com/feed/v1/devguide)), which I opted for as adding extra code to all of my pages might have been redundant.*