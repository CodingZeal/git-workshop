# How to Never Commit Certain Files

Let's now create a brand new file called `super-secret-file.md`. This file is going to have some super secret stuff we NEVER want to `commit`. Since Git remembers everything we ever `commit`, it will make it super easy for someone to look into our history and find out what's inside our secret file.

## Creating a Super Top Secret File

```
touch super-secret-file.md
# Or on powershell
echo $null >> super-secret-file.md
```

After creating our file, let's check the `status` of our current changes.

```
git status
```

We should see the following:

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        super-secret-file.md
```

## Using `.gitignore` to Hide Files from Git

Uh oh, we can see that git sees our new `super-secret-file.md`. Even though were not going to try to `add` this file, but what happens in the future if we forget and accidentally do?

There is a way to have Git to never ever allow this file to be committed. Enter the `.gitignore` file.

In a `.gitignore` file you will list all the files you want Git to ignore and never include an any future commit.

Now let's make a `.gitignore`.

```
touch .gitignore
# or if powershell
echo $null >> .gitignore
```

Next we need to add `super-secret-file.md` to our `.gitignore`.

```
echo super-secret-file.md >> .gitignore
```

## Verifying Super Top Secret File is Ignored

Now thats done, let's check the  `status` and see what Git says now.

```
git status
```

We should get:

```
Untracked files:
  (use "git add <file>..." to include in what will be committed)

        .gitignore
```

Oh hey! No more `super-secret-file.md` but we do have `.gitignore` file now. Mission accomplished! Now our super secret files will never have the chance to be committed. Remember to do this any time you have files you never want to be committed to Git.

Let's `commit` our changes, first `add` our file.

```
git add .gitignore
```

Now for the `commit`.

```
git commit -m 'Adding in the gitignore'
```
[Next](intro-github.md)
