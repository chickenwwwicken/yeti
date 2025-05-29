##### Telescope remaps
`<leader>sh` - Search Help
`<leader>sk` - Search Keymaps
`<leader>sf` - Search Files
`<leader>ss` - Search Select telescope
`<leader>sw` - Search current Word
`<leader>sg` - Search by Grep
`<leader>sd` - Search Diagnostics
`<leader>sr` - Search Resume
`<leader>s.` - Search recent files - "." for repeat
`<leader><leader>` - Find existing Buffers

##### Terminal mode
`<Esc><Esc>` - Exit terminal mode

##### Window commands "n"
see :help wincmd for a list of all window commands
`<C-h>` - Move focus to the left window
`<C-l>` - Move focus to the right window
`<C-j>` - Move focus to the lower window
`<C-k>` - Move focus to the upper window

##### LSP remaps "n" 
-- Rename the variable under your cursor
`grn` - [R]e[N]ame

-- Execute a code action, usually your cursor needs to be on top of an error or a suggestion from your LSP to activate
`gra` - Goto code Action - "x" "n"

-- Find references for the word under cursor
`grr` - Goto References

-- Jump to implementation of the word under cursor
-- Useful when you language has ways of declaring types without an actual implementation
`gri` - Goto Implementation

-- Jump to definition
-- this is where a variable is first declared, or where funnc is defined, 
-- to jump back press `<C-t>`
`grd` - Goto Definition

-- Go to Declaration
-- in C this would take you to the header.
`grD` - goto Declaration

-- fuzzy find all symbols in your current document
-- symbols are things like variables, functions, types, etc.
`gO` - open document symbols

-- fuzzy find all symbols in current workspace
-- similar to prev except searches in entire project
`gW` - Open workspace symbols

-- jump to the type of word under your cursor. 
-- useful when you're not sure what type a variable is and you want to see
-- the definition of its *type*, not where it was *defined*. 
`grt` - Goto Type definition

