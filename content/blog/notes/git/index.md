---
title: My Git Notes, Concepts and Commands
date: "2021-12-02T22:12:03.284Z"
description: 'My Git Notes, Concepts and Commands'
inHome: false
---

## Introduction

Learning Git is essential in software development, no matter what technology you use, or if you work individually or in a group.

Usually Git works in a formidable way if it is code oriented, because Git will be able to analyze the files, determine what changed, do code joins, and everything automatically.

Now, there is going to be a point where Git will not be able to do it automatically, as when two people touch the same code, a conflict occurs and in those cases Git needs that conflict to be resolved manually.

Facing conflicts is normal, there is no need to panic, and there are even techniques to avoid having a large number of conflicts.

We will only see the use of Git through the console command, in order to cover all the necessary concepts, then with that information learned it is easy for everyone to choose the graphical Git repository manager that they like the most.

## Concepts

### Repository

It is the name that Git gives to each code project, although a repository can store any type of content, not just programming code.

### Stage

Initially a repository has all its files untracked. Later we can add one, several or all the files to the "Stage" which we could understand with the analogy of a stage where a photo is going to be taken. We upload files to the stage (adding it to the stage) and then we take the picture (make a commit).

### Commit

Following the analogy of the concept of 'Stage', doing a commit is like taking a photo of all the files that are in the 'stage', that is, saving the current state of all those files and leaving it registered in the timeline of our Git repository.

## Commands

#### Know the installed version of Git

```
git --version
```

#### View the help content of the Git command

See general help:

```
git help
```

See help for a specific subcommand:

```
git help commit
```

#### Git initial setup

Configure the user's name:

```
git config --global user.name = "Fabian Karaben"
```

Configure the user's email:

```
git config --global user.email = "fabian@example.com"
```

View and optionally edit the current user settings:

```
git config --global -e
```

#### Initialize a repository

```
git init
```

#### View the repository status

This command displays information about commits, about the current branch, and more:

```
git status
```

#### Add and remove files from the 'stage'

Add a specific file to the stage:

```
git add index.html
```

Add all files to the stage:

```
git add .
```

Remove a specific file from the stage:

```
git reset index.html
```

#### Commits

Make a commit

```
git commit -m "A descriptive message for this commit"
```

