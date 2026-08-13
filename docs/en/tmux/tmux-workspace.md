---
title: Create a tmux workspace
---

# Create a tmux workspace

Opening terminals, navigating to each project, and running commands manually every morning is repetitive. With a tmux script you can spin up your entire environment in seconds with a single command.

## The goal

When you type `tw` in the terminal, this should happen:

- If a session named `work` already exists, tmux attaches to it.
- If it does not exist, it is created automatically with two windows ready for work.

## Step 1: create the startup script

Save this file in your home directory as `~/.tmux_work.zsh`:

```zsh
#!/bin/zsh

SESSION="work"

tmux new -s $SESSION -d

# Window 1: main application
tmux send-keys -t $SESSION 'cd ~/workspace/app1 && clear' C-m
tmux split-window -v
tmux send-keys -t $SESSION 'cd ~/workspace/app1 && clear' C-m
tmux send-keys -t $SESSION 'npm run dev' C-m
tmux select-pane -t 1

# Window 2: api or backend
tmux new-window -t $SESSION
tmux send-keys -t $SESSION 'cd ~/workspace/app2 && clear' C-m
tmux split-window -h
tmux send-keys -t $SESSION 'cd ~/workspace/app2 && clear' C-m
tmux send-keys -t $SESSION 'python manage.py runserver' C-m
tmux select-pane -t 1

tmux select-window -t $SESSION:1
tmux attach -t $SESSION
```

Adjust the paths (`~/workspace/app1`, `~/workspace/app2`) and commands (`npm run dev`, `python manage.py runserver`) to match what you use on a daily basis.

Make it executable:

```sh
chmod +x ~/.tmux_work.zsh
```

## Step 2: create the alias

Add this to your `~/.zshrc` (or `~/.bashrc`):

```sh
alias tw="tmux attach -t work || sh ~/.tmux_work.zsh"
```

Reload the configuration:

```sh
source ~/.zshrc
```

## Step 3: use it

Type `tw` and tmux does the rest.

```sh
tw
```

## Step 4: close the session

If you want to shut everything down and kill the session:

```sh
tmux kill-session -t work
```

You can also detach from it (`Ctrl + b`, then `d`) to leave it running in the background.

---

> Although they add dependencies, you also have alternatives such as **tmuxinator** or **tmuxp** that let you define sessions through YAML configuration files.
