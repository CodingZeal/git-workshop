# Handling Merge Conflicts

What is a Merge Conflict?

> A merge conflict is an event that occurs when Git is unable to automatically resolve differences in code between two commits. When all the changes in the code occur on different lines or in different files, Git will successfully merge commits without your help

To better understand when this will happen were going to make a situation where we will get a merge conflict.

Let's create a new `branch` so we can replicate a `merge conflict`.

```
git checkout -b branch-conflict
```

Check the output to make sure everything worked:

```
Switched to branch 'branch-conflict'
```

## Making an edit to `cool-file.md` on `branch-conflict`

Open `cool-file.md` lets add two new lines like below.

```
this is an edit

This is an edit on the cool-file-upgrade branch

Making a line change here on the branch-conflict
```

Once we have our changes and saved the file, let's go through our `commit` cycle:

```
git add -p
```

Confirm all your changes and `commit`.

```
git commit -m 'Making a change the will conflict'
```

Double check the `commit` was a success:

```
[master 307204c] Making a change the will conflict
 1 file changed, 2 insertion(+), 0 deletion(-)
```

## Switch back to `master` branch

Now let's switch back to our `master` branch but this time were also going to make changes to the `cool-file.md` in our master branch.

`checkout` to switch to `master`:

```
git checkout master
```

Confirm we switch to `master`:

```
Switched to branch 'master'
```

Now lets also do an edit to `cool-file.md` on the same line in your `master` branch. Edit your file to look like below:

```
this is an edit

This is an edit on the cool-file-upgrade branch

Making a line change here on master
```

One your changes are saved, let's `commit` them on `master`.

```
git add -p
```

Confirm your changes and `commit`.

```
git commit -m 'Making a change on master'
```

## Causing a Merge Conflict

At this point we should have "almost" identical changes on our `branch-conflict` branch and on `master` branch with some difference. Think if this like two people working on the same file at the same time.

Now let's try merge our `branch-conflict` with `master` and see what happens.

```
git merge branch-conflict
```

Uh oh, you should see a message like the following in your terminal.

```
Auto-merging cool-file.md
CONFLICT (content): Merge conflict in cool-file.md
Automatic merge failed; fix conflicts and then commit the result.
```

Git it telling us that it has issues trying to combine the changes in `cool-file.md` from our `branch-conflict` work. It's asking us to `fix conflicts and then commit the result.` Once we fix the  `merge conflict` Git will be happy to complete the merge.

We can confirm there is current a `merge conflict` but using the `status` command.

```
git status
```

```
On branch master
You have unmerged paths.
(fix conflicts and run "git commit")
(use "git merge --abort" to abort the merge)

Unmerged paths:
(use "git add <file>..." to mark resolution)

both modified:   cool-file.md
```

Let's learn how to do that.

## Resolving a Merge Conflict

To resolve a merge conflict we're going to have to go in and tell Git what changes we do want or even combine changes.

Let's open `cool-file.md` and see what is going on.

You should see in the file something the looks like the following:
```
<<<<<<< HEAD
Making a line change here on the master
=======
Making a line change here on branch-conflict
>>>>>>> branch-conflict
```

Whoa thats some funky syntax! This is Git's special syntax telling you what part of the code it has had issues combining.

The part above the `=======` will always be the changes on the branch you are currently on. In this case the changes are from `master` since were trying to get changes from `conflict-branch` in to `master`. The below `=======` is the changes coming in from `conflict-branch`.

Now is the time to make a decision about what the file should look like. Is the changes on `master` correct? Or is it the changes from `conflict-branch`? What about both are correct?

If you think `master` is correct then you should edit that part of the code to look like this:
```
Making a line change here on the master
```

If you think `conflict-branch` is correct then you should edit the code to look like this:
```
Making a line change here on branch-conflict
```

If its both:
```
Making a line change here on the master
Making a line change here on branch-conflict
```

What ever changes you make to the file will be committed. Make sure to save your changes.

Now we need to `stage` the changes to `cool-file.md` that resolves our `merge conflict`:

```
git add cool-file.md
```

Let's verify there are not other issue using `status`
```
git status
```

Now lets `commit`:

```
git commit -m 'Resolved merge conflict between master and conflict-branch'
```

Done!

For good measure let's also push our changes to Github so they are backed up there.

```
git push origin master
```

If you visit your repository on Github you should see the latest changes there.

[Next](creating-a-pull-request.md)
