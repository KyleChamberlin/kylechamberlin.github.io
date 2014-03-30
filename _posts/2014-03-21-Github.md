---
layout : post
category : git
tags : [git, thoughts, learning, collaboration]
tagline : "collaboration for teams"
---

{% include JB/setup %}

Pull Requests
=============

## A tool for collaboration

I have just begun really using github for my organization at work, and because of that I am 
learning some of the features of github that I had previously ignored, or been oblivious of. 

One of the biggest parts of collaborating on github is the pull request. Everything on github
goes through pull requests. Fortunately github has provided a number of great nicities to make
it easier. I thought it might be a good idea to cover the *standard* workflow that makes github
work so well. 

# Setup

## Fork

Understanding the workflow that git expects you to use is paramount to collaborating well on code. 
So first things first, you'll need to have git installed, obviously. for the purposes of this 
we'll also need github, luckily github offers a number of tools that will help you get up and
running. [Here](http://github.com) you'll be able to sign up for an account if you don't already 
have one. The installer for the github client on Windows and OSX include git, so that is probably 
easiest way to get up and running. 

Once you are up and running with git, you need to identify the project you'd like to contribute to. 
I have taken the liberty of starting an Organization on github with a very plain repo, just a few 
ruby files. You are welcome to use that repo as a guinea pig during this process. [Link](https://github.com/LearningGitWorkflow/LearningGitWorkflow)

The first step is to fork the repo on github. *Unfortunately github doesn't yet support pull requests 
from repositories that weren't forked on github.* [Github's article on forking a repo](https://help.github.com/articles/fork-a-repo) 
is much better than anything I would give you, so you should read that.

## Clone

The next step is clone your fork to create a local working copy. To do this lets jump into the 
command line.

    $ git clone git@github.com:KyleChamberlin/LearningGitWorkflow.git
    Cloning into 'LearningGitWorkflow'...
    remote: Counting objects: 3, done.
    remote: Compressing objects: 100% (2/2), done.
    remote: Total 3 (delta 0), reused 3 (delta 0)
    Receiving objects: 100% (3/3), done.
    Checking connectivity... done.

Now that we have a working copy on our drive, lets move into that directory,

    $ cd LearningGitWorkflow

Here we could make our changes just like this, and everything would work as expected, however if we
really want to take advantage of the power of pull requests, we should first create a feature branch.

## Branch

The reason we want to create a branch for each feature/pull request we wish to make is that we can 
compartmentalize our changes to the master source. This allows you to make changes to different part 
of the source that aren't really related, and have them in seperate pull requests. I will explain how
this is so powerful later. 

In order to create a local branch for the feature we are going to add, or the bug we wish to fix, we 
can issue the following command

    $ git branch newFeature

Now it is important to note that this simply creates the branch to work on, however your working copy
is still on the master branch. Before you begin working on your feature you need to checkout the branch
you want to work on. 

    $ git checkout newFeature
    Switched to branch 'newFeature'

Now we are ready to make our changes. I should note that you can accomplish the same thing in a single
command, which is typically what I do. you would do that like this,

    $ git checkout -b newFeature

That command will both create the branch and check it out. 

# Making Changes

## Edit

If you are new to git, or version control in general, committing, and staging changes can seem 
tedious, or unnecessary. Let me tell you, it is neither. In fact, it is pretty much the best thing 
you'll learn to do. I can't over state how important committing early and often is. That is not to 
say that you should commit after every line of code, but when you make a change, like add a function 
or method, or refactor a variable, commit. The fewer changes in a commit, the easier it is to track
your changes. If you find that you've made a mistake, or broken a test, you can always rollback to 
a previous commit. All that said, let's cover how to stage your commits. 

## Staging

Once you have made a change, really any change, it is time to begin staging files. To begin let's 
check the status of our repo:

    $ git status
    On branch newFeature
    Changes not staged for commit:
      (use "git add <file>..." to update what will be committed)
	 (use "git checkout -- <file>..." to discard changes in working directory)

	       modified:  README.md

    no changes added to commit (use "git add" and/or "git commit -a")

There is a lot of information in that output, and git generally is very expressive and will try to 
help you along. so lets parse the information that we are getting here. 

Git tells us that we have made a change, but that change wont be included in the next commit. This 
can be confusing when you are starting out, I know it was for me. This is however a nice feature, 
git lets your pick and choose the changes to include in each commit. You see, when you are collaborating
on a project, you want your commits to read like a story of the steps from the original status (when 
you branched) to the finished status. The collaborators will want to review your changes, and a clean
commit history will help others follow your changes. 

So we will want to stage the files for inclusion that are part of the change we made. In the example 
I am using that means I need to add the README.md file so I can commit the changes that I made. 
In order to do that we simply need to follow the directions git gave us. 

## Commit


