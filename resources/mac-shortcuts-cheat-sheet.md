# Mac Shortcut Cheat Sheet

<p align="center">
  <img src="images/apple.svg" alt="Apple" width="48" height="48">
  &nbsp;&nbsp;&nbsp;
  <img src="images/vscode.png" alt="VS Code" width="48" height="48">
</p>

Keyboard shortcuts are not a productivity trick — they're how you stop losing your train of
thought. Every trip to the trackpad costs you a second and a little bit of focus, and you make
that trip a few hundred times a night. Keep this open; you're not expected to memorize it.

> **On Windows?** See the [Windows shortcut cheat sheet](windows-shortcuts-cheat-sheet.md).
> Most of this page works there with **`Ctrl`** where this page says `Cmd`.

## If you learn only five

Start here. These five come up constantly in class, and the last one saves people the most
frustration by a wide margin.

| Shortcut | What it does |
|---|---|
| `Cmd` + `Space` | Spotlight — then type an app name and press `Return` |
| `Cmd` + `Tab` | Switch between open apps |
| `Cmd` + `Shift` + `4` | Screenshot a region — perfect for asking for help |
| `Ctrl` + `` ` `` | Open/close the terminal in VS Code |
| `Cmd` + `Shift` + `R` | Hard refresh the browser — *load my actual changes* |

**Click any section to jump to it:**
[Modifier keys](#the-modifier-keys) ·
[Spotlight and the system](#spotlight-and-the-system) ·
[Windows and Spaces](#managing-windows-and-spaces) ·
[Text editing](#text-editing-everywhere) ·
[Finder](#finder) ·
[Browser](#the-browser) ·
[Terminal](#the-terminal) ·
[VS Code](#vs-code) ·
[Windows differences](#if-youre-coming-from-windows)

---

## The modifier keys

Mac shortcuts are written with symbols, and menus show them that way — so it's worth five
seconds to learn which is which. On the bottom row, left to right: `fn`, `Ctrl`, `Option`,
`Cmd`, then the space bar.

| Symbol | Key | Where it is |
|---|---|---|
| `⌘` | **Command** (`Cmd`) | Either side of the space bar — your main shortcut key |
| `⌥` | **Option** (`Alt`) | Between `Ctrl` and `Cmd` |
| `⇧` | **Shift** | Where you'd expect |
| `⌃` | **Control** (`Ctrl`) | Bottom-left corner — used far less than on Windows |
| `🌐` / `fn` | **Function / Globe** | Very bottom-left, below `Ctrl` |

**`Cmd` is not `Ctrl`.** They sit in different places and do different jobs. `Cmd` is the
everyday shortcut key — copy, paste, save, quit. `Ctrl` on a Mac is mostly reserved for
Mission Control and the terminal. When a tutorial written for Windows says `Ctrl` + `C`, on a
Mac that's almost always `Cmd` + `C` — *except in a terminal*, which is the one exception and
the one that trips everybody up.

**The function keys need `fn`.** `F1` through `F12` control brightness and volume by default,
so a shortcut like VS Code's `F2` (rename) is actually `fn` + `F2`. If that annoys you, turn it
off permanently: **System Settings → Keyboard → Keyboard Shortcuts → Function Keys**, then
switch on *"Use F1, F2, etc. keys as standard function keys."*

---

## Spotlight and the system

`Cmd` + `Space` is the single most useful key combination on a Mac. It opens Spotlight, and you
**just start typing** — an app name, a file name, even a calculation — instead of hunting
through the Applications folder or the Dock.

| Shortcut | What it does |
|---|---|
| `Cmd` + `Space` | Spotlight — type an app or file name, press `Return` |
| `Cmd` + `Shift` + `3` | Screenshot the whole screen |
| `Cmd` + `Shift` + `4` | Screenshot a region you drag over |
| `Cmd` + `Shift` + `5` | Screenshot toolbar — window capture and screen recording |
| `Ctrl` + `Cmd` + `Space` | Emoji and symbol picker |
| `Ctrl` + `Cmd` + `Q` | Lock your screen |
| `Cmd` + `Option` + `Esc` | Force Quit — for an app that's genuinely frozen |
| `Cmd` + `,` | Open the current app's settings — works in nearly every app |
| `Cmd` + `Q` | **Quit** the app entirely |

**Screenshots are how you ask for help.** `Cmd` + `Shift` + `4` gives you crosshairs; drag a
box and the image lands on your **Desktop** as a file. Add `Ctrl` to any of the screenshot
shortcuts — `Ctrl` + `Cmd` + `Shift` + `4` — and it goes to your clipboard instead, ready to
paste straight into Teams, an email, or an AI assistant.

When you're stuck, screenshot the *whole* window — code, terminal, and error together. That
gets you a useful answer far faster than a cropped shot of just the red text.

> **`Cmd` + `Shift` + `4`, then press `Space`** turns the crosshairs into a camera and captures
> one whole window, cleanly, with its shadow. It's the nicest-looking screenshot on the
> platform and nobody finds it by accident.

**No clipboard history, out of the box.** Windows has `Win` + `V`; macOS has nothing
equivalent, which means copying a second thing destroys the first. If that bites you often,
[Maccy](https://maccy.app) (free) or Raycast adds it. Not required for class — just know the
limitation is real and not your imagination.

---

## Managing windows and Spaces

You'll routinely have an editor, a browser, and a terminal fighting over the same screen. Two
things to know up front: `Cmd` + `Tab` switches **apps**, not windows, and closing a window
does *not* quit the app.

| Shortcut | What it does |
|---|---|
| `Cmd` + `Tab` | Switch apps — hold `Cmd` and tap `Tab` to go further back |
| `Cmd` + `` ` `` | Cycle windows **within** the current app |
| `Cmd` + `W` | Close the window (the app keeps running) |
| `Cmd` + `Q` | Quit the app |
| `Cmd` + `M` | Minimize to the Dock |
| `Cmd` + `H` | Hide the app (`Cmd` + `Option` + `H` hides all the others) |
| `Ctrl` + `Up` | Mission Control — every window, laid out |
| `Ctrl` + `Down` | Every window of the *current* app |
| `Ctrl` + `Left` / `Right` | Switch between Spaces (virtual desktops) |
| `fn` + `Ctrl` + `Left` / `Right` | Tile the window to that half of the screen *(macOS 15+)* |
| `fn` + `Ctrl` + `F` | Fill the screen without going full-screen *(macOS 15+)* |

