# Intruction for prepare Tmux

## Install Tmux

1- Update repos

```sudo apt update```

2- Install Tmux

```sudo apt install tmux```

## Save and Restore in Tmux

1- clone this repo

```git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm```

2- Open your ~/.tmux.conf and add this text and then save the file

```
#List of plugins
set -g @plugin 'tmux-plugins/tpm'
set -g @plugin 'tmux-plugins/tmux-sensible'
set -g @plugin 'tmux-plugins/tmux-resurrect'


#Initialize TMUX plugin manager (keep this line at the very bottom of tmux.conf)
run '~/.tmux/plugins/tpm/tpm' 
```

3- source the config file

```tmux source ~/.tmux.conf```

4- Open tmux -> run Tmux

Save Process    --- Create your own session and the Ctrl+b + ctrl+s to save session

Restore Process --- Use Ctrl+b + ctrl+r to restore saved session





