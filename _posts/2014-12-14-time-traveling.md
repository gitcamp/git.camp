---
layout: post
index: 1
title: "Time Traveling with git checkout"
---

In this video, I walk through the process of using git to view your repository’s 
contents at different points in time.

<iframe src="//player.vimeo.com/video/115069762?title=0&byline=0&portrait=0" width="100%" height="400" frameborder="0" webkitallowfullscreen mozallowfullscreen allowfullscreen></iframe> <p><a href="http://vimeo.com/115069762">02 - Time Traveling with git</a> from <a href="http://vimeo.com/user34026330">Jesse Shawl</a> on <a href="https://vimeo.com">Vimeo</a>.</p>

### Or, view the text version

Being able to navigate the history of your repository first requires
a better looking and more informational map.

Create an alias in your `~/.bashrc`:

    alias gl="git log --all --oneline --pretty --graph"

Or use mine:

    $ curl http://git.camp/gl >> ~/.bash_profile

## Checkout an old commit

    $ git checkout -b branch-name sha

This will move your HEAD to the specified sha and create a new branch all in one go.

Also, this updates your entire working directory to its state at the specified sha. 

## Detached HEAD state

If you checkout a commit without creating a new branch, you’ll end up in detached HEAD state.

    $ git checkout sha

It isn’t as scary as it sounds. Detached head state just means you’re
in a place that can only be referred to by its commit sha.

Without a branch name to refer to commits, you are in jeopardy of losing work. Don’t 
worry, git will warn you several times, and even if you ignore the warnings, you can
usually get back detached HEAD commits by taking a look at `git reflog`.

## Revert files to a previous state

    $ git checkout sha -- <file>

