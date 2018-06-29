# vim cheat sheet for Ubuntu

## General

First, install ```vim-gtk``` to make sure copy / paste between vim and and system clipboard works:

```
sudo apt-get install vim-gtk
```

## Keyboard shortcuts

### Files

```:w <filename>``` write file using a new name (save as)
```:w``` save current file
```:vnew``` create new file in vertically split window
```:new``` create new file in horizontally split window
```:tabedit <filename>``` open <filename> in new tab
```:q``` close file / vim
```:q!``` close file / vim and discard changes
```:x``` close file / vim and save changes

### Navigation
```gg``` go to beginning of the file
```G``` go to the end of the file
```<n>gt``` switch tabs by number (n = number of tab)
```CTRL+w``` switch between splits
```/<text>``` find text
```n``` after ```/``` find next search result
```N``` after ```/``` find previous search result

### Selecting, copy/paste, formatting etc.
```V``` Visual Mode, now you can select parts of the file using arrow keys
```ggVG``` select all
```y``` copy selection to buffer
```p``` paste buffer
```dd``` delete current line
```u``` undo
```"+p``` paste from system clipboard
```"+y``` copy to system clipboard
```gg=G``` reformat file
```V=``` reformat selection
```=``` reindent current section

## Modes
Vim has several modes.
```Normal``` mode is active after you opened vim (or a file using vim).
In normal mode you can not edit text, but you can execute commands as shown below.

```Insert``` mode allows you to edit text. You can activate insert mode by pressing ```i``` in normal mode.
You can exit insert mode by pressing ```ESC```

```Visual``` mode allows you to select text.
It can be activated by hitting ```V```.
You can exit visual mode by pressing ```ESC```

## Configuration in ~/.vim/.vimrc
```set nocp``` enabling features which are not Vi compatible but really nice.
```set number``` enable line numbers
```syntax on``` enbale syntax highlighting
```filetype plugin indent on``` language-dependent indenting
```set backspace=indent,eol,start``` enable backspace key

## Plugins

Plugins are installed using Pathogen, a plugin system for vim.
So we have to install Pathogen first:

```
mkdir -p ~/.vim/autoload ~/.vim/bundle
curl -LSso ~/.vim/autoload/pathogen.vim https://tpo.pe/pathogen.vim
```

In ```~/.vim/.vimrc``` add:

```
execute pathogen#infect()
```

### FuzzyFinder

[FuzzyFinder](http://www.vim.org/scripts/script.php?script_id=1984) is a File Explorer for vim.

#### Installing FuzzyFinder

```
cd ~/.vim/bundle
git clone git@github.com:vim-scripts/L9.git
git clone git@github.com:vim-scripts/FuzzyFinder.git
```

#### Using FuzzyFinder

```:FufFile``` opens file explorer of ```FuzzyFinder```i
```CTRL+Enter``` opens a file in a new split
```CTRL+L``` opens a file in a new tab

As a shortcut to open ```FuzzyFinder``` file explorer in current folder, add this to ```~/.vim/.vimrc```:

```
map ,f :FufFile **/<CR>
```

Files can now be browsed using ```,f```.
