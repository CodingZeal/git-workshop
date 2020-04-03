# Getting Started with Git

## Installing

You can install `git` by visting https://git-scm.com/downloads
This will install `git` in a command line interface that will be the main we will be using `git` for most of this workshop.

## Lets Make a Project

```
mkdir hello-git
```

```
cd hello-git
```

```
touch cool-file.md

echo $null >> cool-file.md
```
## Doing Our First Git Command

In order to use Git in any project, the first thing you need to do is initialize Git.
```
git init
```
The git init command creates a new Git repository. Running this command in any folder will create a Git repository and this is the very first command you use to get started with a new Git repo.

After running the command you should see something like the following in your terminal window.
```
Initialized empty Git repository in /blah/blah/blah/.git/
```
[Next](git-status.md)
