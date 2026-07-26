# Git for Kids: Branches, Commits, and Merges (CLI only)

This guide teaches Git as if it were a story game.

- No GitHub.
- No `push` or `pull`.
- Only local Git.

## Idea in 30 seconds

- A `commit` is a saved checkpoint (a photo of your files at a moment).
- A `branch` is an alternate path to try ideas safely.
- A `merge` joins one path back into another.

Think of it like building a story with alternate endings.

## 1) Create your story project

```bash
mkdir my-first-git-story
cd my-first-git-story
git init
```

Now you have an empty local Git repository.

## 2) First commit (first checkpoint)

Create a file and save it in Git:

```bash
echo "Once upon a time there was a dragon" > story.txt
git add story.txt
git commit -m "start story"
```

What happened:

- `git add` tells Git: "put this file in the staging area".
- The staging area is the waiting room for the next `commit`.
- So `git commit` saves only the files that are in that waiting room.

Quick way to think about it:

- Edit file = write ideas.
- `git add` = choose which ideas go into the backpack.
- `git commit` = close the backpack and label it.

Useful check:

```bash
git status
```

If a file is not added, it will not be in the commit.

## 3) Create a branch (alternate path)

```bash
git switch -c dragon-ending
```

Now you are on branch `dragon-ending`.

Add a different ending and commit it:

```bash
echo "The dragon learned to cook" >> story.txt
git add story.txt
git commit -m "add funny ending"
```

## 4) Go back to main and add another change

```bash
git switch main
echo "The end" >> story.txt
git add story.txt
git commit -m "add main ending"
```

Now both branches changed the same file in different ways.

## 5) Merge branches

```bash
git merge dragon-ending
```

If Git can combine changes automatically, merge finishes immediately.
If both branches changed the same lines, Git asks you to solve a conflict first.

## 6) Visualize history

```bash
git log --oneline --graph --all
```

Typical shape:

```text
*   9f3a2d1 merge branch 'dragon-ending'
|\
| * 41ac0be add funny ending
* | 82f9b77 add main ending
|/
* 57de301 start story
```

## Simple branch drawing

Before merge:

```text
*---*---*   (dragon-ending)
     \
      *---* (main)
```

After merge:

```text
*---*---*\
     \    M  (main)
      *---*/
```

## Quick recap

- `commit` = save checkpoint
- `branch` = new path
- `merge` = join paths

That is the core of Git.
