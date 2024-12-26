# vim-jrnl

`vim-jrnl` is a simple syntax plugin for [Vim](https://www.vim.org) and [Neovim](https://neovim.io), tailored for the [jrnl](https://jrnl.sh/) format.

This plugin is a fork of [cmhamill/vim-jrnl](https://github.com/cmhamill/vim-jrnl).

The `master` branch mirrors the original repository (`cmhamill/vim-jrnl`), ensuring compatibility with upstream changes.

**The `custom` branch, set as default, introduces:**

- detect and autoload for the `*.jrnl` file extension,
- detect and highlight the 'timeformat' `YYYY-MM-DD HH:MM:SS`

GitHub: <https://github.com/Gregory-K/vim-jrnl>  
Mod   : Gregory.K


## Installation

### Using vim-plug

[vim-plug](https://github.com/junegunn/vim-plug)

Add the following line to `vimrc` or `init.vim`:

```vim
Plug 'Gregory-K/vim-jrnl'
```

Then, install the plugin:

```vim
:PlugInstall
```

### Manual Installation

Clone this repository into  
`.vim` / `~/.config/vim` / `~/vimfiles` _(windows)_ directory:

```sh
mkdir -p ~/.config/vim/pack/vendor/start/vim-jrnl
cd ~/.config/vim/pack/vendor/start/vim-jrnl
git clone https://github.com/Gregory-K/vim-jrnl .
```


## Usage

Simply open a `.jrnl` file in Vim or Neovim, and the syntax highlighting will be applied automatically:

```sh
vim my-journal.jrnl
```

### jrnl set-up tip!

REL:  
- <https://jrnl.sh/en/stable/privacy-and-security/#vim>
- <https://github.com/jrnl-org/jrnl/issues/491#issuecomment-347361507>

If you want `jrnl --edit` to open 'vim' with privacy leaky features disabled:

1. Into `.vimrc`

```vim
" ~~ JRNL
function! JrnlSettings()
    set viminfo= noswapfile noundofile nobackup nowritebackup noshelltemp history=0 nomodeline secure
endfunction
command! JrnlSettings call JrnlSettings()
```

2. Then in `.jrnl_config`:

```json
{
  "editor": "vim -c JrnlSettings",
}
```

OR `jrnl.yaml`:

```yml
editor: vim -c JrnlSettings
```
