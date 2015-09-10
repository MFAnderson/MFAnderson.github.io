---
layout: post
title: "Testing is cool and good: How I learned to stop cowboying and love the Assert"
---


Confession: I used to hate tests. I thought they were a waste of time because
they were a pain in the ass to write, I couldn't get them to test all the sweet
logic I wrote into my `class Foo extends JFrame`, and besides, I'm smart,
clearly I know that my code works.  I was also a complete fucking idiot. No,
seriously, if any of the arguments above ring true to you in any capacity
beyond "Hmm, yes, I too remember being young and stupid" then
please never write code for anyone ever until you've rectified that.

These days I'm more of a test evangelist, or maybe a test masochist. I take
perverse joy in jumping into legacy code bases and tearing into their tests to
see what actually works, what is actually tested, and what needs to be done
before we get started making whatever changes we've been brought in to make.
Tracking down `assertNotNulls` and `//assertThats` is my _jam_, in the sort of
way that something that makes you cuss and angrily `git blame` the file can
be someone's jam. When it's time to write new functionality, I have a hard time
__not__ doing TDD.

A lot of people who are far smarter and more experienced than me have written
loads of good things about _how_ to test, but I have not personally seen much
writing that talks about _why_ you should test beyond abstract "shorter feedback
loop", "build quality in" notions. Valid notions to be sure, but not a particularly
compelling argument for your average developer who just wants to enjoy their work.

I initially aspired to try to explain in detail why I like tests and testing, but
after a good deal of gnashing of keys I've come to the conclusion that maybe there's
a reason these smarter people focus on the how and only abstract notions of why.
Nonetheless, I shall endeavour to try to encapsulate my feelings in a lovely list.

1. __Where to start__: There was a time when my development practice when starting a new
piece of work was only marginally more sophisticated than smashing my face
against the keyboard until the app stands up and then seeing all the things it
doesn't do the way I want. It turns out that writing a test describing a discrete piece
of functionality and making it pass is a remarkably effective alternative.
2. __When to stop__: Similarly, the notion of "done" used to be incredibly nebulous.
While not flawless, the heuristic of "you're done when you can't think of another
test to write" is incredibly empowering.
3. __What to write/How to design__: Tests, and particularly TDD, encourage the writing
of extensible code which is easy to reason about. While it is still entirely possible
to write a bunch of complete nonsense, testing can help guide the code towards
good practices like dependency injection, minimizing side effects, and limiting
the responsibilities of single methods/functions.

<!-- -->

Sadly I realize that a 3 point list is unlikely to convince anyone who is less
than enamoured with testing to change their mind, but worse still is that in the
unlikely event that anyone's interest is piqued, I have nothing to offer in terms
of how to go about starting to test effectively. [Test Driven Development By Example][tdd]
is a reasonably interesting book, but did nothing to actually teach me how to
walk the walk. All I can say is that if you are very very extremely unbelievably lucky,
you will have the good fortune to spend a couple of days with a practitioner
as skilled at teaching as [Bill Schofield][bill], who honestly taught me more in 10
hours of pairing than I would have ever believed possible.


__Next on the blog docket__: Maven and Continuous Delivery: a match made by a real asshole?


[bill]: https://twitter.com/Bill_Schofield
[tdd]: http://www.amazon.com/Test-Driven-Development-By-Example/dp/0321146530
