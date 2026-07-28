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
  <a href="#5-ai-assistant-account"><img src="../resources/images/anthropic.svg" alt="Anthropic" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#6-claude-code-cli"><img src="../resources/images/claude.svg" alt="Claude" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#vercel"><img src="../resources/images/vercel.svg" alt="Vercel" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#neon"><img src="../resources/images/neon.svg" alt="Neon" width="48" height="48"></a>
  &nbsp;&nbsp;&nbsp;
  <a href="#context7"><img src="../resources/images/context7.png" alt="Context7" width="48" height="48"></a>
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
> link you've shared.

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

Node.js is a JavaScript runtime used by many modern dev tools, MCP servers, and deployment
CLIs we'll use during the program. You need version **18 or higher**.

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

> **Note:** Node.js is **not** needed to install Claude Code (Step 6 uses a native
> installer). You'll use Node.js for running MCP servers, optional CLI tools like Vercel,
> and back-end work later in the program.

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
3. Install the **Claude Code extension** (optional but recommended):
   - Open Extensions (`Ctrl+Shift+X` on Windows, `Cmd+Shift+X` on Mac)
   - Search for "Claude Code"
   - Click **Install**

**Account required?** No account needed, though you can optionally sign in with GitHub for
settings sync.

---

## 5. AI Assistant Account

We use an AI coding assistant throughout the program — to write, debug, and optimize code,
and to build judgment about when to trust it and when not to.

> ### ⚠️ Do not pay for anything yet — _TBD_
>
> **Which assistant and which plan the class will standardize on is not finalized.** Your
> instructor will confirm the provider, the plan, and any cost in class before you are asked
> to sign up for a paid tier. If you are reading ahead: create a free account if you like,
> but hold off on a subscription until that call is made.
>
> _Owner: instructor, to confirm with the class._

The instructions below cover Anthropic's Claude, which is the assumed default in these
setup notes. Adjust if the class lands somewhere else.

