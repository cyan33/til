# What is Git Cherrypick?

## What and Why

In short, `cherrypick` is used to apply a specific commit changes to your current branch.

Compared to `merge`, which takes in all the changes from a branch, `cherrypick` only takes in a single commit. So the typical use case could be whenever you want to leverage a single commit of another branch but not all the changes of that.

## How

The usage is extremely simple.

First, checkout to the branch where you want to leverage the commit of another branch:

```
git checkout mybranch
```
and then apply the commit change, using the hash:

```
git cherrypick <commit-hash>
```

[Stackoverflow Source](http://stackoverflow.com/questions/9339429/what-does-cherry-picking-a-commit-with-git-mean)