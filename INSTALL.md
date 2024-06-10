### [Vim](http://www.vim.org/)

#### Install

1. Create theme folder (in case you don't have it yet):

- `\*nix`:

```bash
# vim 9+
mkdir -p ~/.vim/pack/themes/start
```

- Windows: create directory `$HOME\vimfiles\pack\themes\start` or
  `$HOME\vimfiles\pack\themes\opt`, according to your version.

2. Navigate to the folder above:

- `\*nix`:

```bash
# vim 9+
cd ~/.vim/pack/themes/start
```

- Windows: navigate to the directory you created earlier

3. Clone the repository using the "dracula" name:

```bash
git clone https://github.com/ethanmchls/vim9-dracula.git dracula
```

(Or use your favorite GUI client, or download the ZIP)

4. Edit your `vimrc` file with the following content:

```
syntax enable
colorscheme dracula
```

If your background is gray rather than the proper dracula background, edit your `vimrc` and add the following:

```
let g:dracula_colorterm = 0
```

The location of the `vimrc` varies between platforms:

- `\*nix`: `~/.vim/vimrc` or `~/.vimrc`
- Windows: `$HOME\vimfiles\vimrc` or `$HOME\_vimrc`

#### Install using other plugin managers

- If you [use vim + pathogen + submodules](http://vimcasts.org/episodes/synchronizing-plugins-with-git-submodules-and-pathogen/):

Navigate to your vim directory (`\*nix`: `~/.vim`; Windows: `$HOME\vimfiles`)

```bash
git submodule add git@github.com:ethanmchls/vim9-dracula.git bundle/dracula
```

Place `colorscheme dracula` after `execute pathogen#infect()`.

- If you [use vim + vundle](https://github.com/VundleVim/Vundle):

```vim
Plugin 'ethanmchls/vim9-dracula', { 'name': 'dracula' }
:PluginInstall
```

Place `colorscheme dracula` after `call vundle#end()`.

- If you [use vim-plug](https://github.com/junegunn/vim-plug) (\`as\` will install
  the plugin in a directory called 'dracula' instead of just 'vim'):

```vim
Plug 'ethanmchls/vim9-dracula', { 'as': 'dracula' }
:PlugInstall
```

Place `colorscheme dracula` after `call plug#end()`.

- If you [use spacevim](https://spacevim.org), put the
  following in `~/.SpaceVim.d/init.toml`:

```toml
[options]
  colorscheme = "dracula"
  colorscheme_bg = "dark"
[[custom_plugins]]
  repo = "ethanmchls/vim9-dracula"
  name = "dracula"
  merged = false
```

---

Note that dracula must be in your `'runtimepath'` to load properly: Version 2.0
introduced autoload functionality for part of the plugin, which doesn't work
without `'runtimepath'` properly set. Consult your plugin-managers documentation
to make sure you put dracula on the `'runtimepath'` before loading it. For
`|packages|`, versions 8.2 and later will autoload `start` packages
correctly even in your vimrc.
