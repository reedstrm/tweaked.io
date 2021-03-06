tweaked.io
==========

This repository contains the source of the (new) website http://tweaked.io/


Content Policy
--------------

The intention behind this site is that there will be one *concise* page
of content for each of the major servers in common use.

For example:

* Apache 2.x.
* nginx.
* lighttpd.
* mysql
* nfs
* glusterfs

I explicitly do not intend to cover the optimization of applications
such as Magento, Wordpress, or similar.  The reason for this is that
too many variables are at play, and new releases would quickly render
documentation obsolete.

By contrast most of the "well known" servers don't release too frequently.

(Although there certainly are some that do.)


Implementation Details
----------------------

The website is built via the [templer](https://github.com/skx/templer)
static-site generator.

If you have `templer` installed just run:

    make serve

Then open your browser at http://localhost:4433/

Dependencies include:

* [python-slimmer](http://packages.debian.org/python-slimmer)
   * Used to minify the CSS
* The following Perl-modules are templer dependencies:
   * [Text::Markdown](http://packages.debian.org/libtext-markdown-perl)
   * [HTML::Template](http://packages.debian.org/libhtml-template-perl)

**NOTE**: If the python slimmer tool is unavailable the CSS will just be non-slimmed.  This is a non-fatal error.


Comments
--------

As the site is 100% static there is nothing dynamic at all.  Except for comments.

Comments are handled by GET/POST requests to

* http://comments.tweaked.io/comments

Each page which has comments-enabled has a distinct key, and that key is
used for both retrieval and submission.

This is an experimental facility and may be removed in the future, once
the cold-medicine has worn off.

The comment-server is pretty trivial, and written using Sinatra. The code
is available within the [comments/](comments/) directory.


Contact
-------

If wish to report issues please do feel free to mail me direct, or
report them in the github tracker.


Steve
--