**Sign up (free account):** [https://claude.ai](https://claude.ai)

### Why the plan question matters

Agentic coding tools consume a lot of tokens. On pay-as-you-go API pricing, a heavy hands-on
session can add up quickly, which is why flat-rate subscription plans are usually the better
fit for a class. That tradeoff is exactly what's being worked out — hence the hold above.

### If you're using an API key instead

1. Go to the [Anthropic Console](https://console.anthropic.com) and create an account
2. Add a payment method — API usage is pay-as-you-go
3. Navigate to **API Keys** and create a new key
4. Copy your API key and save it somewhere safe (you won't be able to see it again)
5. Set it as an environment variable in your terminal:
   - **Mac/Linux:**
     ```bash
     export ANTHROPIC_API_KEY="sk-ant-..."
     ```
   - **Windows (PowerShell):**
     ```powershell
     $env:ANTHROPIC_API_KEY="sk-ant-..."
     ```

> **Tip:** To make this permanent, add the export line to your shell profile (`~/.bashrc`,
> `~/.zshrc`, or Windows environment variables).

> **Never commit an API key to GitHub.** We'll cover how to keep secrets out of a repo, but
> the short version: keys go in environment variables or a `.env` file that Git ignores —
> never typed directly into code you push.

---

## 6. Claude Code (CLI)

Claude Code is the command-line AI coding tool from Anthropic.

**Docs:** [https://docs.anthropic.com/en/docs/claude-code](https://docs.anthropic.com/en/docs/claude-code)

### Setup steps

1. Install Claude Code using the native installer (no dependencies required):
   - **Mac/Linux:**
     ```bash
     curl -fsSL https://claude.ai/install.sh | bash
     ```
   - **Windows (PowerShell):**
     ```powershell
     irm https://claude.ai/install.ps1 | iex
     ```
2. **Restart your terminal** after installing
3. Verify the install:
   ```bash
   claude --version
   ```
4. Launch it for the first time:
   ```bash
   claude
   ```
5. On first run, it will prompt you to authenticate — follow the on-screen instructions

> **Note:** The native installer requires no dependencies (no Node.js, no npm), handles
> updates automatically, and is the recommended installation method from Anthropic.

**Account required?** Yes — uses your account from Step 5. See the _TBD_ note there before
paying for a plan.

---

## 7. GitHub CLI (gh)

The GitHub CLI lets you create repos, pull requests, and more from your terminal.

**Download:** [https://cli.github.com](https://cli.github.com)

### Setup steps

1. Install using the instructions for your OS on the download page, or:
   - **Mac:** `brew install gh`
   - **Windows:** `winget install GitHub.cli`
   - **Linux:** See [install instructions](https://github.com/cli/cli/blob/trunk/docs/install_linux.md)
2. Authenticate with your GitHub account:
   ```bash
   gh auth login
   ```
   Choose **GitHub.com**, **HTTPS**, and **Login with a web browser** when prompted
3. Verify:
   ```bash
   gh auth status
   ```

**Account required?** Yes — uses your GitHub account from Step 1.

---

## Checklist

Once you've worked through the sections above, you should be able to run all of these
without errors:

```bash
git --version
node --version
npm --version
claude --version
gh auth status
code --version
```

If any of these fail, revisit the corresponding section — and if it still fails, bring it to
class. Setup problems are normal, they are not a reflection on you, and debugging one in
front of the group teaches everybody something.

---

## Bonus Setup (Optional)

These are **not needed early on**. We get to them later in the program, and you can safely
skip this section for now.

### Vercel

A platform for deploying web apps instantly. Great for shipping what you build.

**Sign up:** [https://vercel.com/signup](https://vercel.com/signup)

1. Sign up with your **GitHub account** (recommended — links your repos automatically)
2. Free tier is generous and covers everything you'd need
3. Optionally install the CLI:
   ```bash
   npm install -g vercel
   ```

### Neon

A serverless Postgres database. Useful once we start building back-end features that store
real data.

**Sign up:** [https://neon.tech](https://neon.tech)

1. Sign up with your **GitHub account** (easiest) or email
2. Create a free project — you'll get a connection string
3. Free tier includes 1 project with 512 MB storage — plenty for class work

### Context7

Context7 is an MCP server that pulls **up-to-date, version-specific documentation** directly
into your Claude Code prompts. Instead of Claude relying on its training data (which may be
months old), Context7 fetches the current docs for any library — React, Next.js, Prisma,
Tailwind, you name it. This is a game-changer for getting accurate, working code.

**Dashboard:** [https://context7.com/dashboard](https://context7.com/dashboard)

#### The easy way: let Claude Code set it up for you

The fastest way to add Context7 is to just ask Claude Code to do it:

1. Open your terminal and launch Claude Code:
   ```bash
   claude
   ```
2. Then simply type:
   ```
   Add Context7 as an MCP server
   ```
3. Claude Code will handle the configuration for you

#### Manual setup (if you prefer)

Run this one command in your terminal — it handles authentication and installs Context7
automatically:

```bash
npx ctx7 setup --claude
```

If you're on a remote/headless server (no browser), use your API key directly:

```bash
npx ctx7 setup --claude --api-key YOUR_API_KEY
```

#### Get an API key for extended usage

Context7 works without an API key, but you'll hit rate limits quickly during a long hands-on
session. A free API key removes that bottleneck:

1. Go to [context7.com/dashboard](https://context7.com/dashboard)
2. Sign up / log in
3. Create a new API key
4. Your key will unlock higher rate limits for sustained usage

#### Using Context7 in Claude Code

Once set up, Context7 activates automatically when you ask about libraries. You can also
call it explicitly:

```
use context7 to show me how to set up proxy in Next.js 16
```

---

Questions, or stuck on a step? Bring it to the next class session, or reach out ahead of
time so we can get you sorted before it costs you class time.

---

_Adapted, with thanks, from the setup guide in
[chriskehayias/ContextEngineering](https://github.com/chriskehayias/ContextEngineering)._
