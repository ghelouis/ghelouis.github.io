# Vim

## Commands
- Show help for command, motion, any topic: `:help <something>`
- Chain commands: use `|` between commands
- Reload current file: `:e`
- Go to line n: `:n`
- Save a file after editing it in readonly: `:w !sudo tee%`
- Activate spelling check: `:set spell spelllang=fr`
- Load colorscheme: `:colo(rscheme) <colorscheme>`
- Easter egg `:smile`

## Encrypt file
`:X`

Note: file needs to be written for the encryption to take effect.

## Load .vimrc in IntelliJ
`echo "source ~/.vimrc" > ~/.ideavimrc` (cf [https://github.com/JetBrains/ideavim](https://github.com/JetBrains/ideavim))

## Plugins
- [table mode](https://github.com/dhruvasagar/vim-table-mode)

`:TableModeEnable`/`:TableModeDisable`

`|` will format the line
