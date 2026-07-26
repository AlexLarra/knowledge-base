# Creating a `tmux` Session on the Server Connected via SSH for Long-Running Scripts

When you have a script that will take a long time to run on a server, it's beneficial to use `tmux` to keep the process running even if you disconnect from the server. Here's a step-by-step guide on how to do it:

## Step 1: Connect to Your Server

Use SSH to connect to your server.

```
ssh user@your-server.com
```

Remember the machine you just got connected to (e.g. `app01`). The `tmux` session lives only on that machine, so if you reconnect later make sure you are on the same one.

## Step 2: Start a `tmux` Session

Start a new `tmux` session. You can name the session for easy identification.

```
tmux new -s script
```

## Step 3: Run Your Script

```
cd /path/to/your/project
./your-long-running-script.sh
```

It is a good practice to add some logging output (e.g. `puts` in Ruby, `print` in Python) inside your script so you can verify it is making progress.

## Step 4: Detach from the `tmux` Session

Detach from the `tmux` session while leaving your script running in the background.

```
Ctrl + b, then d
```

Press `Ctrl` and `b` together, then release both keys and press `d`. This detaches the session.

## Step 5: Reattach to the tmux Session

To check on the progress of your script or to reattach to the session at any time, first connect to the server (make sure you are on the correct machine) and list all active `tmux` sessions:

```
tmux ls
```

Your session `script` should appear in the list.

Reattach to the session:

```
tmux attach -t script
```

## Step 6: Kill a tmux Session

Once your script has finished running and you no longer need the tmux session, you can kill it. If you are already attached, just use `Ctrl + d` as you would normally. If you are detached and want to kill it remotely, use:

```
tmux kill-session -t script
```
