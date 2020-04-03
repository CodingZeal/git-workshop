# Committing Changes to a File

We have success created a very first commit and added our `cool-file.md` to our repository history.

Wait, there is nothing in our `cool-file.md`! Lets try editing our file and committing the changes.

Run the following command so we can add some text to our new file.
```
echo 'this is an edit' >> cool-file.md
```

## Introduction to `git add -p`

Now we want to `commit` our changes, but before we can `commit` you will have to `add` our file changes. But since we want to `commit` file changes we should use a different `add` command. You should use `add` with the `-p` argument.

Enter the following command:

```
git add -p
```

You should then see the following output asking you for input:
```
diff --git a/cool-file.md b/cool-file.md
index e69de29..1385f26 100644
--- a/cool-file.md
+++ b/cool-file.md
@@ -0,0 +1 @@
+this is an edit
Stage this hunk [y,n,q,a,d,e,?]?
```

## What the heck is `Stage this hunk [y,n,q,a,d,e,?]?`?

Yeah, whoa, that is some weird thing to read. If you dont enter anything in and just click the `enter/return` key you should see an explanation of wht all the arguments mean:
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

What we want to do is `stage` our `hunk` to be committed. When ever we use git `add` were always staging file changes, `add -p` give his full control of what we want to `add` to our `commit`.

Let's stage our file change by entering in `y`.

```
Stage this hunk [y,n,q,a,d,e,?]? y
```

## Confirming What We Will `Commit`

Now lets just do a `status` check and make sure our file change(s) are staged and ready to be committed.

```
git status
```

The `status` should confirm that `cool-file.md` is ready for commit.

```
Changes to be committed:
  (use "git reset HEAD <file>..." to unstage)

        modified:   cool-file.md
```

Let's create a new commit.

```
git commit -m 'Added some text to cool-file'
```

[Next](intro-gitignore.md)
