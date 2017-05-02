## Vim

Learning Vim could be rewarding. And once you get used to it, you can enhance your daily efficiency to a great extent with the help of it.

Learning vim seems to be all about memorizing the command line shortcuts and get used to them. IMHO, the best way to learn vim is to split these commands in several parts so that you could follow them step by step.

Join me if you also want to delve into the Vim world!

## Basic-Starter 

In vim, there are two modes, which are `command mode` and `insert mode`

1. To switch mode:

```
ESC -> command mode
i -> insert mode 
```

P.S. `i` is short for `insert`, it will put the cursor before the current position. Use `a` for `append`, which will put the cursor after the current positon.

2. To save or exit file, first enter the `command mode`:

```
:wq -> save and quit
:q -> quit
:q! -> discard changes and quit
```

3. To navigate your cursor, it's recommended not to use the arrow key, but use the `hjkl` in the command mode:

```
h: left
j: down
k: up
l: right
``` 

4. To navigate through words, in the command mode:

```
w: put the cursor at the beginning of the **next** word
b: put the cursor at the beginning of the **previous** word
```

5. To delete characters, enter the command line and use `x` to delete the char where the cursor is located at.

There you go, first get used to these commands! Good luck!