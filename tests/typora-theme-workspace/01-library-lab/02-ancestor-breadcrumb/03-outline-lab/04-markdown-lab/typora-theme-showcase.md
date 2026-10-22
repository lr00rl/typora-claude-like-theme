---
title: Typora Theme Showcase
theme: Claude-like
tags:
  - typora
  - theme
  - showcase
---

# Typora Theme Showcase

This file exercises as much of the `Claude-like` theme as possible. To see the file tree hint lines on the left and the outline connector lines at the same time, open the whole `tests/typora-theme-workspace` folder in Typora, then open this file.

- Sidebar checks: tree hint lines, sticky ancestor breadcrumb, sticky active file, active row highlight
- Outline checks: connector lines, corners at each heading level, hover and active states
- Body checks: typography, lists, tables, quotes, code blocks, inline code, line numbers, math, images, TOC, sidenotes
- Extra steps: switch between `Claude Like` and `Claude Like Dark`, and resize the window between wide and narrow

> To check the line-number style, turn on line numbers for code blocks in Typora's preferences first.

[TOC]

---

## 1. Table of contents and heading levels

This section gives the outline enough depth to show its vertical stems, L-shaped corners, first and last nodes, and the highlight on the current item.

### 1.1 Third-level heading

A paragraph of running text lets you judge the serif body face, its weight, and how numbers like 1, 24, and 860 sit next to punctuation over a long read.

#### 1.1.1 Fourth-level heading

A deeper heading adds another level to the outline.

##### 1.1.1.1 Fifth-level heading

This level checks that small headings do not crowd together.

###### 1.1.1.1.1 Sixth-level heading

A sixth-level heading is the one most likely to look like body text, so this is where to check that weak levels stay distinct.

### 1.2 Sibling branch

The outline needs sibling branches as well as one deep chain, so here is a second group at the same level.

#### 1.2.1 Child of the sibling branch

The outline should show a natural fork here, not just a single run of indentation.

#### 1.2.2 Another child

One more plain paragraph, so you can check that the active item stays clear while scrolling.

---

## 2. Body text and inline syntax

