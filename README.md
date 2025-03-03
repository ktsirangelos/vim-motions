# VIM Motions - training

## Modes

`ESC` - normal mode
`i` - insert mode
`v` - visual mode
`:` - command mode

## Basics

### Cursor Movement

`h` - move left
`j` - move down
`k` - move up
`l` - move right

`:12` - move to line 12
`12k` - move up 12 lines
`12j` - move down 12 lines

`gg` - move to the top of the file
`G` - move to the bottom of the file

`0` - move to the beginning of the line
`$` - move to the end of the line

`(` - move to the beginning of the previous sentence
`)` - move to the beginning of the next sentence

`{` - move to the beginning of the previous paragraph
`}` - move to the beginning of the next paragraph

`%` - move to the matching parenthesis
`#` - move to the previous occurrence of the word under the cursor
`*` - move to the next occurrence of the word under the cursor

`w` - move to the beginning of the next word
`W` - move to the beginning of the next word (ignoring punctuation)

`b` - move to the beginning of the previous word
`B` - move to the beginning of the previous word (ignoring punctuation)

`e` - move to the end of the next word
`E` - move to the end of the next word (ignoring punctuation)

`ge` - move to the end of the previous word
`gE` -move to the end of the previous word (ignoring punctuation)

`fx` - find the next occurrence of the character `x` in the line
`Fx` - find the previous occurrence of the character `x` in the line

`tx` - find the character `x` in the line and move the cursor to the character before it
`Tx` - find the character `x` in the line and move the cursor to the character after it

`;` - repeat the last `f`, `F`, `t`, or `T` command
`,` - repeat the last `f`, `F`, `t`, or `T` command in the opposite direction

`zz` - center the screen on the cursor

`Ctrl + d` - move half a page down
`Ctrl + u` - move half a page up

`Ctrl + o` - jump back to previous position
`Ctrl + i` - jump forward to next position

`/pattern` - search forward for pattern
`?pattern` - search backward for pattern
`n` - repeat search in same direction
`N` - repeat search in opposite direction

`ma` - mark position with label 'a' (buffer specific)
`'a` - jump to line of mark 'a'
`` `a `` - jump to line and column of mark 'a'
`mA` - mark position with label 'A' (global)
`'A` - jump to line of mark 'A'
`` `A `` - jump to line and column of mark 'A'
