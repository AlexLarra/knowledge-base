---
title: From local Git to GitHub
---

# From local Git to GitHub

This guide is a follow-up to [Git for Kids](git-for-kids-cli.md).
There you learned to save your work locally with `commit`, `branch`, and `merge`.
Here we will see how to push those changes to the cloud and share them.

## From local to the cloud

Git by itself works on your computer. But if you want:

- a backup outside your machine,
- or to work with other people,

you need a **hosting service** for your repository.

GitHub is the best known and most widely used. GitLab is a very valid
alternative, especially in professional and open-source environments that look
for more integrated continuous-integration tools.

## What you need before starting

- An account on GitHub (or GitLab).
- A repository created on the platform, either by cloning an existing one or
  starting a new one.

We will not go into web details; we assume you already have the remote
repository ready.

## New commands

| Command | What it does |
|---------|--------------|
| `git clone URL` | Downloads a remote repository to your computer |
| `git push` | Uploads your local commits to the remote |
| `git pull` | Downloads new commits from the remote to your local branch |

## Typical workflow

1. You work on your computer: edit files, run `git add` and `git commit`
   (just like you learned in the previous guide).
2. When you want to share your progress: `git push`.
3. If others have made changes: `git pull` to bring them in before continuing.

This is the same story-building game, but now the story lives in the cloud and
several people can write it.

## Pushing a new branch for the first time

When you create a local branch with `git switch -c` and make commits on it,
`git push` alone will not work because Git does not yet know which remote
branch it belongs to.

You have to tell it where to push it the first time:

```bash
git push -u origin branch_name
```

The `-u` option (or `--set-upstream`) creates the link between your local
branch and the remote one. From then on, `git push` alone on that branch will
be enough.

## Final note on change integration

When you pull changes with `git pull`, Git may merge them automatically or
ask you to resolve conflicts, just like with a local `git merge`. To keep a
cleaner history, it is convenient to configure Git to use **rebase by default**
when pulling:

```bash
git config --global pull.rebase true
```

With this, your local commits are reapplied on top of the newly downloaded
changes, producing a more orderly history line.
