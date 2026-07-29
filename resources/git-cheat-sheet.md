# Git Cheat Sheet

<p align="center">
  <img src="images/git.svg" alt="Git" width="48" height="48">
  &nbsp;&nbsp;&nbsp;
  <img src="images/github.svg" alt="GitHub" width="48" height="48">
</p>

The handful of Git commands we actually use, day to day. Keep the tab open; you're not expected
to memorize any of it.

## Quick reference

**Click any command to jump to what it does and why you'd use it.**

| Command | What it does |
|---|---|
| [`git clone <url>`](#getting-a-copy-of-a-project) | Download a repo from GitHub (once per project) |
| [`git status`](#checking-where-you-stand) | See what's changed — run this constantly |
| [`git add .`](#staging-your-changes) | Stage your changes for the next commit |
| [`git commit -m "message"`](#saving-a-snapshot) | Save a labeled snapshot, locally |
| [`git push`](#sending-your-work-to-github) | Upload your commits to GitHub |
| [`git pull`](#getting-everyone-elses-work) | Download everyone else's commits |
| [`git check-ignore -v <file>`](#ignoring-files-with-gitignore) | Check whether `.gitignore` is hiding a file |
| [`git branch`](#see-your-branches) | List branches, show which one you're on |
| [`git switch -c <name>`](#create-a-branch-and-switch-to-it) | Create a branch and switch to it |
| [`git switch <name>`](#switch-to-an-existing-branch) | Switch to an existing branch |
| [`gh pr create`](#pull-requests) | Open a pull request from your branch |
| [`gh pr view --web`](#pull-requests) | Open your pull request in the browser |

Almost all of your Git use is one cycle, over and over:

**change files → `add` → `commit` → `push`**

Everything else on this page supports that loop.

---

The rest of this page explains each command — the command itself on top, what it does and why
you'd reach for it underneath. This is not everything Git can do, not close; it's the short
list that covers most of what you'll type in this class.

> **Two words you'll see constantly:**
> **Repository** (or "repo") — a project folder that Git is tracking.
> **Remote** — the copy of that repo living on GitHub. Yours is called `origin`.

---

## Getting a copy of a project

```bash
git clone https://github.com/username/repo-name.git
```

Downloads a full copy of a repository from GitHub onto your machine, including its entire
history, and sets up the connection back to GitHub for you.

**Why you use it:** it's how you start working on a project that already exists — this class
repo, a teammate's project, or your own repo on a new laptop. You only clone a given project
**once**; after that you `pull` to get updates.

Clone creates a new folder named after the repo, so run it from wherever you keep your
projects — not inside another repo.

---

## Checking where you stand

```bash
git status
```

Shows what's changed since your last commit: files you've edited, files Git isn't tracking
yet, and what's staged and ready to commit.

**Why you use it:** it's the "where am I?" command. Run it constantly — before adding, before
committing, any time you're unsure what Git is about to do. It's free, it changes nothing, and
it will save you more confusion than any other command here. When you're stuck, `git status`
usually tells you the next move.

---

## Staging your changes

```bash
git add .
```

Stages your changes — tells Git "these are the edits I want in my next commit." The `.` means
"everything in this folder and below."

**Why you use it:** Git doesn't assume every file you touched belongs in the same commit. You
pick. The staging step is what lets you group related changes together instead of dumping
unrelated work into one lump.

You can also stage one file at a time when you only want part of your work included:

```bash
git add src/index.html
```

---

## Saving a snapshot

```bash
git commit -m "Add contact form validation"
```

Records everything you staged as a permanent snapshot in your project's history, labeled with
the message you wrote after `-m`.

**Why you use it:** commits are your save points and your undo history. Because each one is
labeled, the history becomes a readable story of how the project got here — and you can go
back to any point in it.

Commit often, in small pieces. Write the message as **what changed and why**, not "stuff" or
"fixes." Future you reads these, usually while trying to figure out when something broke.

> Commits live only on **your machine** until you push. Committing is not backing up.

---

## Sending your work to GitHub

```bash
git push
```

Uploads your commits to GitHub so they exist somewhere other than your laptop.

**Why you use it:** it's how your work gets backed up, becomes visible to everyone else, and
becomes eligible for a pull request. Nothing you've committed is safe from a dead hard drive
until it's pushed.

The very first push on a brand-new branch needs a little more, because GitHub doesn't know
about that branch yet:

```bash
git push -u origin my-branch-name
```

The `-u` links your local branch to the one on GitHub. After that, plain `git push` is enough
for the rest of that branch's life.

---

## Getting everyone else's work

```bash
git pull
```

Downloads new commits from GitHub and merges them into the branch you're on.

**Why you use it:** the project moves while you're not looking. Pull before you start working
each session and before you create a new branch, so you're building on current code instead of
yesterday's. Skipping this is the most common way people create conflicts for themselves.

---

## Ignoring files with `.gitignore`

```bash
cat .gitignore
```

`.gitignore` is a plain text file in your project that lists what Git should pretend it can't
see. One pattern per line. Anything matching it won't show up in `git status` and won't get
picked up by `git add .`.

**Why you use it:** because `git add .` means *everything*, and not everything belongs on
GitHub. Three kinds of things get ignored:

- **Secrets** — `.env` files, API keys, credentials. This is the important one.
- **Generated files** — `node_modules/`, build output. Huge, and rebuildable from your code
  with one command, so committing them is pure noise.
- **Machine junk** — `.DS_Store` on Mac, `Thumbs.db` on Windows. Yours, not the project's.

A typical `.gitignore` for the projects we'll build:

```gitignore
# Secrets — never commit these
.env
.env.local

# Dependencies — rebuilt with "npm install"
node_modules/

# Build output
dist/
.next/

# OS files
.DS_Store
Thumbs.db
```

The file itself **does** get committed. That's the point — everyone working on the project
ignores the same things.

> **This is the "never commit an API key" rule from [setup](../setup/), made real.** A key
> pushed to GitHub is public the moment it lands, and deleting it later doesn't help — it's in
> the history, and bots scan for exactly this. `.gitignore` is what stops it from happening in
> the first place. Add `.env` to it *before* you create the `.env` file, not after.

Not sure whether a file is being ignored?

```bash
git check-ignore -v .env
```

Tells you which line of which `.gitignore` is responsible. Silence means the file is **not**
ignored — worth checking before your first push on any new project.

> **The gotcha:** `.gitignore` only affects files Git isn't already tracking. If you committed
> `node_modules/` and *then* added it to `.gitignore`, Git keeps tracking it. Untrack it with
> `git rm -r --cached node_modules` and commit that. (The `--cached` part matters — it removes
> the file from Git, not from your disk.)

---

## Branches

A branch is a separate line of work. You make your changes on a branch, and the main line
(`main`) stays working the whole time. If your branch turns out badly, you throw it away and
nothing is lost.

### See your branches

```bash
git branch
```

Lists the branches in your local repo and marks the one you're currently on with a `*`.

**Why you use it:** to confirm where you are before you start committing. Committing to the
wrong branch is easy to do and annoying to untangle.

### Create a branch and switch to it

```bash
git switch -c fix/broken-nav-links
```

Creates a new branch starting from where you are, and moves you onto it in one step.

**Why you use it:** this is how you start any new piece of work — a feature, a bug fix, an
experiment. Name it after what you're doing, not after yourself or the date.

> You may see `git checkout -b` in older tutorials and answers online. It does the same thing.
> `switch` is the newer, clearer command; `checkout` does about six unrelated jobs, which is
> exactly why `switch` exists.

### Switch to an existing branch

```bash
git switch main
```

Moves you to a branch that already exists.

**Why you use it:** to get back to `main` after finishing a branch, or to hop over to someone
else's branch to look at their work. Commit or stash your changes first — Git will stop you if
switching would lose work.

---

## Pull requests

A **pull request** ("PR") proposes merging your branch into `main`. It's where code gets
reviewed, discussed, and — once approved — merged. This is the command you were trying to
remember:

```bash
gh pr create
```

Opens a pull request from your current branch, prompting you for a title and description.

**Why you use it:** on a real team, work doesn't go straight into `main`. A PR is the
checkpoint where someone else reads your change before it becomes everyone's problem. It's
also a genuinely useful record — the PR explains *why* a change was made in a way the code
never does.

Your branch has to be pushed first. The usual sequence:

```bash
git switch -c feat/add-dark-mode
# ... do the work, add, commit ...
git push -u origin feat/add-dark-mode
gh pr create
```

Then check on it:

```bash
gh pr view --web
```

Opens the pull request in your browser, where you'll find the review comments and the merge
button.

> **`gh` is the GitHub CLI — a separate tool from Git**, and it isn't in the
> [setup guide](../setup/) yet. If `gh` isn't installed, you don't need it: push your branch,
> open the repo on GitHub, and click the **Compare & pull request** button that appears at the
> top of the page. Same result, more clicking. We'll cover PRs both ways in class.

---

## When it goes wrong

It will. Git's error messages are famously unhelpful when you're new, and everyone —
including people who've used it for years — gets tangled up in it.

- **Start with `git status`.** It very often names the problem and suggests the fix.
- **Don't guess at commands you found online**, especially anything with `--force` or `reset
  --hard`. Those are the two that actually destroy work.
- **Ask.** Bring it to class. A broken repo on screen is one of the more useful things we can
  spend fifteen minutes on, and someone else in the room has the same problem.

Nothing in a committed repo is truly lost as easily as it feels like it is.
