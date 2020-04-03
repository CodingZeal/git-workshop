# Merging Your Branch

Great so we have a new feature `branch` of work containing changes we want to make to our `cool-file.md`, but how do we get those file back in to `master`?

This where the `merge` command comes in.

`Merge` is a command that will join the `commit` history from one `branch` into another branch. In this situation we want to have our `cool-file-upgrade` branch join with our `master` branch so it has all the changes we made.

First let's make sure were on `master`

```
git checkout master
```

Always double check output:

```
Switched to branch 'master'
```

Now we use `git merge <target branch>`

```
git merge cool-file-upgrade
```

Now the changes we had made on `cool-file-upgrade` are now in our `master` branch. Let's double check using `log` command.

```
git log
```
[Next](git-merge-conflicts.md)
