# Vim

* https://danielmiessler.com/study/vim/
* http://stackoverflow.com/questions/8750275/vim-super-fast-navigation
* http://nvie.com/posts/how-i-boosted-my-vim/
* http://vimregex.com/#substitute
* http://superuser.com/questions/147715/vim-insert-empty-line-above-current-line-not-open-i-e-without-entering-inser
* https://duckduckgo.com/?ia=cheatsheet&iax=1&q=vim+cheat+sheet
* http://stackoverflow.com/questions/7406949/vim-faster-way-to-select-blocks-of-text-in-visual-mode
* http://stackoverflow.com/questions/253380/how-do-i-insert-text-at-beginning-of-a-multi-line-selection-in-vi-vim
* http://vim.wikia.com/wiki/Search_and_replace
* http://vim.wikia.com/wiki/Moving_lines_up_or_down
* http://stackoverflow.com/questions/594448/how-can-i-add-a-string-to-the-end-of-each-line-in-vim

https://medium.com/hacking-and-gonzo/10-vim-tricks-you-should-know-6393842b3537#.6jldhnolk

`:Goyo` to open distraction free writing

http://askubuntu.com/questions/193072/how-to-use-the-new-adobe-source-code-pro-font

## Vim-Fugitive Git

https://github.com/tpope/vim-fugitive

```vim
:Gstatus
:Gedit
:Gcommit
:Gblame
:Ggrep
:Gbrowse
:Gdiff
:Gmove
```


## Buffer

https://github.com/maxbrunsfeld/vim-yankstack

`meta-p` - cycle backward through your history of yanks
`meta-shift-p` - cycle forwards through your history of yanks

See yanks by `:Yanks`


## Multiple cursors

`ctrl+n`

## Comments

`:gcc`
`:gcgc`

## Folds

* `zR` open all folds

## File commands 

* Write file `:w <fileName>`
* Write file and quit `:wq`
* Edit a file `:e <filename>` (tab autocomplete works)
* `wa` for writing all files
* `:e!` revert to last save
* `!rm %` remove file

## Vinegar

* `-` show files in current directory using vinegar plugin 
	* `-` again to go up a level
* `d` create directory
* `D` delete directory or file
* `%` for new file

## NERDTree

* `NERDTreeToggle`
* `?` find options
* `m` move node
* `a` add node
* `d` delete node
* `c` copy node
* `r` refresh listing


## Buffers
* `:bp` buffer previous
* `:ls` list all buffers
* `:b3` third buffer (found via list)
* `:bd` close tab (buffer)  buffer delete
* `:bp` previous buffer
* `:+up` to cycle through previous commands
* `:bufdo bd!` close every buffer
* `ctrl+wo` make current buffer full screen


## Modes 

Vim has several different modes

* `esc` to get to Normal mode
* `i` insert mode
* `v` visual (for selecting sections of text by the keyboard to be operated on)
* `V` visual selecting by lines

### Visual mode sub commands

* `d` to delete

## Editing 

* `r` to replace under cursor (e.g. `r"'` to replace `"` with `'`)
* `J` to join bottom line to current line
* `o` add line below and go into insert mode
* `O` add line above and go into insert mode
* `shift+>` or `shift+<` for indenting visually selected

### Going into Insert mode

* `i` to place the cursor before the normal mode selection
* `a` to place the cursor after the normal mode selection
* `shift-I` place cursor before first character of the line
* `shift-A` place cursor after last character of the line

### Selecting 

* `vi` for selecting inside (quotes etc) so `vi"` to select inside `""`
* `va` for selecting all include delimeter so `va{` will select the braces and everything inside.

### Sorroundings

* `ci` change inside and puts you in insert mode (i.e. `ci"`)
* `ds` delete sorrounding
* `cs` change sorrounding
* `dst` delete sorrounding tag
* `cst` change sorrounding tag 
* `cit` change inside tag
* `S` add sorrounding to visual selection
* visual select + `:norm vss'` to sorround lines with `'`


### Deleting

