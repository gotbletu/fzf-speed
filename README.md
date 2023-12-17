# fzf-speed 2.0
- use tmux popup/fzf to execute tmux commands instead of hotkeys
- demo https://youtu.be/41JxYe70Xwo
- 2.0 update: just a single script now and only for tmux options
- use my other script fzf-nova, if you want a script launcher in tmux

#### bind to a tmux hotkey (e.g prefix + `):
    
    $EDITOR ~/.tmux.conf
    
    # popup only works on tmux 3.2+
    # if fzf-speed is already in your $PATH
    bind-key ` capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; display-popup -w 80% -h 60% -E "fzf-speed"
    
    # else point to /path/of/script
    bind-key ` capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; display-popup -w 80% -h 60% -E "/path/to/fzf-speed"
    
    # to use regular split-window for binding (lower than tmux 3.2)
    bind-key ` capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; split-window -hZ "/path/to/fzf-speed" \; last-pane -Z
    
    bind-key ` capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; split-window "/path/to/fzf-speed"
    
    # auto attach the next existing session if kill-session or last window is killed 
    set-option -g detach-on-destroy off
    

## options that as "custom" in it you can change or add your own
- goto- : allows you to jump to a specific named window
  - you dont need to change any code
  - just copy/paste a new entry and just rename the "win_name"
  - e.g _weechat_ to like _htop_ and it will always jump any tmux window named _htop_
- workspace- : allows you to spawn a session and auto run any command layout
  - see the example code inside

### author
- gotbletu (@youtube|github|odysee)
- https://www.youtube.com/user/gotbletu

