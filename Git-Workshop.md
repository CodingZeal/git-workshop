# The Power of Git Branches

```
git branch cool-file-upgrade
```

Nothing happened.

```
git branch
```

Should see.

```
  cool-file-upgrade
* master
```

Where the heck `master` come from?

Checkout like a library book

```
git checkout cool-file-upgrade
```

```
Switched to branch 'cool-file-upgrade'
```

> `git branch cool-file-upgrade` and `git checkout cool-file-upgrade` are so common that this action has been combined in to `git checkout -b cool-file-upgrade`

Edit `cool-file.md`
```
hey

This is an edit on the cool-file-upgrade branch
```

```
git add -p
```

```
git commit -m 'Changing cool-file-upgrade branch'
```

```
[master 307204c] Cool file master branch edit
 1 file changed, 2 insertion(+), 0 deletion(-)
```

# Merging on your Branch

Wait doing what?

Merge explanation

```
git checkout master
```

```
Switched to branch 'master'
```

`git merge <target branch>`

```
git merge cool-file-upgrade
```

# Handling Merge Conflicts

What is a Merge Conflict?

Going to make a situation where we will get a merge conflict.

```
git checkout -b branch-conflict
```

```
Switched to branch 'branch-conflict'
```

## Making an edit to `cool-file.md` on `branch-conflict`
```
hey

This is an edit on the cool-file-upgrade branch

Making a line change here on the branch-conflict
```

```
git add -p
```

```
git commit -m 'Making a change the will conflict'
```

```
[master 307204c] Making a change the will conflict
 1 file changed, 2 insertion(+), 0 deletion(-)
```

## Switch back to `master` branch

```
git checkout master
```

```
Switched to branch 'master'
```

Edit `cool-file.md` on the same line in your `master` branch.

```
hey

This is an edit on the cool-file-upgrade branch

Making a line change here on master
```

```
git add -p
```

```
git commit -m 'Making a change on master'
```

```
git merge branch-conflict
```

```
Auto-merging cool-file.md
CONFLICT (content): Merge conflict in cool-file.md
Automatic merge failed; fix conflicts and then commit the result.
```


## Resolving Merge Conflict



Open `cool-file.md`


```
<<<<<<< HEAD
Making a line change here on the branch-conflict
=======
Making a line change here on master
>>>>>>> branch-conflict
```
