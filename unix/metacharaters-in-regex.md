# Metacharacters in Regular Expression

## BRE (Basic Regular Expression)

`.` - any character one time
`*` - any character for any time (zero, one or more)

### Anchors

`^` - start with
`$` - end with

try `grep '^..j.r$' /usr/share/dict/words` to find `Major, major, Gujar`

### Bracket Expressions And Character Classes

`[]` - match one of the charaters that are presented in the set

Note that the `^` (caret) and `-` (dash) have different meanings when in brackets

`^` (only when it's the first character) - negation
`-` (loses its effect when it's the first character) - range

## ERE (Extended Regular Expression)

`|` - Alternation
`( )` - Used for separation
`?` - Match An Element Zero Or One Time
`{ }` - Match an element a specific number of times
