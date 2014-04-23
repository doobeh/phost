Intro
-----

Welcome to *Phost's Development Log*, this is a real journal of development
I'm writing as I journey down the path of creating a functional, stable and
polished web publication platform.

What I hope will make this different from your usual online tutorial is that
I'm not going to cut any corners (deliberately) so that I'm left with a bare
skeleton of the finished app-- it's all well and good building a basic blog,
but I'm looking to build a real project that can be used by other people and
will hopefully, eventually, stand by itself.

In addition, I'm going to be approaching it from a TDD-lite design methodology,
this is mostly for selfish reasons, as I want to get more solid on the
practice, but I hope you will learn something from it too as I think it's
a really, really nice way to approach a project and actually end up with
a released product.

As for the project itself, well, that's the easy bit-- I'm going to be building
a clone of an existing project called `Ghost`_ which is built using `NodeJS`_.  I
picked Ghost because I like the UI, it's `MIT licensed`_, and I think that
Python deserves something as sleek as it.  I've used Ghost on a few VPS
servers and it always seems a bit of a memory hog, I'm hoping Python will prove
to be a little lighter, plus a whole lot more hackable.

As this is a development log, I fully expect to walk down dead-ends and have to
backtrack to solve problems, programming isn't a perfect straight line, often
we have to meander to find the right path to solve a particular feature or
problem.  When this happens, I'll do my best to make it clear to you, dear
reader, so you can skip ahead to the alternate solution if you wish.

I'm still deciding how to engineer this documentation, so it runs in tandem with
the development cycle.  I'm currently picturing using tagging within `Github`_ to
essentially version the code to a specific journal entry, so in addition to the
code snippets included in the journals, you can quickly download the point in
time code for that entry.

.. _Ghost: https://ghost.org
.. _Github: https://github.org
.. _NodeJS: https://nodejs.org
.. _MIT licensed: http://opensource.org/licenses/MIT