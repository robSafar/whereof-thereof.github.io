---
layout: post
title: "Pierre Menard, Author of the Quixote, Unbound"
permalink: pierre-menard-author-quixote-unbound
---

##An experiment in cybertext

> The visible work left by this novelist is easily and briefly enumerated…

<blockquote class="twitter-tweet" lang="en"><p>My new experiment, hopefully featuring a Twitter card too. Hopefully. Blog to follow.  <a href="http://t.co/qyGmOztUgp">http://t.co/qyGmOztUgp</a></p>&mdash; rob safar (@robsafar) <a href="https://twitter.com/robsafar/status/477174747131052032">June 12, 2014</a></blockquote>
<script async src="//platform.twitter.com/widgets.js" charset="utf-8"></script>

I’d encountered *[Book Unbound](http://muse.jhu.edu/journals/postmodern_culture/v007/7.3cayley.html)* by John Cayley when reading Espen Aarseth’s *Cybertext: Perspectives on Ergodic Literature* as an example of a cybertextual narratonomy at play. Published online in 1997, the text can be divided into array and algorithm. The array is a collection of sentences and phrases that, by means of the algorithm, are assembled through some ‘non-trivial’ effort from the reader to make up the text. Upon reading about it, my first reaction was to check if there exists an iPhone app which simulates it. To my knowledge, no such app exists on any mobile platform. Rather than wait until I learn Objective-C or Java (likely many years ahead, if ever) I have opted to emulate this textonomy using JavaScript and HTML. At least no install is required.

However, lacking the original *Book Unbound* from which to obtain that array, another source of content was needed. A result of lacking the original and having read some enthusiastic remarks about it, I was loathe to write my own. The romantic, perhaps naive, impression I have is of a work comprised of elements that are specifically designed to be encountered cybertextually, almost like the ‘fortunes’ from a cookie but more modular and poetic. My poetry is much worse than my prose.

Aarseth mentioned two different short stories by Jorge Luis Borges in his book, which is always a pleasure to see, but I was surprised when *Pierre Menard, Author of the Quixote* didn’t appear in his discussion of poststructuralism’s position that any text can be read subjectively. I can only assume that two Borges references was plenty for one chapter. The Menard recounts a story about the work of a 20th century author who takes it upon himself to write the *Quixote* — not to rewrite Cervantes’ *Quixote*, but to write it. Borges’ description goes well beyond any paultry poststructuralist statement of the subjectivity of reading and into the subjectivity of writing.

> It is a revelation to compare Menard’s Don Quixote with Cervantes’. The latter, for example, wrote (part one, chapter nine):

>>truth, whose mother is history, rival of time, depository of deeds, witness of the past, exemplar and adviser to the present, and the future’s counselor.

> Written in the seventeenth century, written by the “lay genius” Cervantes, this enumeration is a mere rhetorical praise of history. Menard, on the other hand, writes:

>>truth, whose mother is history, rival of time, depository of deeds, witness of the past, exemplar and adviser to the present, and the future’s counselor.

> History, the mother of truth: the idea is astounding. Menard, a contemporary of William James, does not define history as an inquiry into reality but as its origin. Historical truth, for him, is not what has happened; it is what we judge to have happened. The final phrases — exemplar and adviser to the present, and the future’s counselor — are brazenly pragmatic.

It made only too much sense to re-text the *Menard*. It’s well meta.

The result of this attempted synthesis is a division of the Menard into its 146 respective sentences and their treatment as lexias, or at least ‘sub-’lexias where opportunities for intervention are presented between them. The reader has the option to add more lexias or to remove lexias, creating their own reordered version of the original (translated) text. Arriving at a modified factorial of this arrangement*, we find that there are over **1.6 × 10^252** permutations of this work — plenty to regard each journey through the text as unique. Even reading perpetually at 1 permutation per minute, it would still take more than 3.7 x 10^244 millennia to read every one, even if each possible permutation was encountered respectively and we treated as identical different ways of arriving at the same permutation.

> *Of 146 lexias, lexia[0] is always first, and can only be present or absent for any permutation: so double the factorial of the total lexias minus one gives us the number of possible permutations.*

> 145! x 2 = 1609585211494398388969805851559612554219994878015001232689490562094230824747293042821700963759679298454878596460597830039626216443303327319144883218817113835478298631811985622823733271572151049203671631285586605008486400000000000000000000000000000000000

Once the experiment was made, it seemed appropriate to write some text about the (cyber-)re-texting of a text about a modernist re-texting of a text. Hence the piece you are reading now.

<hr>

This was a kind of examination into the singularity of lexias (to the point where we will now use the terms *lexia* and *‘sub-’lexia* interchangeably) and an illustration of the technical difference between cybertext and hypertext. We conclude, somewhat ontologically, that JavaScript applied in textology is more than hypertextual (unlike HTML which, somewhat ontologically, is little more than hypertextual). We might want to conclude that any programming language is by its nature cybertextual and that markup languages are hypertextual — this should not be controversial. What may be controversial is the criticism of hypertextual narratonomy that it merely ‘points’ (a very limited and directing form of interaction). Having devised an algorithm to open up more forms of interaction — based on a very syntactically stubborn artificial language — I am not so sure that cybertextual narratonomy, in fact any language, artificial or otherwise, doesn’t ‘merely’ point as well. Poststructuralism be fucked. That there is no fixed signified for a signifier doesn’t mean that the signifier doesn’t still *point*.

In terms of the utility of the articulated solution, it seems likely that a purely JS approach might have yeilded more elegant & efficient results. Short of defending any flaws in the scripts in this file, I do want to briefly state the rationales behind some of the technical decisions underpinning this piece.

The full list of lexia, from which random lexias are selected and added to the visible narrative, are stored in hypertext markup in the document. The principle reason for this was so that the original text is within the new document, rather than abstracted in an SEO-unfriendly array. An implication of this is that in a cybertext document the sub-lexias may be arranged by the reader but they do exist in some state of original linearity — arbitrarily pre-arranged. This may not be necessary for all cybertexts, but is inevitable for any cybertext that uses a computing device as its medium.

The first lexia of the *Menard* in *Menard Unbound* is fixed. It appears first, in fact it is already present, although it can be removed. This was a reflexive decision when building the code, but one that was maintained by the perfect introduction by way of a double-meaning it gave to this piece. The *“visible”* work left by “this” novelist: a more appropriate description metatag was not forthcoming.

Once any lexia has been rendered visible after being randomly selected from the remaining invisible lexias, it cannot be moved. It can be removed, however. This decision was taken early and I am not sure if this is a feature of *Book Unbound*. Nonetheless, as Creeley puts it: “As soon as / I speak, I / speaks”. Giving the impression that the reader can ‘undo’ what has been read would be misleading, I feel.

Editing down the sentences of the *Menard* into appropriately marked-up lexias seemed a lengthy task but took less time than the programming process. A further decision was made regarding altering punctuation. In some cases where multiple sentences were contained within brackets, the brackets were removed in order to control the validity of the outputted punctuation — otherwise it was quite possible that a closing bracket could precede an open one. Additionally, an ordered list was butchered for its content and the remaining carcass of a. to s. was left unused. Exerting such an editorial influence over the original *Menard* was not taken lightly.

The absence of transitional animations is something I have yet to resolve, a result of the way in which the lexias are placed as `<span>`s within the narrative `<p>` and their removal is effected by reducing their content to nothing. In future I hope to redeploy this experiment in a tidier fashion, using markup that better allows for the CSS transition property to be applied.

<hr>

The apparent absence of *Book Unbound* is a deep shame. It would have been better, I feel, or more fitting with the ethos of the *Menard*, to have rewritten *Book Unbound* word for word, to see if I could mean something quite different in a textually identical re-telling. These two stories pivot against one another, the absence of one is the introduction of the other in the framework laid out in *Pierre Menard, Unbound*.

If anybody can point me in the direction of the original *Book Unbound* HyperCard file, I would be extremely grateful.

<hr>

* [Read Pierre Menard, Unbound](http://whereof.thereof.co.uk/MenardUnbound)