**Why tiling matters:** VS Code on one half and your browser on the other gives you code on one
side and the running page on the other. That side-by-side view is most of front-end development
— you change code, you look at the result, you repeat.

macOS only grew real keyboard tiling in **Sequoia (macOS 15)**. On any version you can drag a
window to a screen edge and it'll offer to tile, or use the **Window** menu → *Move & Resize*.
If you're on something older — or you want Windows-grade snapping — [Rectangle](https://rectangleapp.com)
is free and gives you `Ctrl` + `Option` + `Left`/`Right`.

**Spaces** are a second (and third) monitor you don't have to buy. Open Mission Control
(`Ctrl` + `Up`), click **+** in the top right, and put class work on one Space and everything
else on another. `Ctrl` + `Left`/`Right` moves between them. Your windows aren't closed, just
out of the way.

> **The green button lies.** Clicking it goes *full-screen*, which hides your menu bar and
> shunts the window into its own Space — usually not what you wanted. **`Option`-click** it
> instead to just maximize in place. Double-clicking the title bar does the same thing.

---

## Text editing, everywhere

These work in your editor, your browser, Pages, chat boxes — anywhere you can type. If you know
only the copy/paste three, the ones below the divider are where the real time goes.

| Shortcut | What it does |
|---|---|
| `Cmd` + `C` / `X` / `V` | Copy / cut / paste |
| `Cmd` + `Z` | Undo (`Cmd` + `Shift` + `Z` to redo) |
| `Cmd` + `A` | Select all |
| `Cmd` + `S` | Save |
| `Cmd` + `F` | Find on this page or in this file |
| | |
| `Option` + `Left` / `Right` | Move the cursor one **word** at a time |
| `Cmd` + `Left` / `Right` | Jump to the start / end of the line |
| `Cmd` + `Up` / `Down` | Jump to the top / bottom of the document |
| `Shift` + any of the above | Do the same move, but **select** as you go |
| `Option` + `Delete` | Delete the word behind the cursor |
| `fn` + `Delete` | Delete forward (the key Windows calls `Delete`) |
| `Cmd` + `Shift` + `Option` + `V` | Paste as plain text (drops formatting) |

**Why you use it:** holding `Shift` turns any movement into a selection. `Shift` + `Cmd` +
`Right` selects to the end of the line; `Shift` + `Option` + `Left` grabs the previous word.
Once that clicks, you stop reaching for the trackpad to select text, which is a surprising
share of the mousing you currently do.

> **There is no `Home` or `End` key** on a Mac keyboard — `Cmd` + `Left`/`Right` is how you get
> to the start and end of a line. On a full-size keyboard the physical `Home`/`End` keys work
> too, but they behave differently app to app, so learn the `Cmd` version.

