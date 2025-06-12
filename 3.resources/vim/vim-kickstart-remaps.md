---
tags:
  - rsrc
  - vim
  - remaps
---
### Terminal mode
`<Esc><Esc>` - Exit terminal mode

### Autocomplete
`<C-n>` - select next field
`<C-p>` - select prev field
`<C-y>` - accept completion
`<C-Space>` - manually trigger a completion from nvim-cmp
`<C-l>` - didnt get it

### Window commands "n"
see :help wincmd for a list of all window commands
`<C-h>` - Move focus to the left window
`<C-l>` - Move focus to the right window
`<C-j>` - Move focus to the lower window
`<C-k>` - Move focus to the upper window

### Diagnostic remaps
`"n" - "<leader>q"` - Open diagnostic Quickfix list
`"n" - "[d"` - To to previous DDDiagnostic message
`"n" - "]d"` - Go to next DDDiagnostic message

# Chicken Remaps full

```lua
-- NOTE:
-- NOTE: CHICKEN REMAPS
-- NOTE:
vim.keymap.set('i', 'jj', '<Esc>', { desc = 'Exit insert mode' })
vim.keymap.set('n', '<leader>pv', vim.cmd.Ex, { desc = 'Exit to netrw' })

vim.keymap.set('v', 'J', ":m '>+1<CR>gv=gv", { desc = 'move highlighted up' })
vim.keymap.set('v', 'K', ":m '<-2<CR>gv=gv", { desc = 'move highlighted down' })

vim.keymap.set('n', 'J', 'mzJ`z', { desc = 'cursor stays at start-o-line' })

vim.keymap.set('n', '<C-d>', '<C-d>zz', { desc = 'cursor stays at middle in half page jumpin' })
vim.keymap.set('n', '<C-u>', '<C-u>zz', { desc = 'cursor stays at middle in half page jumpin' })

vim.keymap.set('n', 'n', 'nzzzv', { desc = 'cursor stays at middle in search' })
vim.keymap.set('n', 'N', 'Nzzzv', { desc = 'cursor stays at middle in search' })

vim.keymap.set('x', '<leader>p', '"_dP', { desc = 'paste register stays same' })

vim.keymap.set('n', '<leader>y', '"+y', { desc = 'yank to main clipboard' })
vim.keymap.set('v', '<leader>y', '"+y', { desc = 'yank to main clipboard' })
vim.keymap.set('n', '<leader>Y', '"+Y', { desc = 'yank to main clipboard' })

vim.keymap.set('n', '<leader>d', '"+d', { desc = 'deletin to void register' })
vim.keymap.set('v', '<leader>d', '"+d', { desc = 'deletin to void register' })

vim.keymap.set('n', 'Q', '<nop>', { desc = 'no operation, instead of Quittin' })

vim.keymap.set('n', '<C-k>', '<cmd>cnext<CR>zz', { desc = 'navigate between quickfix items' })
vim.keymap.set('n', '<C-j>', '<cmd>cprev<CR>zz', { desc = 'navigate between quickfix items' })

vim.keymap.set('n', '<leader>k', '<cmd>lnext<CR>zz', { desc = 'navigate between location list items' })
vim.keymap.set('n', '<leader>j', '<cmd>lprev<CR>zz', { desc = 'navigate between location list items' })

vim.keymap.set('n', '<leader>s', [[:%s/\<<C-r><C-w>\>/<C-r><C-w>/gI<Left><Left><Left>]], { desc = 'replace word under cursor in all file' })

-- adds executable permissions to the file/buffer u at
vim.keymap.set('n', '<leader>x', '<cmd>!chmod +x %<CR>', { silent = true })

-- wrappers by chikimua
vim.keymap.set('v', '<leader>mdh', [[c[<c-r>"]()<esc>]], { desc = 'wrap around md hyper []()' })
vim.keymap.set('v', '<leader>mdb', 'c[[<c-r>"]]<esc>', { desc = 'wrap around md link' })
vim.keymap.set('v', '<leader>mq', [[c"<c-r>""<esc>]], { desc = 'wrap around double quotes' })
vim.keymap.set('v', '<leader>mp', [[c(<c-r>")<esc>]], { desc = 'wrap around parenthesis' })
vim.keymap.set('v', '<leader>mb', [[c[<c-r>"]<esc>]], { desc = 'wrap around brackets' })
vim.keymap.set('v', '<leader>ms', [[c'<c-r>"'<esc>]], { desc = 'wrap around single quotes' })
vim.keymap.set('v', '<leader>mcb', [[c{<c-r>"}<esc>]], { desc = 'wrap around curly brackets' })
vim.keymap.set('v', '<leader>mc', [[c<<c-r>"><esc>]], { desc = 'wrap around carrots' })
```
