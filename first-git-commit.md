# Getting Ready to do Our First `Commit`

But first, what is a `commit`?

If you're familiar with games, think of it like a check/save point in your game. When you make a commit, it takes a snapshot of your code at that point in time.

Let's try doing our first `commit`:

```
git commit -m 'HELLO COMMIT'
```

When you run the command something doesn't seem right though. If we read the output you will notice something:

```
On branch master
Your branch is up to date with 'origin/master'.

Untracked files:
        cool-file.md

no changes added to commit
```

## Adding Files to a Commit

If you look at the last line it says `no changes added to commit`. We accidentally skipped an important step in the commit process. Before we can commit our files, we need to add them so they are `staged` for committing.

To `stage` a file you will need to use the following command:

```
git add <arguments>
```

This is another command you will need to use very often. If you need to `commit` you must first `add` files to be committed.

Lets add our file for `cool-file.md` for commit using the following command:

```
git add cool-file.md
```

Let's try checking the `status` of our repository since we just did the `add` command and see how things look.

```
git status
```

You should see something like this:

```
On branch master
Your branch is up to date with 'origin/master'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
        new file:   cool-file.md
```

If you read what `status` is telling you, you will see that it is telling you what files are going to be "committed" when your run `commit` command. Take a look under the line `Changes to be committed:`

Now that we have our `cool-file.md` added and ready for `commit`, let's run the command!

## Finally Committing Our Changes

```
git commit -m 'HELLO COMMIT'
```

After running the command you should see something close to the following output below:

```
[master (root-commit) 837f2be] HELLO COMMIT
 1 files changed, 0 insertions(+), 0 deletions(-)
 create mode 100644 cool-file.md
```

If you inspect the output, you should see the commit message used, and the file(s) that were committed.

[Next](committing-file-changes.md)
