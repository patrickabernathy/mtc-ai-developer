# CSS Selectors & Properties Cheat Sheet

The selectors and properties from Week 3, Day 2 — "Making It Look Like Something." Keep the tab
open; you're not expected to memorize any of it.

> **New to HTML?** See the [HTML tags cheat sheet](html-tags-cheat-sheet.md) first — CSS changes
> how tags *look*; it doesn't replace knowing what they *are*.

## Quick reference

**Click any selector to jump to what it targets.**

| Selector | What it targets |
|---|---|
| [`p`](#point-at-every-tag-of-a-kind) | Every `<p>` on the page. |
| [`.special`](#point-at-a-group-you-named-yourself) | Everything with `class="special"`. |
| [`#store-name`](#point-at-one-specific-thing) | The **one** thing with `id="store-name"`. |
| [`footer a`](#point-at-things-inside-other-things) | Links **inside** the footer. |
| [`h1, h2`](#say-the-same-thing-about-several-at-once) | h1s **and** h2s. |
| [`a:hover`](#point-at-a-thing-only-while-somethings-true) | Links, only while the mouse is on them. |
| [`li.special`](#the-selector-cheat-sheet-all-of-it-at-once) | List items that *also* have that class — no space. |
| [`*`](#the-selector-cheat-sheet-all-of-it-at-once) | Literally everything. Use with care. |

Almost all of CSS is one sentence, over and over: **selector { property: value; }** — *which*
things, *what* about them, *what to*. Everything else on this page supports that.

---

## Anatomy of a rule

```css
h1 { color: darkred; }
```

| Part | Name | Meaning |
|---|---|---|
| `h1` | **selector** | *Which* things this applies to. |
| `color` | **property** | *What* about them you're changing. |
| `darkred` | **value** | What you're changing it *to*. |
| `{ }` and `;` | — | Curly braces hold the rules; every line ends in a semicolon. |

Which, when, what — that's every line of CSS you'll ever write.

---

## Three places to put a style (pick the third one)

```html
<!-- 1. Inline — on the tag itself. Works, but you'll type it once per tag, forever. -->
<h1 style="color: darkred;">The Corner Store</h1>

<!-- 2. Internal — once, at the top of the file, in <head>. Better, but only for THIS page. -->
<head>
  <style>
    h1, h2, h3 { color: darkred; }
  </style>
</head>

<!-- 3. External — its own file, linked from every page. Default to this. -->
<head>
  <link rel="stylesheet" href="styles.css">
</head>
```

| Way | Use it when |
|---|---|
| **Inline** (`style="..."`) | Almost never. A one-off emergency at most. |
| **Internal** (`<style>` in `<head>`) | Almost never — one page's worth of un-shareable rules. |
| **External** (`.css` file + `<link>`) | **By default, always.** Shared across every page, cached by the browser, and content (HTML) stays separate from appearance (CSS). |

**The gotcha:** if a page suddenly looks naked — no colors, no layout — the CSS file is almost
never broken. Check the `<link>` tag first, before touching a single style. A typo in `href`, or a
missing/deleted `<link>` line, fails **silently**: no error, the page just quietly reverts to
default fonts and left-aligned everything.

```html
<link rel="stylesheet" href="styles.css">
```

`rel` says what kind of thing you're linking (a stylesheet); `href` says where it is — a filename
next door, or a full web address for something like Bootstrap. No closing tag, same family as
`<img>` and `<meta>`.

---

## Selectors

### Point at every tag of a kind

```css
p    { color: dimgray; }
li   { font-size: 18px; }
body { font-family: system-ui; }
```

Just the tag name, no punctuation. Every single one on the page — the blunt tool.

### Point at a group you named yourself

```css
.special {
  color: darkred;
  font-weight: bold;
}
```

A dot, then the `class` name. This is what `class="..."` in your HTML was for.

> **The single most common beginner bug:** leave off the dot (`special { ... }` instead of
> `.special { ... }`) and nothing happens — no error. You've just asked the browser to style a
> `<special>` tag that doesn't exist, so it shrugs and moves on. **CSS fails silently, just like
> HTML.** A rule that does nothing looks exactly like a rule you didn't write — which is why the
> inspector (right-click → Inspect) matters: it shows every rule hitting an element and crosses
> out the ones that lost.

### Point at one specific thing

```css
#store-address {
  font-size: 20px;
  color: black;
}
```

A hash, then the `id`. One thing, never reused on the page.

| | Punctuation | Reusable? |
|---|---|---|
| `.class` | dot | Yes — use it nearly always |
| `#id` | hash | No — the one banner, the one footer, the thing there's genuinely only one of |

### Point at things inside other things

```css
footer a   { color: gray; }      /* every link inside the footer */
nav a      { font-weight: bold; } /* every link inside the nav */
main ul li { line-height: 1.8; }  /* list items in lists in main */
```

A **space** means *inside*: find the first thing, then look for the second one anywhere inside it.

### Say the same thing about several at once

```css
h1, h2, h3 { color: darkred; }
```

A **comma** means *and also* — several separate rules collapsed into one line. Careful: a comma
and a space are one keystroke apart and mean opposite things.

```css
footer a   /* links INSIDE the footer */
footer, a  /* the footer AND every link on the page */
```

### Point at a thing only while something's true

```css
a       { color: navy; }
a:hover { color: darkred; }
```

A colon plus a word means "in this state." `:hover` is while the mouse is over it. There's also
`:focus`, for when someone reaches it with the Tab key instead of a mouse — style both, since not
everybody uses a mouse.

### The selector cheat sheet, all of it at once

| Selector | Targets |
|---|---|
| `p` | every `<p>` on the page |
| `.special` | everything with `class="special"` |
| `#store-name` | the one thing with `id="store-name"` |
| `footer a` | links inside the footer |
| `h1, h2` | h1s *and* h2s |
| `a:hover` | links, while the mouse is on them |
| `li.special` | list items that *also* have that class — no space |
| `*` | literally everything — use with care |

---

## When two rules disagree (the cascade)

```css
h1        { color: navy; }        /* a tag */
.headline { color: green; }       /* a class */
```

```html
<h1 class="headline" style="color: orange;">The Corner Store</h1>
```

That heading renders **orange** — the more specific rule wins.

| Specificity (highest to lowest) | Example |
|---|---|
| 1. Inline `style="..."` | beats everything — you pointed at *this one thing* |
| 2. An `#id` | there's only one, so it's nearly as specific |
| 3. A `.class` | a named group, beats a plain tag |
| 4. A tag | the broadest thing you can say — loses to all of the above |
| **Tie-break** | same specificity → **the last rule written wins** |

This is **the cascade** — the C in CSS, and the source of most "why won't this change"
frustration. It's also how you overrule Bootstrap: link your own stylesheet *after* theirs.

---

## Inheritance

```css
body { color: dimgray; font-family: system-ui; }
```

Set that on `<body>` and every paragraph, list item, and link inside it goes gray — without being
mentioned individually. That's **inheritance**.

| Inherited (text things) | NOT inherited (box things) |
|---|---|
| `color`, `font-family`, `font-size`, `line-height` | `padding`, `margin`, `border`, `background` |

Set fonts once on `body` and never again. Putting `padding` on `body` does nothing for the
paragraphs inside it — box properties don't trickle down.

---

## The box model

Every element on every page is **four boxes inside each other**, from the outside in:

```
margin  →  space outside, pushing other elements away
  border  →  the line around the element
    padding  →  space inside, around the content
      content  →  the actual text/image
```

| | Inside or outside the border? | Has a background color? |
|---|---|---|
| **padding** | Inside | Yes — makes the box bigger, pushes content away from its own edge |
| **margin** | Outside | No — always see-through, pushes *other* things away |

**The quick test:** does it have the background color? If yes, it's padding. If it's empty space
between two separate things, it's margin.

```css
.card { padding: 20px; margin: 10px; border: 1px solid gray; }
```

**The gotcha:** `width: 300px` with `padding: 20px` and `border: 5px` renders **350px** wide by
default — padding and border are added on top of the width. Fix it once, globally:

```css
* {
  box-sizing: border-box;
}
```

Now `width: 300px` means the whole box is 300px, padding and border included. Nearly every real
stylesheet on the internet (including Bootstrap's) starts with this line.

---

## Color

| Format | Example | Notes |
|---|---|---|
| Name | `darkred` | Easiest; ~140 of them |
| Hex | `#A32C1E` | What you'll see everywhere — two characters each for red, green, blue |
| `rgb(...)` | `rgb(163, 44, 30)` | Same color, spelled as red/green/blue numbers |
| `hsl(...)` | `hsl(6, 69%, 38%)` | Hue, saturation, lightness |

You don't invent hex codes — pick them. VS Code shows a color picker if you click the little
swatch next to one.

---

## Type and text

```css
body {
  font-family: system-ui, sans-serif;  /* which typeface */
  font-size: 18px;                      /* how big */
  line-height: 1.6;                     /* gap between lines */
  color: #222;                          /* not pure black */
}
```

`line-height: 1.6` does more for readability than any other single line you can write — the
default is cramped. Listing two typefaces with a comma means "try the first, fall back to the
second if the machine doesn't have it."

| Property | Values | Notes |
|---|---|---|
| `text-align` | `left`, `center`, `right` | Center headings, almost never paragraphs — centered body text is harder to read |
| `text-decoration` | `none`, `underline` | `none` removes a link's underline — but an underline-free, color-free link is a link nobody can find |
| `text-transform` | `uppercase` | Shouts without retyping in caps |
| `font-weight` | `bold`, or `400`/`700` | `400` normal, `700` bold |

---

## Backgrounds, borders, and shadows

```css
.card {
  background-color: #F6EEDD;
  padding: 1rem;                          /* background covers padding, never margin */
  border: 2px solid #8F6113;              /* thickness, style, color */
  border-radius: 8px;                     /* rounded corners */
  box-shadow: 0 2px 8px rgba(0, 0, 0, 0.15);
}
```

- `border`'s three values are always thickness, style, color, in that order — `solid` is almost
  always what you want; `dashed`/`dotted` rarely are.
- `border-radius` is doing more work in modern web design than almost anything else here.
- `box-shadow`'s four values: how far right, how far down, how blurred, and the color (the last
  number in `rgba(...)` is how see-through it is). Subtle beats dramatic — a shadow you notice is
  too strong.
- Skip the padding on a colored box and the text jams straight against the edge — that's the
  padding test from the box model, seen in reverse.

---

## Units — which to reach for

| Unit | Meaning | Use it for |
|---|---|---|
| `px` | Exact pixels | Borders, small spacing — predictable, but ignores the reader's font-size setting |
| `rem` | Multiples of the page's base font size | **Type.** Grows if someone's set a bigger default text size. |
| `em` | Multiples of *this element's* size | Handy inside one component, confusing once nested |
| `%` | A share of the parent | Mostly widths |

---

## `display` — overriding block vs. inline

| Value | Behavior |
|---|---|
| `block` | Takes the whole line — what `<p>`/`<div>` already do |
| `inline` | Sits in the sentence — what `<a>`/`<span>` already do |
| `inline-block` | Sits in the line, but can take a width/height/padding — best of both |
| `none` | Gone. Not hidden — not drawn at all, no space reserved, and invisible to screen readers too |

Classic use — turning a plain list into a horizontal nav bar without lying about what it is (a
screen reader still hears "list of links"):

```css
nav ul { list-style: none; padding: 0; }
nav li { display: inline-block; margin-right: 1rem; }
```

---

## Comments

```css
/* Store colors — agreed with Ray, 12 Aug */
h1, h2 { color: darkred; }

/* .special { color: green; }   turned off, didn't like it */
```

Different marks from HTML (`/*` `*/`, not `<!-- -->`), same two jobs: leave yourself a note, or
switch a rule off without deleting it. Commenting a rule out and refreshing to see if a problem
goes away is a real, cheap debugging move.

---

## Someone else's stylesheet: Bootstrap & Font Awesome

```html
<link rel="stylesheet"
  href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.3/dist/css/bootstrap.min.css">
<link rel="stylesheet" href="styles.css">  <!-- yours goes AFTER, so it can win ties -->
```

Bootstrap is just a very big `styles.css`, written by other people and free to use. You bring it in
with the same `<link>` tag as your own stylesheet — the only difference is `href` is a web address
(a **CDN**) instead of a filename next door. You write *their* class names on your tags; they've
already written the rules:

```html
<button class="btn btn-primary">Order</button>
<div class="container"> ... </div>
<p class="text-center">Corner of Main and Third.</p>
```

Font Awesome is the same trick for icons — link their stylesheet, then wear their class names on
an empty tag:

```html
<i class="fa-solid fa-mug-hot"></i> Coffee
```

**The trade:** a working, accessible, responsive result in minutes — at the cost of class-name
soup (`class="btn btn-primary btn-lg px-4 me-2"`) and debugging a file you've never read. A tool
that saves you time also hides what it's doing.
