# CMDUI enhancement tools

## tmux

The prefix key is configured by `.tmux.config` file. The default prefix key is `CTRL+b`.

### Window management

|Command	|Result|
|---|---|
|Prefix + c	|Create a new window|
|Prefix + p	|Switch to the previous window|
|Prefix + n	|Switch to the next window|
|Prefix + 0-9	|Switch to a window using it’s index number|
|Prefix + w	|Choose a window from an interactive list|
|exit	|Close a window|
|Prefix + &	|Force kill-all processes in an unresponsive window|

### Pane management

|Command	|Result|
|---|---|
|Prefix + “	|Split the active pane horizontally|
|Prefix + %	|Split the active pane vertically|
|Prefix + arrow key	|Switch to another pane|
|Prefix + ALT+arrow	|Resize the active pane|
|Prefix + z	|Zoom in on the active pane. Press the same combination again to exit zoom mode|
|exit	|Close the active pane|
|Prefix + x	|Force kill an unresponsive process in a pane|

### Scroll mode

Prefix + `[`, then you can use your normal navigation keys to scroll around (eg. `Up Arrow` or `PgDn`).

Press `q` to quit scroll mode.

When mouse mode is on: press `Shift`

### Customizing tmux

Create `~/.tmux.conf` and fill it with the following content

```
# remap prefix from 'C-b' to 'C-a'
unbind C-b
set-option -g prefix C-a
bind-key C-a send-prefix

# split panes using | and -
bind | split-window -h
bind - split-window -v
unbind '"'
unbind %

# reload config file (change file location to your the tmux.conf you want to use)
bind r source-file ~/.tmux.conf

# Enable mouse mode (tmux 2.1 and above)
set -g mouse on
```

## zsh

Install zsh

```
sudo apt install zsh powerline fonts-powerline
```

Create `.zshrc`

```
git clone https://github.com/robbyrussell/oh-my-zsh.git ~/.oh-my-zsh
cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
```

Modify `.zshrc`

```
ZSH_THEME="agnoster"
```

Change default shell to zsh

```
chsh -s /bin/zsh
```

## Get rid of Ubuntu colorized shell

Comment the following lines

```
# set a fancy prompt (non-color, unless we know we "want" color)
case "$TERM" in
    xterm-color|*-256color) color_prompt=yes;;
esac

# enable color support of ls and also add handy aliases
if [ -x /usr/bin/dircolors ]; then
    test -r ~/.dircolors && eval "$(dircolors -b ~/.dircolors)" || eval "$(dir$
    alias ls='ls --color=auto'
    #alias dir='dir --color=auto'
    #alias vdir='vdir --color=auto'

    alias grep='grep --color=auto'
    alias fgrep='fgrep --color=auto'
    alias egrep='egrep --color=auto'
fi
```

## References

1. [How to Use tmux the Terminal Multiplexer](https://www.linode.com/docs/networking/ssh/persistent-terminal-sessions-with-tmux/)

1. [How do I scroll in tmux?](https://superuser.com/questions/209437/how-do-i-scroll-in-tmux/209608)

1. [StackExchange: Tmux mouse-mode on does not allow to select text with mouse](https://unix.stackexchange.com/questions/332419/tmux-mouse-mode-on-does-not-allow-to-select-text-with-mouse)

1. [Making tmux Pretty and Usable - A Guide to Customizing your tmux.conf](https://www.hamvocke.com/blog/a-guide-to-customizing-your-tmux-conf/)

1. [Install Z-shell (Oh My Zsh) on Ubuntu 18.04 LTS](https://dev.to/mskian/install-z-shell-oh-my-zsh-on-ubuntu-1804-lts-4cm4)

1. [How to setup a nice looking terminal with WSL in Windows 10 Creators Update](https://medium.com/@Andreas_cmj/how-to-setup-a-nice-looking-terminal-with-wsl-in-windows-10-creators-update-2b468ed7c326)

1. [Github: wsl-terminal](https://github.com/goreliu/wsl-terminal)