> The paste-as-plain-text combo is a four-finger stretch and it's worth it. Use it when pasting
> into a doc, a form, or a chat — it strips the fonts, colors, and stray formatting that come
> along with copied text.

---

## Finder

| Shortcut | What it does |
|---|---|
| `Cmd` + `Shift` + `N` | New folder |
| `Return` | **Rename** the selected file (not `F2`) |
| `Space` | Quick Look — preview the file without opening it |
| `Cmd` + `Down` | Open the selected file or folder |
| `Cmd` + `Up` | Go up to the parent folder |
| `Cmd` + `[` / `]` | Back / forward, like a browser |
| `Cmd` + `Shift` + `G` | **Go to folder** — type a path like `~/projects` |
| `Cmd` + `Shift` + `.` | Show hidden files (the dotfiles, including `.git`) |
| `Cmd` + `Delete` | Move to Trash |
| `Cmd` + `Option` + `V` | **Move** here (after a `Cmd` + `C`) — Finder has no cut |
| `Cmd` + `Option` + `C` | Copy the full path of the selected file |

**Two Finder tricks worth more than the shortcuts:**

**Turn on file extensions.** **Finder → Settings → Advanced → Show all filename extensions.**
macOS hides them by default, which means `styles.css` and `styles.css.txt` look identical — and
a file that silently isn't what you think it is will cost you an evening. Turn this on once, on
day one. While you're there, tick **Show Path Bar** in the **View** menu so you can always see
where you actually are.

**Open a terminal in the current folder.** Right-click a folder → **Services → New Terminal at
Folder**. If you don't see it, switch it on in **System Settings → Keyboard → Keyboard
Shortcuts → Services → Files and Folders**. The lazier version works everywhere: type `cd `
(with the space) in a terminal, then **drag the folder in from Finder** — macOS pastes the path
for you. Both save a lot of typing when you're not sure of the exact path.

---

## The browser

You'll live in a browser as much as in your editor. These work in Chrome and Edge; Safari and
Firefox are nearly identical.

| Shortcut | What it does |
|---|---|
| `Cmd` + `T` / `W` | New tab / close tab |
| `Cmd` + `Shift` + `T` | **Reopen the tab you just closed** (repeat to go further back) |
| `Cmd` + `Option` + `Right` | Next tab (`Cmd` + `Option` + `Left` for previous) |
| `Cmd` + `L` | Jump to the address bar and select it — then just type |
| `Cmd` + `R` | Refresh |
| `Cmd` + `Shift` + `R` | **Hard refresh** — reload ignoring the cache |
| `Cmd` + `Option` + `I` | Open DevTools (`Cmd` + `Option` + `J` goes straight to the console) |
| `Cmd` + `Shift` + `N` | New incognito / private window |
| `Cmd` + `+` / `-` / `0` | Zoom in / out / reset |

**Why `Cmd` + `Shift` + `R` matters:** browsers cache your CSS and JavaScript to make pages load
fast. That's helpful right up until you change a file, refresh, and see the *old* version — at
which point you assume your code is broken when it's fine. Hard refresh is the first thing to
try when a change doesn't show up. **DevTools and hard refresh will come up in class every
single week.**

> **Use Chrome for class.** Safari's developer tools are hidden until you enable them
> (**Safari → Settings → Advanced → Show features for web developers**), and its DevTools differ
> enough from Chrome's that following along gets harder than it needs to be.

---

## The terminal

Applies to Terminal, iTerm2, and the terminal inside VS Code. Your Mac's shell is **zsh**, and
these line-editing keys are the same in all of them.

| Shortcut | What it does |
|---|---|
| `Ctrl` + `C` | **Stop** the command that's currently running |
| `Up` / `Down` | Walk back through commands you've already run |
| `Tab` | Auto-complete a file, folder, or command name |
| `Ctrl` + `R` | Search your command history by typing part of it |
| `Ctrl` + `L` | Clear the screen (`Cmd` + `K` clears the scrollback too) |
| `Ctrl` + `A` / `E` | Jump to the start / end of the line |
| `Ctrl` + `U` | Delete the whole line and start over |
| `Ctrl` + `W` | Delete the word behind the cursor |
| `Cmd` + `C` / `V` | Copy / paste — normal Mac behavior here |
| `Cmd` + `T` / `N` | New tab / new window |

