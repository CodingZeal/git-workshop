# Pushing Changes to Github

After creating our repository we should get redirected to the "homepage" of `hello-git` on Github. Right now our repository is 100% empty because we have added any commits to it.

In order to add the all the changes we have in our local Git repository we will have to `push` them. But before we do that we will need to tell our local Git repository about our brand new `remote` repository on Github.

Github offers very simple instructions to get us started right on our repository homepage.

```
git remote add origin git@github.com:YOUR_USERNAME/hello-git.git
```

After telling our local Git repository about our new `remote` repository called `origin` we will `push` the code there.

```
git push origin master
```

>If this is your first time using Github, your first push will fail. Dont worry, thats to be expected. Thats because you will need to add credentials to your computer so Github knows people with permission are making changes.

>Github has a great guide to do this, please visit [Connecting to GitHub with SSH](https://help.github.com/en/github/authenticating-to-github/connecting-to-github-with-ssh)

After successfully pushing your changes to Github, reload the homepage for `hello-git` and you should now see the latest changes you made and more!

[Next](git-branches.md)
