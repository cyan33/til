## Modify Multiple Commits Author in Git

I happened to use a wrong github/gitlab account to push my code to github.
Thus, github doesn't recogonize the commits to be my contribution.

Most of the case, if you want to change only the previous single commit author, you could do:

```
git commit --amend --author="thomasyimgit <thomasyim94@gmail.com>"
```

For more info about `git commit --ammend`, you could read [this](git/git-ammend.md)

So the ultimate solution for this is showed below, I found it from [this answer]('http://stackoverflow.com/questions/750172/change-the-author-and-committer-name-and-e-mail-of-multiple-commits-in-git') in stackoverflow.

```bash
git filter-branch -f --env-filter "
    GIT_AUTHOR_NAME='Newname'
    GIT_AUTHOR_EMAIL='new@email'
    GIT_COMMITTER_NAME='Newname'
    GIT_COMMITTER_EMAIL='new@email'
  " HEAD
```