This paragraph shows the basic reading texture: `inline code`, **bold**, *italic*, ***bold italic***, ~~strikethrough~~, an [external link](https://typora.io/), and identifiers in running text such as `functionName()`, `--accent-color`, and `README.zh.md`.

The theme is also tuned for Chinese and mixed text, so here is one line of it: 这一行用来检查中文正文、标点和 English words 混排时的节奏。

A few more inline elements:

- HTML superscript: E = mc<sup>2</sup>
- HTML subscript: H<sub>2</sub>O
- Inline code capsule: `pnpm dev`
- Mixed numbers: version `v1.2.2`, depth `10`, color `#a85d3b`

### 2.1 Unordered list

- A first-level item
- Another first-level item, with `inline code`
  - A second-level item
  - A second-level item, to check the marker color
- The last first-level item

### 2.2 Ordered list

1. Step one: check the gap between the number and the text.
2. Step two: check that nested lists stay aligned.
3. Step three: check that long paragraphs inside a list do not feel cramped.

### 2.3 Task list

- [x] A finished task, which should have a softer color and a strikethrough
- [x] Another finished task, to check that the checked state is consistent
- [ ] An open task, to check the checkbox hover effect
- [ ] The last open task

---

## 3. Quotes, rules, and notes

> This is a first-level quote, to check the quote background, left border, corner radius, and text color.
>
> > This is a nested quote, to check that the inner quote stays readable instead of blending into the outer one.
>
> The last paragraph checks the spacing between paragraphs inside a quote.

GitHub-style alerts use the same container with a colored title:

> [!NOTE]
> A note carries neutral background information.

> [!WARNING]
> A warning flags something that can go wrong.

A quote sits above and a horizontal rule follows:

---

Body text after the rule checks that the space above and below feels even.

---

## 4. Tables

This table covers alignment, numbers, emphasis, and the row hover background.

| Area | Light | Dark | Notes |
| :-- | :--: | --: | :-- |
| Body text | Calm | Calm | **Restrained** body text for long reads |
| File tree | Yes | Yes | Tree hint lines and an accent bar on the active row |
| Outline lines | Yes | Yes | Easier to see with many heading levels |
| Code blocks | 6px radius | 6px radius | Syntax colors, language label, optional line numbers |
| Sidenotes | Responsive | Responsive | Float right on wide windows, inline on narrow ones |

### 4.1 Token reference

| Token | Value | Meaning |
| :-- | --: | :-- |
| `--accent-color` | `#a85d3b` | Theme accent |
| `--canvas-color` | `#faf9f6` | Light page background |
| `--surface-color` | `#f2f1ee` | Code block and quote background |
| `depth-support` | `10` | Sticky depth support |

---

## 5. Code blocks and line numbers

These blocks cover keywords, strings, numbers, comments, tags, attributes, variable names, and the language label.

### 5.1 TypeScript

```ts
type ThemeFeature = {
  name: string;
  depth: number;
  enabled: boolean;
};

const features: ThemeFeature[] = [
  { name: "tree-lines", depth: 10, enabled: true },
  { name: "outline-lines", depth: 6, enabled: true },
  { name: "sidenote", depth: 2, enabled: true },
];

function summarizeTheme(themeName: string): string {
  const active = features.filter((item) => item.enabled).length;
  return `${themeName} keeps ${active} polished UI details in sync.`;
}

console.log(summarizeTheme("Claude-like"));
```

### 5.2 HTML

```html
<section class="theme-demo" data-mode="light">
  <h2>Tree Hint Line</h2>
  <p>
    Body text
    <span class="sidenote">A margin note rendered by the theme.</span>
  </p>
</section>
```

### 5.3 CSS

```css
:root {
  --accent-color: #a85d3b;
  --line-color: #ddd9d2;
}

.outline-item-active::before {
  width: 7px !important;
}

#file-library-tree .file-tree-node.active {
  position: sticky;
  top: 0;
}
```

### 5.4 Bash

```bash
git log --oneline --decorate -n 10
rg -n "sidenote|outline|file-tree" claude-like.css
```

---

## 6. Math

Inline math: $f(x)=x^2 + 2x + 1$, to check that the math baseline sits naturally in the text.

Block math:

$$
\int_0^1 x^2 \, dx = \frac{1}{3}
$$

A common matrix:

$$
A =
\begin{bmatrix}
1 & 2 & 3 \\
0 & 1 & 4 \\
0 & 0 & 1
\end{bmatrix}
$$

---

## 7. Images and links

These three images check the size, corner radius, and spacing of the light, dark, and sidenote screenshots inside the theme.

![Light Theme Preview](https://raw.githubusercontent.com/lr00rl/typora-claude-like-theme/main/image/light.png)

![Dark Theme Preview](https://raw.githubusercontent.com/lr00rl/typora-claude-like-theme/main/image/dark.png)

![Sidenote Preview](https://raw.githubusercontent.com/lr00rl/typora-claude-like-theme/main/image/sidenote-example-wide.png)

See the [Typora website](https://typora.io/) or the repository's `README.md` and `README.zh.md` for more.

---

## 8. Footnotes

Footnotes show whether Typora's default footnote area fits the rest of the theme. Here is one reference[^theme], and here is a second one[^plugin].

[^theme]: The theme keeps a light and a dark variant, and tunes tables, code blocks, the sidebars, and sidenotes together.
[^plugin]: To get the full sidenote behavior inside the Typora editor, install the `sidenote` plugin from `typora-plugin-lite`.

---

## 9. Sidenotes

This section is the main sidenote check. Look at it in both a wide and a narrow window.

### 9.1 Plugin-friendly short form

This is a paragraph of body text<span class="sidenote">With the `sidenote` plugin from `typora-plugin-lite` installed, the editor turns this span into a styled sidenote. In a wide HTML export the theme floats it into the right margin.</span> and the text continues.

### 9.2 Full Tufte toggle structure

This paragraph uses the full toggle structure<label for="sn-demo-1" class="margin-toggle sidenote-number"></label><input type="checkbox" id="sn-demo-1" class="margin-toggle" /><span class="sidenote">This note checks the numbering, the right-margin float on wide windows, and the toggle on narrow ones.</span> and then carries on.

### 9.3 The markup in a code block

```html
Body text<span class="sidenote">A plugin-friendly sidenote.</span> continues here.

Body text
<label for="sn-demo-2" class="margin-toggle sidenote-number"></label>
<input type="checkbox" id="sn-demo-2" class="margin-toggle" />
<span class="sidenote">The full Tufte sidenote structure.</span>
continues here.
```

---

## 10. Final checklist

- [ ] The file tree shows tree hint lines
- [ ] Scrolling the file tree shows the sticky ancestor breadcrumb
- [ ] The active file stays sticky in the file tree
- [ ] The outline shows connector lines and corners at every level
- [ ] The `TOC` block looks right
- [ ] Table hover, borders, and number alignment look right
- [ ] Code blocks show syntax colors and a language label
- [ ] With line numbers on, the number color and spacing look right
- [ ] Sidenotes float right on wide windows and flow inline on narrow ones
- [ ] Switching between light and dark shows no visual break
