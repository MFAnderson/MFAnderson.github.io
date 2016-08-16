---
layout: post
title: Functional tests: a useless term
---

At ThoughtWorks we talk about testing a lot. TDD is considered a given, developers are expected to
be involved in writing all levels of automated tests, and "the correct way" to test gets debated a
lot. You'll find plenty of adherents of Kent Beck's style of TDD, but there are plenty of London
school adherents too (the London school is pretty clearly laid out in the book Growing Object
Oriented Software Guided by Tests, written by two ex-ThoughtWorkers).

The perennial bugbear I encounter when discussing testing with my colleagues is what exactly is
meant by "functional test". Most people seem to agree that there is a place for "functional tests"
somewhere in the test pyramid of a given project, but the meaning varies wildly. Sometimes it's
being used to refer to full-on Selenium driven UI tests going through entire user journeys; other
times it's just exercising a single service by invoking an entry point method and stubbing all
external dependencies including the persistence layer.  Frequently it's somewhere between these two
extremes. 

No other category of test seems to have as much ambiguity; people certainly have debates about _how_
to do certain types of tests (classicist vs mockist unit tests; in-process vs out-of-process
component tests) but I've not yet encountered any where there is fundamental lack of consensus on
the coarse-grain scope of what is being tested. What's more, I've not yet encountered a definition
of functional test that doesn't have an alternative name with a less ambiguous meaning. Even if
you've never encountered the term before I would suspect that you can pretty readily intuit the
scope of an 'automated 
