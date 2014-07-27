---
layout: post
title: "My first markdown post"
permalink: my-first-markdown-post
---

I spent yesterday setting up my GitHub Pages site to use Jekyll, rather than the custom Bootstrap static markup I was using previously. I had wanted more control (and less *clutter*) than provided by Blogger and Tumblr (paying a monthly fee to have a WordPress site seemed excessive for my requirements), so I had cobbled together a basic framework that I was manually copying across to new .html files when new pages needed to be made. It wasn't too conducive to mobile contributions.

In fact, the last iteration of whereof.thereof.co.uk wasn't really a blog at all, rather a landing page with a link to my single completed project. I'd been blogging using Medium, which is a fine platform in itself, but for its simplicity and elegance I had sacrificed customisability. I'm thinking of bringing across a couple of select articles, and may well continue to use Medium for articles proper.

But this is now my blog. Quick, off-the-cuff brain dumps and tailored, code-dependent pieces alike will find their home here - bearing in mind the medium itself. Blogging hosted on GitHub motivates a certain kind of writing, whereas hosting on Medium motivates something a little different. 

Does this matter at all in the hypertextual environment? Do people pay any attention to the CMS or server software that the content they're engaging utilises? I think it matters to me, in the same way a nice notebook inspires a different kind of writing than a napkin might. Medium tends towards the older, typewriter style approach to writing (while remaining authentically hypertextual and markup-cognizant), whereas GitHub and GitHub Pages tends much more towards writing prose and code texts using a *computer*.

![A sample from Don Quixote volume 1, the 1928 Oxford University Press edition](https://whereofthereofmedia.s3.amazonaws.com/DonQuixote-1-9.jpg "A sample from Don Quixote volume 1, the 1928 Oxford University Press edition")

##Down is the new up
`##Down is the new up`

I wanted this blog post to be especially rich in markdown, a fully-fledged test of my new blog. Frankly, I'm more used to using a WYSIWYG with a markup editor for backup but having found that often wanting (especially if the markup editor isn't forthcoming) I'm looking forward to using markdown regularly outside of Reddit comments.

The biggest obstacle here, as far as I can currently perceive, is the absence of an easy image uploader. On the one hand, I could probably manage to upload images to the GitHub repository and reference them from there. For the previous incarnation of this site I'd been using Amazon S3 for speedy serving of larger images, and see no reason to discontinue for larger images. What I think I'm going to do is use Imgur for my image hosting, and reference any images for mobile posting from there. I've yet to place a Vine or use other social embedding via markdown, but I'm sure I'll get around to trying.

##Philosophy, media theory and code

As a budding student of Python and JavaScript, I certainly hope that *[Pierre Menard, Unbound](http://whereof.thereof.co.uk/MenardUnbound)* isn't my last project that will feature here. In fact, I was especially intrigued by the SlackPropagation post *[On "Geek" Versus "Nerd"](https://slackprop.wordpress.com/2013/06/03/on-geek-versus-nerd/)* that takes a distinctly Wittgensteinean approach to discovering meaning, so I'm trying to weigh up just how far outside my comfort zone a Twitter *meaning as use* engine might be. As I'm approaching the next half of my second Master's degree on Digital Media, this should continue to be my home for extra-curricular experimentation.

Perhaps if I can get the hang of integrating [rich snippets and structured data](https://support.google.com/webmasters/answer/99170?hl=en) into my blog, it may become worthwhile publishing some reviews and analyses of various media and items. Come to think of it, an idea is already forming about how I can achieve this, as well as other funky things like having custom Twitter Cards for each post. There's a handy `head.html` include file that I can use to call upon any special YAML front matter fields that I may be able to define per post...

I love the simple flexibility of Jekyll!

*postscript: I'll also maintain a list of the crucial resources used to build this site in the [About](http://whereof.thereof.co.uk/about) page.*
