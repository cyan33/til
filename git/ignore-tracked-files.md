# Gitignore Tracked Files

.gitignore will prevent untracked files from being added (without an add -f) to the set of files tracked by git, however git will continue to track any files that are already being tracked.

To stop tracking a file you need to remove it from the index. This can be achieved with this command.

```
git rm --cached <file>
```

The removal of the file from the head revision will happen on the next commit.
