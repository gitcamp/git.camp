---
layout: post
index: 1
---

In this video, I walk through the process of cleaning up a pull request
that contains a few changes too many.

<iframe src="//player.vimeo.com/video/114477924?title=0&byline=0&portrait=0" width="100%" height="400" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="http://vimeo.com/114477924">01 - Clean up Pull Requests</a> from <a href="http://vimeo.com/user34026330">Jesse Shawl</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

### Or, view the text version

There are three ways to mess up a pull request:

1. Adding a file that shouldn’t be there.
2. Editing a file that shouldn’t be edited.
3. Removing a file that shouldn’t be removed.

Here is how to undo these changes.

#### 1. Adding a file that shouldn’t be there

This one is the easiest to fix. Just remove the file:

    $ git rm <file>

#### 2. Editing a file that shouldn’t be edited.

Revert the file back to the upstream’s version:

    $ git checkout upstream/master -- <file>

This requires you to have the pull requestee repository
as a remote:

    $ git remote add upstream git@github.com:USER/REPO.git

#### 3. Removing a file that shouldn’t be removed.

To put back a file you’ve accidentally deleted, use the same method
as above:

    $ git checkout upstream/master -- <file>