# Vim Reference

## Modes

`ESC` - Normal mode  

`i` - Insert mode (at cursor)  
`I` - Insert mode (at beginning of line)  
`a` - Insert mode (after cursor)  
`A` - Insert mode (at end of line)  
`o` - Open new line below and enter insert mode  
`O` - Open new line above and enter insert mode  

`v` - Visual mode (character-wise)  
`V` - Visual mode (line-wise)  
`Ctrl+v` - Visual mode (block-wise)  

`:` - Command mode  
`R` - Replace mode  

## Navigation

`:{int}` - Go to line `{int}`  
`{int}G` - Go to line `{int}`  

`zz` - Center cursor on screen  
`zt` - Cursor to top of screen  
`zb` - Cursor to bottom of screen  

`Ctrl+u` - Half page up  
`Ctrl+d` - Half page down  

`Ctrl+b` - Full page up  
`Ctrl+f` - Full page down  

`Ctrl+e` - Scroll one line up  
`Ctrl+y` - Scroll one line down  

`Ctrl+o` - Jump to previous position  
`Ctrl+i` - Jump to next position  

`''` - Jump to last position  

`H` - Top of screen  
`M` - Middle of screen  
`L` - Bottom of screen  

`0` - Beginning of line  
`$` - End of line  

`^` - First non-blank character  
`g_` - Last non-blank character  

## Motions

`h` - Left  
`j` - Down  
`k` - Up  
`l` - Right  

`{int}k` - Move up `{int}` lines  
`{int}j` - Move down `{int}` lines  

`gg` - Top of file  
`G` - Bottom of file  

`(` - Previous sentence  
`)` - Next sentence  

`{` - Previous paragraph  
`}` - Next paragraph  

`%` - Matching bracket/parenthesis  
`*` - Next occurrence of word under cursor  
`#` - Previous occurrence of word under cursor  

`w` - Next word  
`W` - Next WORD (ignoring punctuation)  

`b` - Previous word  
`B` - Previous WORD  

`e` - End of word  
`E` - End of WORD  

`ge` - End of previous word  
`gE` - End of previous WORD  

`f{char}` - Find next `{char}` in line  
`F{char}` - Find previous `{char}` in line  

`t{char}` - Move to before next `{char}`  
`T{char}` - Move to after previous `{char}`  

`;` - Repeat last f/F/t/T  
`,` - Repeat last f/F/t/T (reverse)  

`/{pattern}` - Search for `{pattern}` forward  
`?{pattern}` - Search for `{pattern}` backward  
`n` - Next search result  
`N` - Previous search result  

## Operators

### Operator Usage
`operator + motion`  
`operator + text_object`  

### Delete (`d`)
- `d{motion}` - Delete text specified by `{motion}`
- `dd` - Delete current line
- `D` - Delete from cursor to end of line

### Change (`c`)
- `c{motion}` - Change text specified by `{motion}`, then enter Insert mode
- `cc` - Change current line and enter Insert mode
- `C` - Change from cursor to end of line and enter Insert mode

### Yank/Copy (`y`)
- `y{motion}` - Yank text specified by `{motion}`
- `yy` - Yank current line
- `Y` - Yank from cursor to end of line

### Substitute (`s`)
- `s` - Substitute character and enter Insert mode
- `S` - Substitute entire line and enter Insert mode

### Visual Selection
- `v` - Character-wise visual selection
- `V` - Line-wise visual selection
- `Ctrl+v` - Block-wise visual selection

### Case Modification
- `~` - Toggle case of character under cursor
- `g~{motion}` - Toggle case of text specified by `{motion}`
- `g~~` - Toggle case of current line
- `gu{motion}` - Convert text specified by `{motion}` to lowercase
- `guu` - Convert current line to lowercase
- `gU{motion}` - Convert text specified by `{motion}` to uppercase
- `gUU` - Convert current line to uppercase

### Indentation
- `>{motion}` - Shift text specified by `{motion}` right
- `>>` - Indent current line
- `<{motion}` - Shift text specified by `{motion}` left
- `<<` - Unindent current line
- `={motion}` - Auto-indent text specified by `{motion}`
- `==` - Auto-indent current line

