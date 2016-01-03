# go-vim Docker image
This Docker image adds [Go](https://golang.org/) tools and the following vim plugins to the [official Go image](https://registry.hub.docker.com/_/golang/):

* [vim-go](https://github.com/fatih/vim-go)
* [tagbar](https://github.com/majutsushi/tagbar)
* [neocomplete](https://github.com/Shougo/neocomplete)
* [NERD Tree](https://github.com/scrooloose/nerdtree)
* [vim-airline](https://github.com/bling/vim-airline)
* [fugitive.vim](https://github.com/tpope/vim-fugitive)
* [NERD Tree tabs](https://github.com/jistr/vim-nerdtree-tabs)
* [undotree](https://github.com/mbbill/undotree)
* [vim-easymotion](https://github.com/Lokaltog/vim-easymotion)
* [NERD Commenter](https://github.com/scrooloose/nerdcommenter)

![screenshot](https://griffeltavla.files.wordpress.com/2016/01/go-docker-dev.png "To the left is a file browser which can be toggled with F8. To the right is a pane that lists specific tags that help navigation, toggled with F7. Center bottom is the source code and center top is the Go doc for the Printf function, opened by holding the leader key (' , ') and typing 'gd' or 'gv'")


## Usage

Run this image from within your go workspace. You can then edit your project using `vim`, and usual go commands: `go build`, `go run`, etc.

```
cd your/go/workspace
docker run --rm -tiv `pwd`:/go mbrt/golang-vim-dev
```

A number of shortcuts to use various golang tools from Vim is provided. Look for them in the `.vimrc` file.

## Limitations

This image lacks [gdb](https://golang.org/doc/gdb) support. If anyone has managed to get it working on this image, please let me know (breakpoints are not working for me).

## Changes from upstream project

* Fixed the broken build.
* VIM background is set to black in order to maximize contrast.
* [New plugin](https://github.com/Rykka/colorv.vim) added to help users adjust the vim theme colors.
* Leader key changed to `,`
* The `sudo` and `man` utilities are included to offer more environment control and information.
