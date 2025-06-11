# custom-wrapping-remaps
```
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
