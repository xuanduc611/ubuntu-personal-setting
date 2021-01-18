# SETTING

## Vim editor

Create `~/.vimrc` if the file hasn't exist yet.

``` shell
$ touch ~/.vimrc
```

Set tab space, auto indent, show line number.

``` bash
" Only do this part when compiled with support for autocommands.
if has("autocmd")
    " Use filetype detection and file-based automatic indenting.
    filetype plugin indent on

    " Use actual tab chars in Makefiles.
    autocmd FileType make set tabstop=8 shiftwidth=8 softtabstop=0 noexpandtab
endif

" For everything else, use a tab width of 4 space chars.
set tabstop=4       " The width of a TAB is set to 4.
                    " Still it is a \t. It is just that
                    " Vim will interpret it to be having
                    " a width of 4.
set shiftwidth=4    " Indents will have a width of 4.
set softtabstop=4   " Sets the number of columns for a TAB.
set expandtab       " Expand TABs to spaces.
set autoindent
set linenumber
```

## Bash prompt
You can use bashpromt generator like [bashrcgenerator.com](http://bashrcgenerator.com/) to get your desired setting for PS1.

Open `~/.bashrc` and add below lines

``` bash
if [ "$color_prompt" = yes ]; then
#PS1='${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ '
PS1="\${debian_chroot:+($debian_chroot)}\[\033[01;32m\]\[\033[38;5;10m\]\u\[$(tput sgr0)\]\[$(tput bold)\]@\[$(tput sgr0)\]\[\033[01;32m\]\[\033[38;5;10m\]\h\[$(tput sgr0)\]:\[\033[01;34m\]\W\[\033[00m\]\$ "

else
PS1='${debian_chroot:+($debian_chroot)}\u@\h:\W\$ '
fi
```
