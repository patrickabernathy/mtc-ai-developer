# HTML Tags Cheat Sheet

The tags from Week 3, Day 1 — "Everything Is a Tag." Keep the tab open; you're not expected to
memorize any of it.

## Quick reference

**Click any tag to jump to what it does and why you'd use it.**

| Tag | What it does |
|---|---|
| [`<!DOCTYPE html>`](#the-skeleton-every-page-starts-with) | "This is a modern web page." Always the first line. |
| [`<html lang="en">`](#the-skeleton-every-page-starts-with) | Wraps everything; `lang` tells screen readers what language it's in. |
| [`<head>`](#the-skeleton-every-page-starts-with) | Things the browser needs to know. The visitor never sees it. |
| [`<meta charset="utf-8">`](#the-skeleton-every-page-starts-with) | Which alphabet the file is written in. |
| [`<title>`](#the-skeleton-every-page-starts-with) | The name on the browser tab and in a bookmark. |
| [`<body>`](#the-skeleton-every-page-starts-with) | Everything the visitor sees. |
| [`<h1>` … `<h6>`](#headings) | An outline of the page, biggest to smallest — not font sizes. |
| [`<p>`](#text) | A paragraph. |
| [`<strong>` / `<em>`](#text) | This matters / say this one differently — not just bold/italic. |
| [`<ul>` / `<ol>` / `<li>`](#lists) | A list (bullets / numbers), and each item in it. |
| [`<a href="...">`](#links) | A link. |
| [`<img src="..." alt="...">`](#images) | A picture, and the words that stand in for it. |
| [`<table>` / `<tr>` / `<th>` / `<td>`](#tables) | Rows and columns, for real data. |
| [`<div>` / `<span>`](#div-and-span-the-two-that-mean-nothing) | A generic block / a generic bit of text. Mean nothing on their own. |
| [`<header>` / `<nav>` / `<main>` / `<footer>`](#the-tags-that-hold-a-page-together) | Structure for screen readers and search engines — invisible on screen. |
| [`<form>` / `<label>` / `<input>` / `<button>`](#forms) | Collecting input from a visitor. |
| [`id` / `class`](#id-vs-class) | Name tags for one specific thing / a reusable group. |

Almost everything on this page is the same idea, repeated: **a label wrapped around some words**,
and the label says what the words *are*, not how they should look. How they look is CSS's job —
see the [CSS cheat sheet](css-selectors-cheat-sheet.md).

---

> **A tag has two halves.** `<p>Open until 11.</p>` — `<p>` is the **opening tag**, `</p>` is the
> **closing tag** (the same word with a slash), and everything between them is what a person
> reads. Forget the closing tag and the browser guesses what you meant — usually wrong, and
> always without an error. "It looks fine" is never the same as "it's right."

---

## The skeleton every page starts with

```html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>The Corner Store</title>
  </head>
  <body>

    <h1>The Corner Store</h1>

  </body>
</html>
```

| Line | What it's for |
|---|---|
| `<!DOCTYPE html>` | One line, no closing tag, always first. |
| `<html lang="en">` | Wraps the whole page. `lang="en"` tells a screen reader to read it as English. |
| `<head>` | Everything in here is for the **browser** — the visitor never sees it. |
| `<meta charset="utf-8">` | Leave it off and anything beyond plain English (accents, curly quotes) turns to garbage. |
| `<title>` | The browser-tab text. Not part of the visible page. |
| `<body>` | Everything the **visitor** sees. All your content goes in here. |

**Why it matters:** the page still "works" without most of this, but head-vs-body is the first
thing to check when something you typed refuses to show up — it may have ended up in the head by
mistake.

---

## Headings

```html
<h1>The Corner Store</h1>
<h2>Hours</h2>
<h2>Where we are</h2>
  <h3>Parking</h3>
```

One `<h1>` per page — the name of the page. `<h2>`s are its sections, `<h3>`s are sections of
those, down to `<h6>`.

**Why you use it:** headings are an **outline**, not a font size. Someone using a screen reader
jumps heading to heading the way you'd skim a table of contents. Picking `<h4>` because it looked
the right size on screen breaks that — sizing is a CSS job, not an HTML one.

---

## Text

```html
<p>We close at 11pm. <strong>Not 11:30.</strong></p>
<p>The good coffee is <em>behind</em> the counter.</p>
```

`<strong>` renders bold, `<em>` renders italic — but that's not what they *mean*. They mean **this
matters** and **say this one differently**, which is why a screen reader can change its voice for
them. Want bold text just for the look of it, with no meaning behind it? That's CSS
(`font-weight`), not `<strong>`.

---

## Lists

```html
<ul>
  <li>Coffee and breakfast</li>
  <li>Cold drinks</li>
</ul>
```

`<ul>` is the list itself (bullets); swap it for `<ol>` and you get `1, 2, 3` instead. `<li>` is
one item. You say "this is a list" — the browser decides how to draw the bullets or numbers.

**Nesting a list inside a list:** the inner `<ul>` goes *inside* the `<li>`, before its closing
tag:

```html
<ul>
  <li>Drinks
    <ul>
      <li>Coffee</li>
      <li>Soda</li>
    </ul>
  </li>
  <li>Snacks</li>
</ul>
```

---

## Links

```html
<a href="https://github.com/username/repo">Our board</a>
```

`href="..."` is an **attribute** — extra information tucked inside the opening tag (the same idea
as `lang="en"`). It's where the link goes; nobody sees it. The words between the tags are what the
visitor sees and clicks — make them say where the link goes. "Click here," read on its own, tells
someone nothing.

A link can point at more than just another website:

```html
<a href="https://example.com">another site</a>
<a href="hours.html">another page in this same folder</a>
<a href="mailto:ray@cornerstore.com">opens their email</a>
<a href="tel:8035550100">on a phone, it dials</a>
```

A bare filename (`hours.html`) works because it sits right next to the current file — that's how a
multi-page site holds together. `target="_blank"` opens a link in a new tab; use it rarely, since
it takes the Back button away from someone relying on it.

---

## Images

```html
<img src="storefront.jpg" alt="The store from across Main Street at dusk">
```

`<img>` has **no closing tag** — there's nothing to wrap, the picture *is* the content. Two
attributes: `src` (where the picture is) and `alt` (what it shows).

**Why `alt` matters:** it isn't a box to tick. It's the words that do the job when the picture
can't — a broken file, a slow connection, or a screen reader that can't show it.

---

## Tables

```html
<table>
  <tr>
    <th>Day</th>
    <th>Opens</th>
  </tr>
  <tr>
    <td>Mon–Fri</td>
    <td>6am</td>
  </tr>
</table>
```

`<tr>` is one row. `<th>` is a heading cell (top of a column). `<td>` is an ordinary cell.

**Why you use it:** tables are for things that really are rows and columns — actual data. For
years people used them to position everything on a page. Don't; that's what CSS layout is for.

---

## Forms

```html
<form>
  <label for="email">Email</label>
  <input id="email" type="email">
  <button>Tell me about specials</button>
</form>
```

| Piece | What it's for |
|---|---|
| `<label>` | The words next to the box. |
| `<input>` | The box itself. No closing tag — same reason as `<img>`. |
| `for` / `id` | The **same value on both** ties the label to its box. |

**Why `for`/`id` matters:** with them, clicking the word "Email" puts the cursor in the box. Miss
it and clicking the label does nothing — and a screen reader reaches the box and says "edit text,
blank," with no idea what belongs there.

`<input>` changes shape based on `type`:

```html
<input type="text">      <!-- anything at all -->
<input type="email">     <!-- phone keyboards show the @ key -->
<input type="number">    <!-- little up/down arrows -->
<input type="date">      <!-- the browser gives you a calendar -->
<input type="checkbox">  <!-- on or off -->
<input type="radio">     <!-- pick exactly one from a group -->

<textarea></textarea>    <!-- a big multi-line box -->
<select><option>...      <!-- a dropdown -->
```

Every one of them still needs its own `<label>`.

---

## The tags that hold a page together

```html
<body>
  <header>  <!-- the name of the place, the top bit -->
  <nav>     <!-- the links to everywhere else -->
  <main>    <!-- the actual point of this page -->
  <footer>  <!-- the address, the small print -->
</body>
```

Adding these changes **nothing** about how the page looks — that's the point. They exist for
everyone who isn't looking at the screen: screen readers, "reader mode," and search engines.
`<main>` is how a screen reader offers to skip straight past the menu.

## `<div>` and `<span>` — the two that mean nothing

```html
<div>a box round some things</div>
<p>a <span>few words</span> inside a sentence</p>
```

`<div>` and `<span>` say *nothing* about what's inside them. They exist so you have something to
grab hold of when you want to style it — which is why they almost always show up wearing a
`class`. Rule of thumb: if a tag exists that says what the thing *is* (a list, a heading, a nav),
use that one. Reach for `<div>`/`<span>` only when there honestly isn't one.

---

## `id` vs `class`

```html
<p id="store-hours">Open 6am to 11pm.</p>

<li class="special">Coffee and a pastry — $4</li>
<li class="special">Two cold drinks — $3</li>
<li>Milk</li>
```

| Attribute | Meaning |
|---|---|
| `id` | **One** particular thing on the page. Never reuse it — like a seat number. |
| `class` | A **group** of things that belong together. Reuse it freely. |

On their own, these two attributes do nothing — the page looks identical either way. They're name
tags. Tomorrow's job (CSS) is saying "make *those* red" by pointing at the class or id — see
[Selectors](css-selectors-cheat-sheet.md#the-selector-cheat-sheet-all-of-it-at-once).

---

## Nesting: parent, child, sibling

```html
<body>
  <ul>
    <li>Coffee</li>      <!-- li is a CHILD of ul -->
    <li>Soda</li>        <!-- the two li's are SIBLINGS -->
  </ul>                  <!-- ul is the PARENT -->
</body>
```

Tags go inside tags — that's the whole structure of a page, a family tree. **One hard rule: they
nest, they never overlap.** `<p><strong>hi</p></strong>` is wrong — close the inside tag first.

## Block vs. inline

| Take the whole line (**block**) | Sit inside a line (**inline**) |
|---|---|
| `h1 h2 p ul li div table` | `a strong em img span` |

Block tags start on a new line and push the next thing down. Inline tags sit in the flow of a
sentence, only as wide as they need — which is why a link doesn't shove the rest of the sentence
onto the next line. CSS's `display` property can override which one a tag is.

---

## Tags with nothing inside (no closing tag)

```html
<meta charset="utf-8">
<img src="..." alt="...">
<input type="email">
<br>
<hr>
<link rel="stylesheet" href="styles.css">
```

The rule: **if there are no words to wrap, there's nothing to close.** You'll sometimes see these
written with a trailing slash (`<br />`) — same thing, older style, still valid.

- `<br>` forces a line break — use sparingly, it's usually a paragraph you actually wanted.
- `<hr>` draws a horizontal rule — a change of subject.

---

## Comments and special characters

```html
<!-- Notes to yourself. The browser ignores all of this. -->

<p>Bread &amp; milk</p>          <!-- → Bread & milk -->
<p>Use &lt;h1&gt; for the name</p> <!-- → Use <h1> for the name -->
```

A **comment** (`<!-- -->`) never reaches the page — good for reminders, or switching a chunk off
without deleting it.

To put a literal `<`, `>`, or `&` on the page (characters that otherwise start a tag or an entity),
spell them out: `&lt;`, `&gt;`, `&amp;`. They always start with `&` and end with `;`.
