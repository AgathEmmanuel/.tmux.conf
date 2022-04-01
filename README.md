# .tmux.conf

# remap  prefix Ctrl+B to Alt + a
set -g prefix M-a
unbind C-b
bind M-a send-prefix
# split panes using - and =
bind - split-window -h
bind = split-window -v
unbind '"'
unbind %

# Move around panes with hjkl, as one would in vim after pressing ctrl + w
bind h select-pane -L
bind j select-pane -D
bind k select-pane -U
bind l select-pane -R

# copy mode : vim 

# set vi mode for copy mode
setw -g mode-keys vi
# Setup 'v' to begin selection, just like Vim
bind-key -T copy-mode-vi 'v' send -X begin-selection
# Setup 'y' to copy selection
bind -T copy-mode-vi y send-keys -X copy-pipe-and-cancel 'xclip -in -selection clipboard'




## Commands


Command 	Description  
tmux 	start tmux  
tmux new -s <name> 	start tmux with <name>  
tmux ls 	shows the list of sessions  
tmux a # 	attach the detached-session  
tmux a -t <name> 	attach the detached-session to <name>  
tmux kill-session –t <name> 	kill the session <name>  
tmux kill-server 	kill the tmux server  


Press ‘ctrl-a’ and then type the commands from the below tables  

? 	show the list of commands  
r 	reload .tmux.conf file  
s 	list sessions  
$ 	rename sessions  
d 	detach session  
w 	list windows and select one  
, 	rename window  
c or N 	create new window  
n 	go to next window  
p 	go to previous window  
f 	find window  
& 	kill window  
0-9 	go to window 0-9  
% 	vertical split  
" 	horizontal split  
x 	kill pane  
o 	go to next pane  

h, j, k, l 	go to next pane in vim-style  
z 		toggle full-screen mode for current pane  
arrow keys 	resize the pane  
q 		show pane-numbers  
: 		go to command mode  
list-keys 	shows all the commands  
list-panes 	shows the names of all panes  

resize-pane -D 20 	resize down  
resize-pane -U 20 	resize up  
resize-pane -L 20 	resize left  
resize-pane -R 20 	resize right  
swap-pane -s 3 -t 1 	swap pane '1' with pane '3'  
Esc 			go to copy mode  
q 			quit mode  
j, k, l, h 	down, up, right left  
J or K 		scroll down or up  
F or B 		go to next or previous page  
$ 		go to end of line  
0 		go to beginning of line  
w or b 		go to next or previous word  
/ or ? 		search forward or backward  
n 		search next (use after above commands)  
space 		start selection  
Esc 		clear selection  
y 		copy section  
p 		paste selection  
  
 


Is there a tmux shortcut to create a new session?  
  
There are no predefined shortcuts, the only native way to do it is :  
  
    Create session: tmux new -s session_name  
  
    Ctrl-B + d to detach  
  
    Return to your session: tmux attach-session -t session_name  
  
You can use tmux kill-server to cleanly and gracefully kill all tmux open sessions (and server).  
  
If you are inside a tmux session you would like to keep, use 

    tmux kill-session -a to close all other sessions.  
  
To close a specific session, use 

    tmux list-sessions to identify the session you want to kill, and then use 
    tmux kill-session -t targetSession to kill that specific session.  
  
Also you can grossly kill all tmux processes with 
    pkill -f tmux.  
 



## Links  


[https://tmuxguide.readthedocs.io/en/latest/tmux/tmux.html](https://tmuxguide.readthedocs.io/en/latest/tmux/tmux.html)  