### Filtering and Formatting
- `!{motion}{cmd}` - Filter text specified by `{motion}` through external command `{cmd}`
- `!!{cmd}` - Filter current line through external command `{cmd}`
- `gq{motion}` - Format text specified by `{motion}` according to 'textwidth'
- `gqq` - Format current line

### Examples of Operator + Motion
- `dd` - Delete the current line
- `dw` - Delete from cursor to beginning of next word
- `d$` - Delete from cursor to end of line
- `dG` - Delete from current line to end of file
- `cc` - Change the entire current line
- `cw` - Change from cursor to beginning of next word
- `c0` - Change from cursor to beginning of line
- `yy` - Yank the current line
- `yw` - Yank from cursor to beginning of next word
- `yG` - Yank from current line to end of file
- `>>` - Indent the current line
- `>j` - Indent current line and line below
- `gUU` - Convert current line to uppercase
- `gUw` - Convert from cursor to next word to uppercase

## Text Objects

Use with operators: `operator + i/a + text_object`

**Inner (`i`) vs Around (`a`)**
- `w` - word (letters, digits, underscore)
- `W` - WORD (non-blank characters)
- `s` - sentence (ends with `.`, `!`, `?`)
- `p` - paragraph (separated by empty lines)
- `(` or `b` - parentheses `()`
- `{` or `B` - curly braces `{}`
- `[` - square brackets `[]`
- `<` - angle brackets `<>`
- `t` - tag block (e.g., `<div>...</div>`)
- `"` - double quotes
- `'` - single quotes
- ``` ` ``` - backticks

### Examples of Operator + Text Objects
- `diw` - Delete **inner** word (word only, no spaces)
- `daw` - Delete **around** word (word + surrounding space)
- `ciW` - Change **inner** WORD
- `cas` - Change **around** sentence
- `yip` - Yank **inner** paragraph
- `yap` - Yank **around** paragraph (includes blank lines)
- `di"` - Delete **inner** content of double quotes
- `ya'` - Yank **around** single quotes (includes quotes)
- `ci(` or `cib` - Change **inner** parentheses content
- `da(` or `dab` - Delete **around** parentheses (includes parentheses)
- `ci{` or `ciB` - Change **inner** curly braces content
- `da{` or `daB` - Delete **around** curly braces (includes braces)
- `ci[` - Change **inner** square brackets content
- `da<` - Delete **around** angle brackets (includes brackets)
- `dit` - Delete **inner** tag block content
- `dat` - Delete **around** tag block (includes tags)
- `gUiw` - Uppercase **inner** word
- `>ap` - Indent **around** paragraph
- `=i{` - Auto-indent **inner** curly brace block

## Other Editing Commands

### Basic Operations
`x` - Delete character under cursor  
`X` - Delete character before cursor  

`p` - Paste after cursor/line  
`P` - Paste before cursor/line  

`r{char}` - Replace character under cursor with `{char}`  
`.` - Repeat last change  

### Undo/Redo
`u` - Undo last change  
`Ctrl+r` - Redo last undone change  
`U` - Undo all changes to current line  

### Join Lines
`J` - Join line below to current line (with space)  
`gJ` - Join line below to current line (without space)  

### Number Operations
`Ctrl + a` - Increment number under cursor by 1  
`Ctrl + x` - Decrement number under cursor by 1  

### Marks and Registers
`ma` - Set mark `a`  
`'a` - Jump to mark `a`  
`"ayy` - Yank to register `a`  
`"ap` - Paste from register `a`  
`:reg` - Show all registers  

### Visual Mode Operations
`gv` - Reselect last visual selection  
`o` - Move to other end of visual selection  

## File and Command Operations

`:q` - Close file  
`:q!` - Quit without checking changes  
`:qa` - Close all files  

`:w` - Save  
`:wq` - Save and close file  

`:x` - Save and close file (if changes)  

`:e {filename}` - Edit `{filename}` file  
`:w {filename}` - Save file as `{filename}`  

`ZZ` - Save and quit  
`ZQ` - Quit without checking changes  

`:!command` - Execute shell command  
`:help {topic}` - Go to manual page for `{topic}`  
