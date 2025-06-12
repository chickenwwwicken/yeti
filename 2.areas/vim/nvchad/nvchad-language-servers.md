#### Language servers
`lua-language-server` - nvchad uses this by default
`stylua` - nvchad uses this by default
`pyright` - python ls developed by microsoft
`gopls` - go ls developed by go
`ts_ls` - typescript ls
`ruby_lsp` - ruby ls

type the `:Mason` command in nvim to open list of available language servers
inside `lspconfig.lua` add `pyright` and `gopls` in `local servers` list

should end up like this: 
``` lua
-- load defaults i.e lua_lsp
require("nvchad.configs.lspconfig").defaults()

local lspconfig = require "lspconfig"

-- EXAMPLE
local servers = { "html", "cssls", "pyright", "gopls", "ts_ls", "ruby_lsp" }
local nvlsp = require "nvchad.configs.lspconfig"

-- lsps with default config
for _, lsp in ipairs(servers) do
  lspconfig[lsp].setup {
    on_attach = nvlsp.on_attach, 
    on_init = nvlsp.on_init, 
    capabilities = nvlsp.capabilities,
  }
end

-- configuring single server, example: typescript
-- lspconfig.ts_ls.setup {
--   on_attach = nvlsp.on_attach, 
--   on_init = nvlsp.on_init, 
--   capabilities = nvlsp.capabilities,
-- }
```
After adding the lsps into the `lspconfig.lua` file, close nvim and reopen it.
Run `:MasonInstallAll` - reads `lspconfig.lua` and installs lsps (reminder that lua lsps are gonna be downloaded by nvchad by default, so no need to add them.)

I got this error while trying to download lsps:
`spawn: npm failed with exit code - and signal -. npm is not executable`

So we need to download `npm` which is `Node.js`
[[2. areas/vim/nvchad/node-js-install]]

after installing node.js, we go back to trying to run `:MasonInstallAll`
we already had `stylua` `lua-language-server` and `gopls`
now we have `pyright` `typescript-language-server` `css-lsp` `html-lsp`
we missing `ruby-lsp` with this error: `spawn: gem failed with exit code - and signal -. gem is  not executable`