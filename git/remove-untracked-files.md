# Remove Untracked Files in Git

Things that I know earlier:

Use `git reset HEAD^` to reset `commited` files.

Use `git checkout .` to reset `added` files.

For untracked files, use `git clean`:

Use `-n` to see which files are to be removed/cleaned:

```sh
$ git clean -n
```

and then move on the the clean:

```sh
git clean -f
```

Also,

* To remove directories, run `git clean -fd`
* To remove ignored files, run `git clean -fX`
* To remove ignored and non-ignored files, run `git clean -fx`
