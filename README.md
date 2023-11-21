# fzf-speed
 
- control tmux with just scripts instead of hotkeys
- tmux popup + fzf as a script launcher, aka dmenu/rofi for tmux
- demo https://youtu.be/41JxYe70Xwo

#### bind to a tmux hotkey (e.g prefix+TAB):
    
    $EDITOR ~/.tmux.conf
    
    # popup only works on tmux 3.2+
    # if fzf-speed is already in your $PATH
    bind-key Tab capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; display-popup -w 80% -h 60% -E "fzf-speed"
    
    # else point to /path/of/script
    bind-key Tab capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; display-popup -w 80% -h 60% -E "/path/to/fzf-speed"
    
    # to use regular split-window for binding (lower than tmux 3.2)
    bind-key Tab capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; split-window -hZ "/path/to/fzf-speed" \; last-pane -Z
    
    bind-key Tab capture-pane \; save-buffer /tmp/tmux-buffer \; delete-buffer \; split-window "/path/to/fzf-speed"
    
    # auto attach the next existing session if kill-session or last window is killed 
    set-option -g detach-on-destroy off
    

#### quick jump to named window
- you dont need to change any code, copy the file and just rename the filename
- e.g _htop_ to like _weechat_ and it will always jump any tmux window named _weechat_

    _tmux_goto_htop,--.jump.to.custom.named.window.(process.viewer)
    _tmux_goto_weechat,--.jump.to.custom.named.window.(irc.chat.client)
    

#### spawn your own custom session layout
- if you want to spawn a bunch of tmux windows/panes and execute commands on it
- see the example code inside

    _tmux_workspace_example,--.jump.to.or.start.custom.session


### author
- gotbletu (@youtube|github|odysee)
- https://www.youtube.com/user/gotbletu

