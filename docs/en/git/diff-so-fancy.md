---
title: diff-so-fancy (optional)
---

# diff-so-fancy

> **Note:** This is completely optional. It is not needed to use Git. It is a convenience improvement for those who have been working with `git diff` for a while and want the output to be more readable.

## What it does

`diff-so-fancy` improves the presentation of Git diffs. It turns the raw output of `git diff` into something cleaner, with better color differentiation and without the `+` and `-` symbols at the beginning of each line.

It is useful when you review changes frequently and prefer a nicer reading experience.

## Installation

Before installing through other means, check if your distribution includes it in its official repositories.

### Linux

**Arch Linux:**

```bash
sudo pacman -S diff-so-fancy
```

**Debian / Ubuntu:**

```bash
sudo apt install diff-so-fancy
```

### macOS

```bash
brew install diff-so-fancy
```

### If it is not in the repositories

You can install it via npm:

```bash
npm install -g diff-so-fancy
```

Or download the script directly from its [official repository](https://github.com/so-fancy/diff-so-fancy).

## Configuration with `.gitconfig`

The usual way to use it is by configuring Git to pipe the output of `git diff` (and related commands) through `diff-so-fancy`.

Add or modify the following sections in your `~/.gitconfig` file:

```ini
[core]
    pager = diff-so-fancy | less --tabs=4 -RFX

[color]
    ui = true

[color "diff-highlight"]
    oldNormal = red bold
    oldHighlight = red bold 52
    newNormal = green bold
    newHighlight = green bold 22

[color "diff"]
    meta = 11
    frag = magenta bold
    commit = yellow bold
    old = red bold
    new = green bold
    whitespace = red reverse
```

With this, commands like `git diff`, `git log -p`, or `git show` will automatically use `diff-so-fancy`.

## What now?

Open any repository and run `git diff`. If everything is set up, you will see a cleaner output with better use of color.

If something does not work, verify that `diff-so-fancy` is in your `PATH` by running `which diff-so-fancy`.
