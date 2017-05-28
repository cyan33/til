# How to Copy, Move, Rename, Delete Files in UNIX

## Copy:

```
cp [source] [destination]

e.g: cp -R ./public/* ./documents/public
```

`-R` must be used when you want to copy a directory to another directory

## Move(Rename):

```
mv [source] [destination]

e.g: mv ./public ./documents/public
```

Note that the `move` could also do `rename` in a way that:

```
mv ./public ./newPublic
```
This serves that the `public` folder is renamed to `newPublic`

## Delete

```
rm [file]
rmdir [directory]
```

**Note:** to get the correct access when manipulating files, you may need to add `sudo`, which stands for *set user and do*. It sets the user to the one that you specify and performs the command that follows the username.