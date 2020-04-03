# The Power of Git Branches

Branches are a super cool feature in Git that allows you to isolate the work you're doing to avoid issue when working with others, or doing things like upgrade work on the side.

## Creating a Branch

Let's try making a branch and get more into the details of what is going on. In your terminal:

```
git branch cool-file-upgrade
```

Ok, nothing happened. No feedback? Let's try running `git branch` and see what it says.

```
git branch
```

What we get back is:

```
  cool-file-upgrade
* master
```

We should see the branch we made `cool-file-upgrade.md` but what the heck `master` come from? `master` is a branch that Git automatically creates when you first ran `git init`, this special branch should reflect the latest working code.

## `Checkout` Our Branch

Now that we have our `cool-file-upgrade` branch created, we need to switch over to it. To do that we will use the command `checkout`. I like to think of `checkout` is like checking out a library book, when you run the command, you switch to the

```
git checkout cool-file-upgrade
```

```
Switched to branch 'cool-file-upgrade'
```

> `git branch cool-file-upgrade` and `git checkout cool-file-upgrade` are so common that this action has been combined in to `git checkout -b cool-file-upgrade`

## Commtting a Change on a New Branch

Edit `cool-file.md`

```
this is an edit

This is an edit on the cool-file-upgrade branch
```

`stage` the changes:

```
git add -p
```

`commit` our changes:

```
git commit -m 'Changing cool-file-upgrade branch'
```

Confirm everything looks good:

```
[master 307204c] Cool file master branch edit
 1 file changed, 2 insertion(+), 0 deletion(-)
```

In our branch any changes we make to current files and new files will be isolated to our branch. This makes it very easy to work with others when they are working on completely separate tasks so they you dont end up clobbering each other.

## Using `git log` to Check our `commit` History

To help illustrate how `commits` done on a branch are isolated from other work branches of work, we're going to use `git log` command.

Try it out:

```
git log
```

You should see at least a couple row of information displayed. `log` displays the history of `commits` made to your branch, the order is from newest to oldest. At the top we should see the `commit` we just made. Cool, to exit this view enter `q` for quit.

Now let's switch to our `master` branch using the `checkout` command.

```
git checkout master
```

Displays:

```
Switched to branch 'master'
```

Let's see the `commit` history for our `master` branch using the `log` command again.

```
git log
```

If you look at the latest `commit` you will see the `commit` message is from the work we had done before we started work on our `cool-file-upgrade` branch.

[Next](git-merge.md)
