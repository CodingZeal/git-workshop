---
marp: true
---

# Introduction to Git

From `git init` to `git push origin master` and more

---

# Erik (Gooseman) Guzman

Senior Fullstack Engineer @ Coding Zeal
Live Coder on Twitch.tv
@Talk2MeGooseman

---

# What is a Version Control System (a.k.a Source Control Management)?

It is tool used to track changes in code and other text files. It also provides a running history of code development and help to resolve conflicts when merging contributions from multiple sources.

---

# How I like to internalize the idea

It's like journal or log of all the changes that you have made to file and you can go back in time to look at what thing use to look like.

---

# So why do we need a SCM?

We make mistakes all the time, it's only natural. So when a mistake does finally happen we're able to go back in time to our older changes and use those to fix or replace our problematic code.

---
<!-- _footer: Source https://git-scm.com/ -->

# Introducing Git

Git is a free and open source distributed version control system designed to handle everything from small to very large projects with speed and efficiency.

*Erik's Opinion: it's pretty cool.*

---

# Why Git is cool

Git has a lot of cool features the make our development life easier like:

- Branches
- Distrubuted Development
- Pull Requests (Extra enhancement)

Dont worry if you dont understand any of this well touch on this things a much more.

---

# Getting Started with Git

You can install `git` by visting https://git-scm.com/downloads
This will install `git` in a command line interface that will be the main we will be using `git` for most of this workshop.

---

#

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

---

```
git init
```

```
Initialized empty Git repository in /blah/blah/blah/.git/
```

---

```
git status
```

```
On branch master

No commits yet

Untracked files:
  (use "git add <file>..." to include in what will be committed)

        cool-file.md

nothing added to commit but untracked files present (use "git add" to track)
```

---

```
git add <arguments>
```

```
git add .
```

---

```
git commit -m 'HELLO COMMIT'
```

```
[master (root-commit) 837f2be] HELLO COMMIT
 1 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 cool-file.md
```

---

```
echo 'this is an edit' >> cool-file.md
```

```
git add -p
```

```
diff --git a/cool-file.md b/cool-file.md
index e69de29..1385f26 100644
--- a/cool-file.md
+++ b/cool-file.md
@@ -0,0 +1 @@
+this is an edit
Stage this hunk [y,n,q,a,d,e,?]?
```

---

# What the heck is `Stage this hunk [y,n,q,a,d,e,?]?`?

```
y - stage this hunk
n - do not stage this hunk
q - quit; do not stage this hunk or any of the remaining ones
a - stage this hunk and all later hunks in the file
d - do not stage this hunk or any of the later hunks in the file
.
.
.
```

---

```
Stage this hunk [y,n,q,a,d,e,?]? y
```

---

```
git status
```

```
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   cool-file.md
```

```
git commit -m 'Added some text to cool-file'
```

---

```
touch super-secret-file.md

echo $null >> super-secret-file.md
```

```
git status
```

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        super-secret-file.md
```

---

# The Problem

super-secret-file.md is showing up as an item to commit.

Solved with `.gitignore`

```
touch .gitignore
# or if powershell
echo $null >> .gitignore
```
---

```
echo super-secret-file.md >> .gitignore
```

```
git status
```

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore
```

No more `super-secret-file.md`.

---

```
git add .gitignore
```

```
git commit -m 'Adding in the gitignore'
```
Now our super-secret-file.md will forever be ignored and never committed.

---

What is a remote repository? How to add one.

---

