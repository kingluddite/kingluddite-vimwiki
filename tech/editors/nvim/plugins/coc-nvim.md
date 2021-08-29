# coc.nvim (Conquer of Completion)
## Install Instructions
1. Place this in your `~/.config/nvim`:

Plug 'neoclide/coc.nvim'

2. Then run the following in Vim:

`:source %`
`:PlugInstall`

## Troubleshooting
### Problem `.tsx` file not formatting
* `.tsx` files have the correct typescript.tsx filetype, but do not format on save

#### Solution
`typescript` should be used in `coc.preferences.formatOnSaveFileTypes`
<a href="https://github.com/neoclide/coc-tsserver/issues/37" target="_blank">[ref]</a>
