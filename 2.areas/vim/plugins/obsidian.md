A neovim plugin for writing and navigating Obsidiann vaults, written in Lua. 
### remaps
`<leader>of` - obsidian follow to  follow obsidian links
`<leader>od` - obsidian done to check boxes
### config
```lua
  {
    'epwalsh/obsidian.nvim',
    version = '*', -- recommended, use latest release instead of latest commit
    lazy = true,
    ft = 'markdown',
    -- Replace the above line with this if you only want to load obsidian.nvim for markdown files in your vault:
    -- event = {
    --   -- If you want to use the home shortcut '~' here you need to call 'vim.fn.expand'.
    --   -- E.g. "BufReadPre " .. vim.fn.expand "~" .. "/my-vault/*.md"
    --   -- refer to `:h file-pattern` for more examples
    --   "BufReadPre path/to/my-vault/*.md",
    --   "BufNewFile path/to/my-vault/*.md",
    -- },
    dependencies = {
      -- Required.
      'nvim-lua/plenary.nvim',
    },
    opts = {
      workspaces = {
        {
          name = 'yeti',
          path = '~/yeti',
        },
      },
      completion = {
        -- set to false to disable completion
        nvim_cmp = true,
        -- trigger completion at 2 chars.
        min_chars = 2,
        -- put new notes in the same directory as the current buffer.
        new_notes_location = 'current_dir',
      },
      mappings = {
        -- "obsidian follow"
        ['<leader>of'] = {
          action = function()
            return require('obsidian').util.gf_passthrough()
          end,
          opts = { noremap = false, expr = true, buffer = true },
        },
        -- toggle check-boxes "obsidian done"
        ['<leader>od'] = {
          action = function()
            return require('obsidian').util.toggle_checkbox()
          end,
          opts = { buffer = true },
        },
      },
    },
  },
```
