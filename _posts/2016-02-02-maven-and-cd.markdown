---
layout: post
title: Maven is not good, but also maybe not all that bad
---

I know a number of very smart people who hate Maven. Many have good reasons,
but to be frank Maven seems to engender a lot of dogmatic support/dismissal.
My experience has been a roller coaster from enthusiasm to uninformed hatred,
back to some amount of positivity before arriving at extremely reserved support
in limited situations. 

My first exposure to Maven was while working for a tiny start-up in Toronto;
it was my very first time getting paid to write code. I can't recall why (I think
it had something to do with an SVN to Git migration that I was also pushing?),
but somehow I ended up in the unenviable position of trying to overhaul the
existing build system. The starting state was a pretty bog standard hot mess
of Ant scripting. The build could run only if you had the code checked out to
`E:\Develop` (yes, Windows), and only if you were running it as the right user
and were using the Eclipse built-in Ant runner rather than a standalone Ant
distribution. The app in question was a desktop Java app built on top of
Eclipse's OSGi implementation, Equinox. I have no idea how Maven entered the
picture, but somehow I ended up embarking on refactoring the build of this
10+ OSGi plugin app to run in Maven with the help of a tool called Tycho. When
I was done the build was runnable on every developer's machine, and I remember
walking away from the experience with something of an appreciation for Maven.
The configuration had been a bit of a pain to figure out due to pretty sparse
documentation on the relevant plugins, but we were clearly miles ahead of the
complete clusterfluff we had been working with initially.

In the intervening years I've had the joys of working with Maven on various 
open source projects, as well as in massive enterprise environments. When I
started at ThoughtWorks I definitely bought the "ew, Maven" koolaid, but having
actually seen where it works and where it falls flat I feel a little more equipped
to discuss it now.

Let's start with the (arguably) good. Maven has opinions. Lots of them. It
knows how a Java project should be laid out and how to turn that into a package,
and it frankly doesn't have a lot of time for your bullshit waffling
over directory structure. It knows you might have some dependencies, and they
might have their own dependencies, and maybe some of those dependencies you only
need when you're running tests. So far so good. In this respect, if you're building
a self-contained Java library that has it's own simple set of tests and gets
sent out into the ether of Maven Central for other people to pull in as a compile-time
dependency, you're golden. If that's your use case I'd say you'd be hard-pressed
to find a better tool, because Gradle out of the box is going to give you about
the same amount of stuff but with the added price-tag of being slower.

These opinions are also largely where Maven starts getting in the way. First and
foremost among these is the Maven lifecycle. In Maven everything is tied to some
phase of the lifecycle, and trying to do things out of sequence or bypassing prior
steps is an exercise in frustration.
