---
title: Why use tmux
---

# Why use tmux

Imagine you are running a script on a remote server via SSH.

It has been processing data for twenty minutes. You step away from your computer, close your laptop, and when you return you discover the connection dropped and the script stopped.

Do you have to start over?

If you did not take precautions, probably yes.

## The real problem

When we work in the terminal, everything depends on that window staying open.

- We accidentally close the terminal and lose everything that was running.
- The Wi-Fi connection cuts out and a download or installation gets interrupted.
- We disconnect from a remote server and the process we left there dies instantly.

Many beginners solve this by leaving the computer on for hours or re-running everything from scratch. It works, but it is inconvenient, slow, and prone to mistakes.

## The solution

Tmux is a tool that creates terminal sessions that **stay alive** even if you close the window or lose the connection.

You can start a process inside tmux, disconnect safely, shut down your computer if you want, and when you return — from the same machine or from somewhere else — resume exactly where you left off.

It is like leaving something cooking on the stove while you go out to do other tasks. The pot is still there, the fire is still on, and when you come back everything is as you left it.

## Key advantages

**1. You do not lose work if the terminal closes**

Tmux keeps the session active on the server. Even if you close your computer's window, the process keeps running in the background.

**2. You can disconnect and come back later**

You start a long task at the office, disconnect, and from home you re-enter the same session to check on progress. Nothing is lost along the way.

**3. Multiple windows inside a single session**

Tmux lets you split the screen or open tabs, as if you had several terminals inside one. This is useful when you need to view logs in one window while editing files in another.

**4. Useful both locally and remotely**

Although it shines especially on servers via SSH, you can also use tmux on your own computer to organize tasks and prevent an accidental terminal closure from ruining what you were doing.

## When to start

From the very first script that takes more than a few minutes to run, or from your first remote connection to a server.

You do not need to wait for big projects or professional environments. Using tmux on small tasks gets you used to working safely and saves you frustration from day one.

## What now?

If you want to try it with your own hands, you can follow the hands-on guide [Creating a tmux session for long-running scripts](use-tmux-for-production-scripts.md). It is designed for people who have never used tmux: it explains the steps one by one and guides you through your first session on a remote server.

