# Intruction for prepare Tmux

## Install Tmux

1- Update repos

```
sudo apt update
```

2- Install Tmux

```
sudo apt install tmux
```

## Save and Restore in Tmux

1- clone this repo

```
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

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

```
tmux source ~/.tmux.conf
```

4- Open tmux -> run Tmux and then Ctrl+b + I(shift + i)

__Save Process__    ---> Create your own session and the Ctrl+b + ctrl+s to save session

__Restore Process__ ---> Use Ctrl+b + ctrl+r to restore saved session

## Shortkeys

__at First you should click *ctrl+b* and then use other to move the mode__

| Row | Shortkey    | Description    |
| :---:   | :---: | :---: |
| 1 | % ( shift + 5)   | divide vertically   |
| 2 |"   | divide horizontally   |
| 3 |z   | zoom to one part |
| 4 | up,down,right,left  | move between windows   |
| 5 | ctrl + up,down,right,left   | resize windows   |




