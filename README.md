## Exiting

`:q` - Close file  
`:qa` - Close all files  

`:w` - Save  
`:wq` / `:x` - Save and close file  

`ZZ` - Save and quit  
`:q!` / `ZQ` - Quit without checking changes  
  
## Modes
  
`ESC` - enter normal mode  

`i` - enter insert mode (at cursor)  
`I` - enter insert mode (at the beginning of the line)  

`a` - enter insert mode (after cursor)  
`A` - enter insert mode (at the end of the line)  

`o` - open a new line below and enter insert mode  
`O` - open a new line above and enter insert mode  

`v` - enter visual mode  
`:` - enter command mode  
`R` - enter replace mode  

### Navigation

`:12` - move to line 12  

`zz` - center the screen on the cursor  
`zt` - position cursor at the top of the screen  
`zb` - position cursor at the bottom of the screen  

`Ctrl + u` - move half a page up  
`Ctrl + d` - move half a page down  

`Ctrl + e` - move page one line up  
`Ctrl + y` - move page one line down  

`Ctrl + i` - jump forward to next position  
`Ctrl + o` - jump back to previous position  

`H` - move to the top of the screen (High)  
`M` - move to the middle of the screen (Middle)  
`L` - move to the bottom of the screen (Low)  

`0` - move to the beginning of the line  
`$` - move to the end of the line  

### Motions

`h` - move left  
`j` - move down  
`k` - move up  
`l` - move right  

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

`%` - move to the matching closing character  
`#` - move to the previous occurrence of the word under the cursor  
`*` - move to the next occurrence of the word under the cursor  

`w` - move to the beginning of the next word  
`W` - move to the beginning of the next word (ignoring punctuation)  

`b` - move to the beginning of the previous word  
`B` - move to the beginning of the previous word (ignoring punctuation)  

`e` - move to the end of the next word  
`E` - move to the end of the next word (ignoring punctuation)  

`ge` - move to the end of the previous word  
`gE` - move to the end of the previous word (ignoring punctuation)  

`fx` - find the next occurrence of the character `x` in the line  
`Fx` - find the previous occurrence of the character `x` in the line  

`tx` - find the character `x` in the line and move the cursor to the character before it  
`Tx` - find the character `x` in the line and move the cursor to the character after it  

`;` - repeat the last `f`, `F`, `t`, or `T` command  
`,` - repeat the last `f`, `F`, `t`, or `T` command in the opposite direction  

`/pattern` - search forward for pattern  
`?pattern` - search backward for pattern  
`n` - repeat search in same direction  
`N` - repeat search in opposite direction  

## Editing

### Operator Usage

`operator + motion`  
`operator + text_object`  

### 1. Operators

*   `d` - Delete:
    *   `d{motion}` - Delete text specified by motion.
    *   `dd` - Delete current line.
    *   `D` - Delete from cursor to end of line (equivalent to `d$`).

*   `c` - Change:
    *   `c{motion}` - Change text specified by motion, then enter Insert mode.
    *   `cc` - Change current line and enter Insert mode.
    *   `C` - Change from cursor to end of line and enter Insert mode (equivalent to `c$`).

*   `y` - Yank (copy):
    *   `y{motion}` - Yank text specified by motion.
    *   `yy` - Yank current line.
    *   `Y` - Yank from cursor to end of line.

*   `s` - Substitute:
    *   `s` - Substitute character(s) under cursor and enter Insert mode (equivalent to `cl`).
    *   `S` - Substitute entire current line(s) and enter Insert mode (equivalent to `cc`).

*   Visual Selection (these commands start a selection mode; an operator can then be applied to the selection):
    *   `v` - Start character-wise visual selection.
    *   `V` - Start line-wise visual selection.
    *   `Ctrl+v` - Start block-wise visual selection.

*   Case Modification:
    *   `~` - Swap case of character under cursor and move right.
    *   `g~{motion}` - Swap case of text specified by motion.
    *   `g~~` - Swap case of current line.
    *   `gu{motion}` - Convert text specified by motion to lowercase.
    *   `guu` - Convert current line to lowercase.
    *   `gU{motion}` - Convert text specified by motion to uppercase.
    *   `gUU` - Convert current line to uppercase.

*   Indentation:
    *   `>{motion}` - Shift text right by 'shiftwidth'.
    *   `>>` - Indent current line.
    *   `<{motion}` - Shift text left by 'shiftwidth'.
    *   `<<` - Unindent current line.
    *   `={motion}` - Auto-indent text (uses 'equalprg' or internal formatting).
    *   `==` - Auto-indent current line.

