---
layout: post
title: python.el tip
published: true
---

I downloaded [emacs 24.3][a] the other day. One thing I ran into when loading python-mode was this.

    Only symbols are supported in `compiler-macro'

I googled it and was pointed to a github issue about using the proper python.el in the
emacs-24 branch. Then I remembered that python.el is included with emacs 24.3. I ran emacs
with

    --debug-init

and found that I had a previous version from elpa. I removed that
directory and all works again!

[a]: http://www.masteringemacs.org/articles/2013/03/11/whats-new-emacs-24-3/  "Whats new in emacs 24.3"
