# Remember

## Browser

gx - to search for word

## CamelCase

Capital letter to navigate CamelCaseWords.
'iw' as text-object

`diw` deletes case.

CamelC*aseWords

## Command-t

|Mapping       |Command          |
|--------------|-----------------|
|<Leader>c     |Navigate commands|
|<Leader>?     |Navigate History |
|<Leader>j     |Jump stack       |
|<Leader>b     |Buffers          |
|<Leader>l     |Find Line        |
|<LocalLeader>t|Tag stack        |
|<unique><F1>  |Help             |

The following mappings are active when the prompt has focus:

|Mapping|Command                                       |
|-------|----------------------------------------------|
|<BS>   |delete the character to the left of the cursor|
|<Del>  |delete the character at the cursor            |
|<Left> |move the cursor one character to the left     |
|<C-h>  |move the cursor one character to the left     |
|<Right>|move the cursor one character to the right    |
|<C-l>  |move the cursor one character to the right    |
|<C-a>  |move the cursor to the start (left)           |
|<C-e>  |move the cursor to the end (right)            |
|<C-u>  |clear the contents of the prompt              |
|<Tab>  |change focus to the file listing              |


The following mappings are active when either the prompt or the file listing
has focus:

|Mapping|Command                                              |
|-------|-----------------------------------------------------|
|<CR>   |open the selected file                               |
|<C-CR> |open the selected file in a new split window         |
|<C-s>  |open the selected file in a new split window         |
|<C-v>  |open the selected file in a new vertical split window|
|<C-t>  |open the selected file in a new tab                  |
|<C-j>  |select next file in the file listing                 |
|<C-n>  |select next file in the file listing                 |
|<Down> |select next file in the file listing                 |
|<C-k>  |select previous file in the file listing             |
|<C-p>  |select previous file in the file listing             |
|<Up>   |select previous file in the file listing             |
|<C-f>  |flush the cache (see |:CommandTFlush| for details)   |
|<C-q>  |place the current matches in the quickfix window     |
|<C-c>  |cancel (dismisses file listing)                      |

## Dash
|Mapping|Command            |
|-------|-------------------|
|,da    |search word in dash|
|Dash!  |open Dash          |

## Git Diff

|Mapping|Command |
|-------|--------|
|zd     |Git Diff|

## EasyMotion

Atempts to act on the normal movement mindset

|Mapping|Command   |
|-------|----------|
|,j     |Move down |
|,k     |Move up   |
|,L     |Linewise  |
|,h     |Move Right|
|,l     |Move Right|

## Git Workflow

|Mapping|Command                        |
|-------|-------------------------------|
|ga     |:Git add %:p<CR><CR>           |
|gs     |:Gstatus<CR>                   |
|gc     |:Gcommit -v -q<CR>             |
|gt     |:Gcommit -v -q %:p<CR>         |
|gd     |:Gdiff<CR>                     |
|ge     |:Gedit<CR>                     |
|gr     |:Gread<CR>                     |
|gw     |:Gwrite<CR><CR>                |
|gl     |:silent! Glog<CR>:bot copen<CR>|
|gg     |:GitGutterToggle<CR>           |
|gp     |:Ggrep                         |
|gm     |:Gmove                         |
|gb     |:Git branch                    |
|go     |:Git checkout                  |
|gps    |:Dispatch! git push<CR>        |
|gpl    |:Dispatch! git pull<CR>        |
|g?     |:map <localleader>g<cr>        |


Normal mode silent mappings

|Mapping|Command          |
|-------|-----------------|
|gsl    |:Glog<CR>        |
|gsd    |:Gdiff<CR>       |
|gsb    |:Gblame<CR>      |
|gsw    |:Gwrite<CR>      |
|gsC    |:Gcommit<CR>     |
|gst    |:Gstatus<CR>     |
|gscd   |:Gcd<Bar>pwd<CR> |
|gsld   |:Glcd<Bar>pwd<CR>|

## FZF

Mapping, Command
ctrl-t, tab split
ctrl-x, split
ctrl-v, vsplit

