## tmux

For every key binding, there's a prefix `ctrl + b` to activate that binding
- `w`: to list windows in the session in the format of index (which can be navigated using mouse clicks from there?)
- `:`: to type some commands (similar to the usage in `vi` editor)
- To swap window in tmux after getting into command typing (`ctrl + b`, then `:`)
	- `swap-window -s 3 -t 1`: to swap window at positions 3 and 1
	- `swap-window -t 0`: to swap the window to the top position
	- `swap-window -t -1`: to the swap the current window with the window at it's left (by default it doesn't stay on the same window the command is issued, use `-d` flag to stay on the same window after swapping)
	- `swap-window -t +1`: to the swap the current window with the window at it's right (by default it doesn't stay on the same window the command is issued, use `-d` flag to stay on the same window after swapping)


[tmux scrolling](https://unix.stackexchange.com/questions/26548/write-all-tmux-scrollback-to-a-file) useful link for getting scrolling commands