> **The gotcha that gets everyone:** in a terminal, `Ctrl` + `C` means **cancel**, not copy —
> and it's `Ctrl`, not `Cmd`, on every platform including this one. If a server is running and
> your prompt won't come back, that's not frozen — it's working as designed. `Ctrl` + `C` stops
> it and gives you the prompt back. To actually copy, use `Cmd` + `C` as usual.

**Why `Up` and `Tab` matter more than they look:** most terminal work is re-running a command
you ran two minutes ago, and `Up` a few times beats retyping it — with fewer typos. `Tab`
completes long folder names for you, which is also how you find out you're in the wrong
directory: if `Tab` won't complete the name, the thing you're typing isn't there.

> `Ctrl` + `A` and `Ctrl` + `E` are muscle memory worth building — arrow-keying across a long
> command is the slowest way to fix a typo at the front of it. You can also **`Option`-click**
> anywhere in the line to drop the cursor right there.

---

## VS Code

VS Code has hundreds of shortcuts. These are the ones worth knowing in week one; you'll pick up
more as you need them.

| Shortcut | What it does |
|---|---|
| `Ctrl` + `` ` `` | Toggle the built-in terminal — **`Ctrl`, not `Cmd`** |
| `Cmd` + `P` | Quick open — type part of a filename and hit `Return` |
| `Cmd` + `Shift` + `P` | **Command Palette** — search every command by name |
| `Cmd` + `B` | Show/hide the sidebar |
| `Cmd` + `/` | Comment or uncomment the selected lines |
| `Option` + `Up` / `Down` | Move the current line up or down |
| `Shift` + `Option` + `Up` / `Down` | Duplicate the current line |
| `Cmd` + `D` | Select the next occurrence of what's selected — edit both at once |
| `Cmd` + `Shift` + `F` | Search across every file in the project |
| `Shift` + `Option` + `F` | Auto-format the file |
| `fn` + `F2` | Rename a variable **everywhere** it's used |
| `Cmd` + `K` `Cmd` + `S` | Open the full keyboard shortcut list |

**The two that matter most:**

**`Cmd` + `Shift` + `P`** is the answer to "how do I do X in VS Code?" Open it, type roughly
what you want, and the command shows up — along with its keyboard shortcut, which is how you
learn the rest of them over time. If you remember one shortcut from this section, this is it.

**`Cmd` + `P`** finds a file by name in a project with hundreds of them, without touching the
file tree. Once a project outgrows a handful of files, this is how you navigate.

> `Cmd` + `K` `Cmd` + `S` is a **chord** — press `Cmd` + `K`, let go, then press `Cmd` + `S`.
> VS Code uses several of these. It's also the place to change any shortcut you don't like.

---

## If you're coming from Windows

Most Windows shortcuts work here if you swap **`Ctrl` → `Cmd`** (`Cmd` + `C`, `Cmd` + `S`,
`Cmd` + `P`, and so on). The rest:

| Windows | Mac |
|---|---|
| `Alt` + `Tab` | `Cmd` + `Tab` (apps) · `Cmd` + `` ` `` (windows in one app) |
| `Win` (Start menu) | `Cmd` + `Space` (Spotlight) |
| `Win` + `Left` / `Right` | `fn` + `Ctrl` + `Left` / `Right`, or Rectangle |
| `Win` + `Shift` + `S` | `Cmd` + `Shift` + `4` |
| `Win` + `E` (File Explorer) | `Cmd` + `Space`, type "Finder" |
| `Win` + `V` (clipboard history) | Nothing built in — Maccy or Raycast |
| `F2` (rename a file) | `Return` |
| `F12` (DevTools) | `Cmd` + `Option` + `I` |
| `Home` / `End` | `Cmd` + `Left` / `Right` |
| `Ctrl` + `Left` / `Right` (by word) | `Option` + `Left` / `Right` |
| `Ctrl` + `Backspace` (delete word) | `Option` + `Delete` |
| `Delete` (forward delete) | `fn` + `Delete` |
| `Alt` + `F4` | `Cmd` + `Q` (quit) or `Cmd` + `W` (close window) |
| `Ctrl` + `Alt` + `Delete` | `Cmd` + `Option` + `Esc` (Force Quit) |

`Ctrl` + `C` in a terminal is `Ctrl` + `C` on a Mac too — that one is `Ctrl`, not `Cmd`, on
every platform.

---

## How to actually learn these

Don't try to memorize the page. Pick **two** shortcuts you'd genuinely use, and force yourself
to use them for a week — even when reaching for the trackpad would be faster in the moment.
That week is the whole cost; after it, they're automatic and free forever.

When you catch yourself doing something repetitive with the trackpad, that's the signal to come
back here and look for the shortcut. That's the habit worth building — not the list.
