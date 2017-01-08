

### context: WINDOW
| ACTION              | KEY     | BINDING | DESCRIPTION / [shell] MAPPING | CMD |
|:---                 |:---:    |:---      |:---          | |
| Last Window bind    | S-C-a   | | | `bind -n S-C-a last-window`
| previous-window     | S-Left   | | shift arrow left | `bind -n S-Left  previous-window`
| next-window         | S-Right   | | shift arrow right | `bind -n S-Right next-window`
||||Split pane|`bind -n M-<vertical bar> split-window -h`|
|||||`bind -n M-- split-window -v`|

## context: PANE
| ACTION              | KEY     | BINDING | DESCRIPTION / [shell] MAPPING | CMD |
|:---                 |:---:    |:---      |:---          | |
|Resize Panes [iTerm2]|||ctrl+alt+shift+left   0x1b 0x68|`bind -n M-h resize-pane -L 5`|
||||ctrl+alt+shift+right  0x1b 0x6C|`bind -n M-l resize-pane -R 5`|
||||ctrl+alt+shift+up     0x1b 0x6A|`bind -n M-j resize-pane -U 5`|
||||ctrl+alt+shift+down   0x1b 0x6B|`bind -n M-k resize-pane -D 5`|
|Switch Panes [iTerm2]|||||``|
||||cmd+alt+left|`bind -n M-Left select-pane -L`|
||||cmd+alt+right  16 / 0x10|`bind -n M-Right select-pane -R`|
||||cmd+alt+up     0x1b 0x6E|`bind -n M-Up select-pane -U`|
||||cmd+alt+down   0x1b 0x70|`bind -n M-Down select-pane -D`|
|||||``|
|||||``|
|||||``|
|||||``|
|||||``|
|||||``|
|||||``|
|||||``|
|||||``|
|||||``|
|||||``|
|||||``|


| Hex | Escape Sequence | 
# 02 1b 4f 43 ^[OC [1;5C meta-OC  ctrl + shift + left
# 02 1b 4f 44 ^[OD [1;5D meta-OD  ctrl + shift + right
# 02 1b 4f 41 ^[OA meta-OA  ctrl + shift + up
# 02 1b 4f 42 ^[OB meta-OB  ctrl + shift + down
# 0x1b 0x4f 0x43

# tmux escape 0x02
# escape 0x1b ^[;
# delete 0x7f

# TESTING
# python -c "from curses import ascii as A; print A.unctrl(0x4A)"
# python -c "from curses import ascii as A; print A.unctrl(0x7d),A.unctrl(0x5B),A.ctrl(ord('C'));"
# xxd -pkg
# showkey -a
# tmux -C