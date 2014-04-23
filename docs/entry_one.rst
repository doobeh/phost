First, you must create a universe [#cosmos]_
--------------------------------------------

To get to the starting line, first you need to put on your socks and the same
is true with any project-- there is always a degree of grunt-work required to
get to the point where you can get yourself to the point where you can begin
your development.

.. [#cosmos] The wonderful Carl Sagan said "If you wish to make an apple pie
             from scratch, you must first invent the universe."

A Project Directory Inside a Virtual World
==========================================

A good place to start is creating a directory to hold the project.  I'm going to
create a ``phost`` parent directory, then within there I will have a ``docs``
directory for my journal entries, and a ``phost`` for all my code.

.. sourcecode:: bash

    $ mkdir phost
    $ mkdir phost/doc
    $ mkdir phost/phost
    $ cd phost

From now on, I'm going to pretend we're always in the parent ``phost`` directory, so
if I mention going ``cd phost`` I mean the child directory, as I would if I said
``cd docs`` etc.

Next we'll need a virtual environment to install all the python libraries we'll
need, without interfering with our entire system.

.. sourcecode:: bash

    $ virtualenv .venv
    $ source .venv/bin/activate

If we need to get out of the virtual environment, we can just run ``deactivate``
within our terminal.  As a reminder, if you open a new terminal it won't have
your new virtual environment activated, you'll have to ``source`` activate it
again.


Documentation
=============

So, as I mentioned, I'd like to use Sphinx to document this projects evolution.
Sphinx is a very widely used documentation tool, you should learn it-- as should
I, hence my use of it here.  It allows me to insert highlighted source code
easily, and with a bit of luck, I can even get it to include tagged versions
of my code from `Github`_ when I get to that point.

But first things first, I need to install it:

.. sourcecode:: bash

    $ pip install sphinx
    $ cd doc
    $ sphinx-quickstart

It goes through a series of questions, author name, destinations.  I just accepted
all the defaults, I can always tweak them later if required.  It generated an
``docs/index.rst`` file, which I modified slightly, adding ``intro`` and ``entry_one``

.. sourcecode:: rst

    Welcome to phost's documentation!
    =================================

    Contents:

    .. toctree::
       :maxdepth: 2

       intro
       entry_one

    Indices and tables
    ==================

    * :ref:`genindex`
    * :ref:`modindex`
    * :ref:`search`

I then of course, created :file:`intro.rst` and :file:`entry_one.rst` alongside
the :file:`index.rst` and entered the beginnings of this very journal in them.
Very meta.

When I want to generate the pretty HTML documentation, all that's required is:

.. sourcecode:: bash

    $ cd docs
    $ make html

It will generate the documentation in :file:`docs/_build/html/` so just open up
:file:`index.html` to view the tasty, beautiful documentation.  Wait, no-- the
default theme is really quite horrible.  Let's fix that.

.. sourcecode:: bash

    $ pip install sphinx_rtd_theme

Then edit the :file:`docs/conf.py` file and add to the bottom:

.. sourcecode:: python

    import sphinx_rtd_theme
    html_theme = "sphinx_rtd_theme"
    html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]

now run :file:`make html` again, view the :file:`index.html` file and *now* you can
sit back and truly enjoy the beautiful documentation.  Thank you `Read The Docs`_
for the wonderful theme!

Seriously, having a nice bit of documentation, even only the two pages I have so
far, really does make you want to write more.

Source Control
==============

Code is really sneaky, it will try and get away from you.  You need source control
to keep it from wandering too far off course.  I'll be using it to both maintain
some sense of order over the progression of the project, enabling me to try out
ideas and quickly rewind them, or merge them if they prove useful.

In addition, I'll be tagging it to keep pace with these journal entries, that way
you can step through the development process with me, rather then just seeing the
finished project and being overwhelmed by it all.

The nice part is source control is pretty easy now, we've got `Github`_ to thank
for that, everyone uses it, you should too.

As a little time-saver, I like creating my :file:`.gitignore` file before I
initialize my git repository.  So I downloaded the :file:`Python.gitignore`
from the `Github .gitignore`_ repository, renamed it to :file:`.gitignore`
and shoved it into my project root.  Then I created my repo and added my
project files to it.

.. sourcecode:: bash

    $ git init
    $ git add * .gitignore
    $ git commit -m 'initial commit'


.. _Github .gitignore: https://github.com/github/gitignore
.. _Github: https://github.com
.. _Read The Docs: https://readthedocs.org