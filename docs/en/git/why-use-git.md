---
title: Why use Git
---

# Why use Git

Imagine you are writing a long story on your computer.

You write several paragraphs, decide to delete one because you do not like it, and the next day you realize the original was better.

Can you get it back?

If you did not make a manual copy before deleting it, probably not.

## The real problem

When we program, the same thing happens, but more often and with more files.

- You try an idea and the code stops working.
- You edit a file at night and the next day you cannot remember what you changed.
- You need to go back to a working version, but you have no way to recover it.

Many beginners solve this by creating manual copies: `project_final.py`, `project_final2.py`, `project_final2_DEFINITIVE.py`. It works, but it is slow, confusing, and easy to forget.

## The solution

Git is a tool that automatically saves a "snapshot" of all your files whenever you ask it to.

Each snapshot includes which files existed, what they contained, and when it was saved. You can jump between those snapshots at any time, compare them, or even try ideas in parallel without touching your main work.

It is like having unlimited save points in a video game, but for your code.

## Key advantages

**1. You can experiment without fear**

You want to try a risky idea. If it goes wrong, you simply go back to the previous snapshot. Nothing you did affects your main work until you decide it is ready.

**2. You can go back at any time**

If you discover that something stopped working three days ago, you can see exactly what changed and recover the previous version without searching through duplicated folders.

**3. You know what you changed and why**

Each snapshot has a descriptive label that you write yourself: "add login button", "fix price calculation error". This lets you read your project's history like a journal.

**4. It makes working with other people easier**

When several people edit the same files, Git helps combine the changes and warns you if two people modified the same line at the same time. This prevents someone from accidentally overwriting another person's work.

## When to start

From the very first project, no matter how small.

You do not need to wait until you have a big job or until you join a team. Using Git on personal projects gets you used to thinking in versions and gives you confidence from day one.

## What now?

If you want to try it with your own hands, you can follow the hands-on guide [Git for Kids: branches, commits, and merges](git-for-kids-cli.md). It is designed for people who have never used Git: it explains concepts step by step and guides you through your first repository.