## Gist

|Mapping             |Command             |
|--------------------|--------------------|
|<leader>g           |List Gist           |
|:Gist               |Create gist         |
|:Gist -p            |Private gist        |
|:Gist -a            |Anonym gist         |
|:Gist -s description|With description    |
|:Gist -b            |Open Gist in browser|

## Finder

|Mapping|Command            |
|-------|-------------------|
|gof    |Open file in finder|

## Navigating Functions

|Mapping   |Command               |
|----------|----------------------|
|,f        |find definition       |
|,F        |find in vertical      |
|<leader>jd|Definition/Declaration|

## Splits

Better version of splits. Able to take multiple arguments

|Mapping|Command       |
|-------|--------------|
|:E     |Edit          |
|:Sp    |Split         |
|:Vs    |Vertical Split|

## Files

:rename[!] {newname}
:NF To make new file from selection

## Grep

"grep the current word using K (mnemonic Kurrent)
nnoremap <silent> K :Ag <cword><CR>

"grep visual selection
vnoremap K :<C-U>execute "Ag " . GetVisual()<CR>

"grep current word up to the next exclamation point using ,K
nnoremap ,K viwf!:<C-U>execute "Ag " . GetVisual()<CR>

"grep for 'def foo'
nnoremap <silent> ,gd :Ag 'def <cword>'<CR>

"Grep for usages of the current file
nnoremap ,gcf :exec "Ag " . expand("%:t:r")<CR>


## Scrolling

|Mapping|Command    |
|-------|-----------|
|<C-Y>  |Scroll up  |
|<C-E>  |Scroll Down|

## Surround

    #Todo: Add more

|Command|Surround with    |
|-------|-----------------|
|,"     |"quotes"         |
|,'     |'single quotes'  |
|,      |`backticks`      |
|,)     |(parens)         |
|,]     |[square-brackets]|
|,}     |{square-brackets}|

**Insert mode**

Ctrl+g og s/S 

** Visual Mode **

Select it then - S.

### Mappings
Works in visual mode

|Mapping|Surrounds      |
|-------|---------------|
|S#     |# Echo Esc_html|
|S#     |- PHP tag      |
|S#     |= Echo php     |


## Tmux Runner

|Mapping      |   Command                    |
|--------------------------------------------|
|<leader>rr   |   VtrResizeRunner<cr>        |
|<leader>ror  |   VtrReorientRunner<cr>      |
|<leader>sc   |   VtrSendCommandToRunner<cr> |
|<leader>sl   |   VtrSendLinesToRunner<cr>   |
|<leader>or   |   VtrOpenRunner<cr>          |
|<leader>kr   |   VtrKillRunner<cr>          |
|<leader>fr   |   VtrFocusRunner<cr>         |
|<leader>dr   |   VtrDetachRunner<cr>        |
|<leader>ar   |   VtrReattachRunner<cr>      |
|<leader>cr   |   VtrClearRunner<cr>         |
|<leader>fc   |   VtrFlushCommand<cr>        |

Custom

|Mapping|Command      |
|-------|-------------|
|,gu    |gulp         |
|,npm   |npm run start|
|,sp    |Spotify      |

## Undo

,u to toggle :UndotreeToggle

|Mapping|Command      |
|-------|-------------|
|j      |Previous/Down|
|k      |Next/Up      |
|r      |Redo         |

## Visual Mode

Use the arrow keys to move a visual selection

D to duplicate the selection.

## Equation align

nmap <silent> =     :call EQAS_Align('nmap')<CR>
nmap <silent> ==    :call EQAS_Align('nmap', {'paragraph':1} )<CR>
nmap <silent> +     :call EQAS_Align('nmap', {'cursor':1} )<CR>
nmap <silent> ++    :call EQAS_Align('nmap', {'cursor':1, 'paragraph':1} )<CR>
vmap <silent> =     :call EQAS_Align('vmap')<CR>
vmap <silent> +     :call EQAS_Align('vmap', {'cursor':1} )<CR>
