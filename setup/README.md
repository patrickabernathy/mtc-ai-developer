# Setup: Tools and Accounts

<p align="center">
  <a href="#1-github-account"><img src="../resources/images/github.svg" alt="GitHub" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#2-git"><img src="../resources/images/git.svg" alt="Git" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#3-nodejs"><img src="../resources/images/nodejs.svg" alt="Node.js" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#4-visual-studio-code-vs-code"><img src="../resources/images/vscode.png" alt="VS Code" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#5-vercel"><img src="../resources/images/vercel.svg" alt="Vercel" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#6-neon"><img src="../resources/images/neon.svg" alt="Neon" width="48" height="48"></a>
</p>

This is the toolkit we'll use in class. Work through the sections in order — budget about
30–60 minutes for the whole thing.

**You do not need all of this on night one.** We install tools together, in class, when we
first need them. This page exists so you can get ahead, catch up if you miss a night, or
re-install after a laptop change. Nothing here is a test, and nothing here has to be
finished alone — if a step fails, bring it to class and we'll fix it together.

**What you need:** a laptop you can install software on, with an account that has
administrator rights. Windows, Mac, and Linux are all fine — instructions for each are
below.

**Everything on this page is free.** Every account below has a free tier that covers what we
do in class. You will not be asked to enter a credit card for any of them.

---

## 1. GitHub Account

GitHub is where code lives and where you'll push your work. Create this first — you'll use
the same email when configuring Git in the next step.

**Sign up:** [https://github.com/signup](https://github.com/signup)

> **Important: This is YOUR personal account.**
>
> Your GitHub account is tied to you as an individual — not your employer or organization.
> It follows you from job to job and is how you get invited to collaborate on projects
> outside your current workplace. If your organization has a GitHub Organization account,
> you would be invited to join it using your personal GitHub account.
>
> **Do not create a GitHub account on behalf of your organization here.** Create a personal
> account using your own email address.

### Setup steps

1. Go to the signup page and create a free account
2. Verify your email address
3. That's it — free accounts have everything you need

> **Pick a username you'd be comfortable putting on a résumé.** By the end of this program
> your GitHub profile is part of your portfolio, and renaming an account later breaks every
> link you've shared. This account also signs you in to Vercel and Neon below, so it's worth
> a minute of thought.

---

## 2. Git

Git is the version control tool we use to download and share code. You'll use it throughout
the program.

**Download:** [https://git-scm.com/downloads](https://git-scm.com/downloads)

### Setup steps

1. Go to the download page and choose your operating system (Windows, Mac, or Linux)
2. Run the installer — the default options are fine for everything
3. Open a terminal (Terminal on Mac, PowerShell or Git Bash on Windows) and verify it works:
   ```bash
   git --version
   ```
   You should see something like `git version 2.44.0`
4. Configure your name and email — **use the same email you signed up with on GitHub**:
   ```bash
   git config --global user.name "Your Name"
   git config --global user.email "you@example.com"
   ```

**Account required?** No account needed for Git itself — it uses your GitHub account from
Step 1.

> **Never opened a terminal before?** That's expected, and it's not a prerequisite. We cover
> the terminal from zero in class. If you'd rather wait and do this step with the group,
> that is a completely reasonable choice.

---

## 3. Node.js

Node.js is a JavaScript runtime — it lets JavaScript run on your machine instead of just in
a browser. Modern development tooling is built on it. You need version **18 or higher**.

**Download:** [https://nodejs.org](https://nodejs.org) (choose the **LTS** version)

### Setup steps

1. Download the LTS installer for your operating system
2. Run the installer — accept all defaults
3. **Restart your terminal** after installing (important!)
4. Verify it works:
   ```bash
   node --version
   npm --version
   ```
   You should see version numbers for both (e.g., `v22.x.x` and `10.x.x`)

**Account required?** No.

---

## 4. Visual Studio Code (VS Code)

VS Code is the code editor we'll use in class. It's free, lightweight, and works on all
platforms.

**Download:** [https://code.visualstudio.com](https://code.visualstudio.com)

### Setup steps

1. Download and install for your operating system
2. Open VS Code and familiarize yourself with the basics:
   - **File Explorer** (left sidebar) — where your project files live
   - **Terminal** (`` Ctrl+` `` or `View > Terminal`) — the built-in command line
   - **Extensions** (left sidebar, square icon) — for adding features

**Account required?** No account needed, though you can optionally sign in with GitHub for
settings sync.

> We'll add extensions together in class as we need them, including one for whichever AI
> assistant we settle on. Nothing to install here beyond the editor itself.

---

## 5. Vercel

Vercel is where we'll deploy what you build, so your work has a real URL you can send to
someone. Sign up now — we'll use it once we have something worth putting online.

**Sign up:** [https://vercel.com/signup](https://vercel.com/signup)

### Setup steps

1. Sign up with your **GitHub account** from Step 1 — this links your repos automatically
   and saves a lot of friction later
2. Choose the **Hobby** (free) plan when prompted
3. That's it — no deployment to create yet

**Account required?** Yes. The free tier covers everything we do in class.

---

## 6. Neon

Neon is a serverless Postgres database — where your applications will store real data once
we get into back-end work.

**Sign up:** [https://neon.tech](https://neon.tech)

### Setup steps

1. Sign up with your **GitHub account** from Step 1 (easiest) or your email
2. That's it — we'll create your first database together in class

**Account required?** Yes. The free tier includes plenty of room for class work.

---

## 7. AI Assistant

**An AI coding assistant is required for this program.** Using AI to write, debug, and
optimize code is not a side topic here — it runs through every part of the course, along
with the judgment to know when to trust what it gives you and when to push back.

> ### Which one — and don't pay for anything yet _(TBD)_
>
> **The specific tool and plan the class will standardize on is not finalized.** Your
> instructor will confirm the choice in class before you're asked to sign up for anything
> paid.
>
> If you want to get a head start, create a **free** account with any of the major
> assistants and start getting a feel for it. That time isn't wasted — the skills carry
> across tools. Just hold off on a subscription until the call is made.
>
> _Owner: instructor, to confirm with the class._

### If you already have one

Great — keep using it. If you already pay for an AI assistant, don't add a second
subscription on our account. Bring what you have to class and we'll work with it.

### One rule that applies no matter which tool

**Never commit an API key or credential to GitHub.** If your tool uses an API key, it goes
in an environment variable or a `.env` file that Git ignores — never typed directly into
code you push. We'll cover how to keep secrets out of a repo, but the habit starts now.

---

## Checklist

Once you've worked through the sections above, you should be able to run all of these in a
terminal without errors:

```bash
git --version
node --version
npm --version
code --version
```

And you should be able to sign in to all four of these in a browser:

- [ ] GitHub
- [ ] Vercel
- [ ] Neon
- [ ] An AI assistant (free account is fine for now)

If any of these fail, revisit the corresponding section — and if it still fails, bring it to
class. Setup problems are normal, they are not a reflection on you, and debugging one in
front of the group teaches everybody something.

---

Questions, or stuck on a step? Bring it to the next class session, or reach out ahead of
time so we can get you sorted before it costs you class time.

---

_Adapted, with thanks, from the setup guide in
[chriskehayias/ContextEngineering](https://github.com/chriskehayias/ContextEngineering)._
