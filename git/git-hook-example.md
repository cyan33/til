# Git Hook Example

Git hooks are scripts that run specificly when a git task is done during the lifecycle, like `pre-commit`, `post-commit`, etc.

Let's create a post-commit script that will open a webpage after a git commit.

First, create a folder and track it with git:

```sh
mkdir git-hook-example && cd ./git-hook-example 
```

In the `./git/hooks` directory, you can see a lot of sample hook scripts. By default, the suffix `.sample` prevent them from executing.

In the `hooks` folder, create a `post-commit` on our own:

```sh
#!/bin/sh

# `open` for mac/linux, `start` for windows
open "http://google.com" 
```

And make it executable by:

```sh
chmod +x .git/hooks/post-commit
```

Try modify the tracked files and do:

```sh
git add .
git commit -m "some modification"
```

After you commit, the script will be executed automatically and redirect you to `http://google.com`
