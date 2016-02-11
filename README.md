# vim cheat sheet for Ubuntu

##General
First, install ```vim-gtk``` to make sure copy / paste between vim and and system clipboard works:

```
sudo apt-get install vim-gtk
```

### Configuration in ~/.vim/.vimrc
```set nocp``` enabling features which are not Vi compatible but really nice.    
```set number``` enable line numbers    
```syntax on``` enbale syntax highlighting    
```filetype plugin indent on``` language-dependent indenting    
```set backspace=indent,eol,start``` enable backspace key    

##Plugins 
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

```FuzzyFinder``` is a File Explorer for vim.

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

As a short cut to open ```FuzzyFinder``` file explorer in current folder, add this to ```~/.vim/.vimrc```:

```
map ,f :FufFile **/<CR> -> in .vimrc
```

Files can now be browsed using ```,f```.

##Files

```:w <filename>``` write file using a new name (save as)     
```:w``` save current file    
```:vnew``` create new file in vertically split window    
```:new``` create new file in horizontally split window    
```:tabedit <filename>``` open <filename> in new tab    

##Navigation
```gg``` go to beginning of the file    
```G``` go to the end of the file     
```<n>gt``` switch tabs by number (n = number of tab)     
```CTRL+w``` switch between splits     
```/<text>``` find text
```n``` after ```/``` find next search result
```N``` after ```/``` find previous search result

##Selecting, copy/paste, formatting etc.
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