* [deleting backwards tricks](http://stackoverflow.com/questions/1373841/vim-deleting-backword-tricks)

`di` stands for delete inside

* `di+(` for deleting everything in between paranthesis
* `di+"` for deleting everything in between quotes
* `di+'` for deleting everything in between single-quotes
* `x` delete character under cursor
* `3x` delete 3 characters forward.  Capital for reverse
* `^D` delete all characters on line starting from first non-whitespace
* `0D` delete all characters on line including whitespace		


## Movement

* left `h`
* right `l`
* up `k`
* down `j`
* top `gg`
* `ctrl+^` go back to previous edit point or location
* `ctrl+d` page down
* `$` move to end of line
* `^` move to first not blank character on line
* `0` to move to first column of line
* `f<char>` move forward to first instance of character
* `<number>f<char>` move forward to Nth character
* `w` forward word
* `b` back word
* `alt+j` move line up
* `alt+k` move line down
* `42G` or `42gg` or `:42` to go to line number
	* http://vim.wikia.com/wiki/Go_to_line

## Misc

* command mode `:`
* Current working directory `:pwd`
* `:source ~/.vimrc` to source a .vimrc
* Source current file `:so %`
* `.` references last command
* `,ev` edit vim config
* `:!<command>` to run commandline command
* `:reg` to registers (clipboard etc)


## Viewing

* `zz` current line middle of screen
* `:e .` show the files & current in the current directory
	* j,h,k,l for traversing
	* `/<search>` for search

### Splits

* `:q` to close out split
	* `ctrl+w` then `q` to close out split
* `:sp` for split (default horizontal)
* switching default is `ctrl+w+<movementkey>`
* `:vsp` for vertical split
* `ctrl+w+|` split takes up full
* `ctrl+h+|` split takes up full
* `ctrl+w+=` to normalize

* `ctrl+h`  left split
* `ctrl+l`  right split
* `sbuffer 3" split for buffer 3



## Search 
* search `/term`
* next `n`
* previous `N`
* turn off search `,space` actually leader but it works
* ':copen"  show all matches

### folder wide

* `:Ag '<search'` to search for occurence 

### Search and replace
* `:Gsearch` 
	* replace in results file
		* select all lines
		* `:s/<query>/<replace>` to replace the first match on each line
		* `:s/<query>/<replace>/g` to replace all matches on all lines
		* `:Greplace` to run the replace

#### Autocomplete for substitution

http://stackoverflow.com/questions/19730567/vim-auto-completion-on-substitutions-and-searches-in-the-command-line

* visually select for the substitution
* enter normal mode `esc`
* `ctrl+f` to enter commandline window
* start typing substitution and hit `ctrl+p` when needed to autocomplete.  e.g.: `s/star..`

### Ctags

* `:!ctags -R`
* `:tag` to search for a tag (method)
* `:tn` to go to next tag
* `:tp` to go to previous tag
* `:ts` to select from all of the tags available
* `ctrl+]` to go to method from usage. e.g. `$this->myMethod()` goes to `myMethod()` definition
* `,ct` for rebuilding tag cache

## copy pasta
 **Visual Mode**

* `y` for yank (while in visual mode)
* `yy` for yank line
* `p` for paste after cursor
* `P` for paste before cursor
* `d` for cut
* `ddp` for switching lines of text


## CtrlP

* `ctrl+d` while in pane to search only for file names
* `ctrl+r` show symbols or tags while in the file
* `ctrl+e` show recently used files
* `F5` to refresh file listings

## Mappings

* `nmap` = normal mode mapping
* `imap` = insert mode mapping
* 

## PHP

* `,su` sort namespaces by length in selection
* `,n` import namespace
* `,nf` use fully qualified namespace
* `ctrl+n` autocomplete choose item then keep typing
* `<Leader>pf` php cs fixer on directory

## vim special character mapping

you can only map one character with another followed by n sets

<BS>           Backspace
<Tab>          Tab
<CR>           Enter
<Enter>        Enter
<Return>       Enter
<Esc>          Escape
<Space>        Space
<Up>           Up arrow
<Down>         Down arrow
<Left>         Left arrow
<Right>        Right arrow
<F1> - <F12>   Function keys 1 to 12
#1, #2..#9,#0  Function keys F1 to F9, F10
<Insert>       Insert
<Del>          Delete
<Home>         Home
<End>          End
<PageUp>       Page-Up
<PageDown>     Page-Down
<bar>          the '|' character, which otherwise needs to be escaped '\|'