*   Filtering and Formatting:
    *   `!{motion}{cmd}` - Filter text specified by motion through an external command `{cmd}`.
    *   `!!{cmd}` - Filter current line through external command `{cmd}`.
    *   `gq{motion}` - Format text specified by motion according to 'textwidth'.
    *   `gqq` - Format current line.
    *   `gw{motion}` - Format text specified by motion according to 'textwidth', keeping cursor position.
    *   `gww` - Format current line, keeping cursor position.

*   ROT13 Encode:
    *   `g?{motion}` - ROT13 encode text specified by motion.
    *   `g??` - ROT13 encode current line.

*   Folding:
    *   `zf{motion}` - Create a fold for the text specified by motion (e.g., `zfap` for a paragraph; often used with visual selection).
    *   `zF` - Create a fold for the current line.


### 2. Examples of Operator + Motion

*   `dd` - Delete the current line (operator `d` repeated on the current line)
*   `dw` - Delete from the cursor to the beginning of the next word
*   `d$` - Delete from the cursor to the end of the current line
*   `dG` - Delete from the current line to the end of the file
*   `cc` - Change the entire current line
*   `cw` - Change from the cursor to the beginning of the next word
*   `c0` - Change from the cursor to the beginning of the line
*   `yy` - Yank (copy) the current line
*   `yw` - Yank from the cursor to the beginning of the next word
*   `yG` - Yank from the current line to the end of the file
*   `>>` - Indent the current line
*   `>j` - Indent the current line and the line below
*   `gUU` or `gUgU` - Convert the current line to uppercase
*   `gUw` - Convert from the cursor to the beginning of the next word to uppercase
*   `!!sort` - Sort the current line (filters the current line through the `sort` command)
*   `!Guniq` - Make all lines from the current line to the end of the file unique

### 3. Text Objects

*   `w` - word (sequence of letters, digits, and underscore)
*   `W` - WORD (sequence of non-blank characters, separated by whitespace)
*   `s` - sentence (ends with `.`, `!`, `?` followed by end-of-line, space or tab)
*   `p` - paragraph (separated by empty lines)
*   `b` or `()` - block of parentheses `()`
*   `B` or `{}` - Block of curly braces `{}`
*   `[]` - block of square brackets `[]`
*   `<>` - block of angle brackets `<>`
*   `t` - tag block (e.g., `<div>...</div>`)
*   `"` - double quotes `"`
*   `'` - single quotes `'`
*   ``` ` ``` - backticks ``` ` ```

### 4. Examples of Operator + i/a + Text Objects

*   `diw` - Delete **i**nner **w**ord (deletes the word under the cursor, but not surrounding spaces)
*   `daw` - Delete **a** **w**ord (deletes the word under the cursor and one surrounding space)
*   `ciW` - Change **i**nner **W**ORD
*   `cas` - Change **a** **s**entence
*   `yip` - Yank **i**nner **p**aragraph
*   `yap` - Yank **a** **p**aragraph (includes the blank line after/before)
*   `di"` - Delete **i**nner content of **"**double quotes**"**
*   `ya'` - Yank **a**round **'**single quotes**'** (includes the quotes)
*   `ci(` or `cib` - Change **i**nner content of **(**parentheses block**)**
*   `da(` or `dab` - Delete **a**round **(**parentheses block**)** (includes the parentheses)
*   `ci{` or `ciB` - Change **i**nner content of **{**curly braces**}**
*   `da{` or `daB` - Delete **a**round **{**curly braces**}** (includes the braces)
*   `ci[` - Change **i**nner content of **[**square brackets**]**
*   `da<` - Delete **a**round **<**angle brackets**>** (includes the brackets)
*   `dit` - Delete **i**nner **t**ag block (e.g., content of `<div>...</div>`)
*   `dat` - Delete **a** **t**ag block (e.g., `<div>...</div>` including the tags)
*   `gUiw` - Uppercase **i**nner **w**ord
*   `>ap` - Indent **a** **p**aragraph
*   `=i{` - Auto-indent **i**nner **{**curly brace block**}**

### 5. Other Editing Commands

*   `x` - Delete character under cursor (like `dl`)
*   `X` - Delete character before cursor (like `dh`)
*   `p` - Paste yanked/deleted text **p**after the cursor (if character-wise) or after the current line (if line-wise)
*   `P` - Paste yanked/deleted text **P**before the cursor (if character-wise) or before the current line (if line-wise)
*   `r{char}` - Replace the character under the cursor with `{char}` (stays in Normal mode)
*   `.` - Repeat the last change
*   `u` - Undo last change
*   `Ctrl + r` - Redo last undone change
*   `J` - Join the line below to the current line (adds a space)
*   `gJ` - Join the line below to the current line (without adding a space)

