# AI Bootcamp Materials

This repository holds everything we use in the **AI track's Bootcamp**:

| Folder | What's inside |
|---|---|
| [`Day 1/`](Day%201/) | The tools you need (Python, conda, Jupyter, Kaggle, Colab) and why we use them |
| [`notebooks/`](notebooks/) | The Jupyter notebooks we write code in during the sessions, with a full walkthrough |

If you have **never used Git**, the short guide below covers the only commands you need for this bootcamp — nothing more. Read it once and you're set.

---

# How to use Git — only the essentials

## What is Git and why do we need it?

**Git** is a free tool that records **snapshots of your files over time**. Each snapshot is called a **commit**, and each commit keeps a note of *who changed what and when*. That means you can never really lose your work, and you can always look back at earlier versions of any file. A folder that Git is tracking is called a **repository** (short: *repo*). **GitHub** is the website where an online copy of a repo lives, so the whole group can download it in one click and share updates with each other.

## 1. One-time setup (do this only once)

1. **Install Git** — download it from <https://git-scm.com/downloads>, pick your operating system, and install with the default (recommended) options. No other settings are needed.
2. **Check that it installed:** open a terminal (on Windows: **Git Bash**, which now exists in your Start menu, or **PowerShell**) and type:

   ```
   git --version
   ```

   Seeing something like `git version 2.45` means it is installed.

3. **Tell Git who you are** — your name and email are attached to every snapshot you make:

   ```
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

4. **Create a free GitHub account** at <https://github.com/signup> — we need it to reach this repo: <https://github.com/Collective-Lab-Builders-Group/AI-bootcamp-materials>

   The first time you **push** (explained below), a browser window opens asking you to log in to GitHub. Accept it — that is normal for new accounts.

## 2. Get your own copy of this repo (clone)

Open the terminal in whichever folder you want the project to live in, then run:

```
git clone https://github.com/Collective-Lab-Builders-Group/AI-bootcamp-materials.git
```

This downloads the whole project into a new folder called `AI-bootcamp-materials`. The big advantage over downloading a ZIP file: this folder stays **connected to GitHub**, so you can download future updates with one command (`git pull`). That is why cloning is preferred — you never have to re-download anything again.

## 3. The daily routine — 5 commands

This small loop is everything you do with Git from day to day. Run these from inside the `AI-bootcamp-materials` folder:

| Step | Command | What it does |
|---|---|---|
| 1 | `git pull` | Downloads the newest changes from GitHub **into your copy**. Run this *before* you start working. |
| 2 | `git status` | Shows which files you (or someone else) have changed. Always safe to run — it changes nothing. |
| 3 | `git add .` | Prepares your changed files to be saved ("stages" them). The `.` means *all changed files here*. |
| 4 | `git commit -m "message"` | Saves a snapshot of the prepared changes. The message is a short description of what you did, e.g. `"add day 1 notes"`. |
| 5 | `git push` | Uploads your saved snapshots to GitHub so everyone else gets them. |

A good way to remember the order: **pull → work → add → commit → push**.

## 4. Look at the history

```
git log
```

Lists every past snapshot with its author, date, and message. Press the `q` key on your keyboard to exit this view. To see what recently changed in a more compact way, use `git log --oneline` (one commit per line).

## 5. Two small problems and how to fix them

- **`git push` says "rejected"** → your copy is older than the one on GitHub. Run `git pull`, and push again afterwards.
- **You changed a file and want to throw those changes away:** run

  ```
  git restore <file-name>
  ```

  This puts the file back exactly as it was at the last commit. Only use this on your *own* work so you don't discard someone else's.

## Cheat sheets & further help

You do **not** need to memorise the commands above — keep the cheat sheet handy instead:

- 📄 **GitHub's official Git cheat sheet (PDF, 2 pages)** — every Git command summarised on one printable sheet: <https://education.github.com/git-cheat-sheet-education.pdf>
- 🗜 **NDP Software's interactive Git cheat sheet** — click any command to see exactly where it moves your files: <https://ndpsoftware.com/git-cheatsheet.html>
- 🎮 **Learn Git Branching** — learn Git interactively by playing levels in the browser: <https://learngitbranching.js.org>
- 📖 **Pro Git** — the official, free Git book (for after the bootcamp): <https://git-scm.com/book/en/v2>
- 🌱 **GitHub's own beginner guides**: <https://docs.github.com/en/get-started>
