# CSS Complete Notes — Properties, Values & Why We Use Them

> CSS (Cascading Style Sheets) controls the **look and layout** of HTML. HTML = structure, CSS = style.
> Syntax: `selector { property: value; }`

---

## Table of Contents
1. [Basics: Ways to add CSS](#1-basics)
2. [Selectors](#2-selectors)
3. [Units & Values](#3-units--values)
4. [Colors & Backgrounds](#4-colors--backgrounds)
5. [Box Model (margin, padding, border, size)](#5-box-model)
6. [Text & Fonts](#6-text--fonts)
7. [Display & Positioning](#7-display--positioning)
8. [Flexbox](#8-flexbox)
9. [Grid](#9-grid)
10. [Lists, Tables, Cursor, Misc](#10-lists-tables-and-misc)
11. [Effects: shadow, filter, opacity](#11-effects)
12. [Transforms, Transitions, Animations](#12-transforms-transitions-animations)
13. [Responsive Design & Media Queries](#13-responsive-design)
14. [Pseudo-classes & Pseudo-elements](#14-pseudo-classes--pseudo-elements)
15. [Variables, calc(), functions](#15-variables-and-functions)
16. [Specificity, Cascade, Inheritance](#16-specificity-cascade-inheritance)
17. [Quick Cheat Sheet](#17-quick-cheat-sheet)

---

## 1. Basics

### Three ways to add CSS
| Method | Example | When to use |
|---|---|---|
| **Inline** | `<p style="color:red">` | Quick one-off tests only; hard to maintain |
| **Internal** | `<style> p{color:red} </style>` in `<head>` | Single-page demos |
| **External** | `<link rel="stylesheet" href="style.css">` | **Best practice**; reusable across pages, cached by browser |

### Comments
```css
/* This is a CSS comment */
```

### `@import`
Imports another stylesheet. `@import url("fonts.css");` (prefer `<link>`, it is faster).

---

## 2. Selectors
**Why:** Selectors decide *which* HTML elements get the style.

| Selector | Example | Meaning |
|---|---|---|
| Universal | `* {}` | All elements (used for resets) |
| Element/Type | `p {}` | All `<p>` |
| Class | `.card {}` | Elements with `class="card"` (reusable) |
| ID | `#header {}` | One element with `id="header"` (unique) |
| Group | `h1, h2, p {}` | Several selectors, same style |
| Descendant | `div p {}` | `p` anywhere inside `div` |
| Child | `div > p {}` | `p` directly inside `div` |
| Adjacent sibling | `h1 + p {}` | `p` immediately after `h1` |
| General sibling | `h1 ~ p {}` | All `p` siblings after `h1` |
| Attribute | `[type]`, `[type="text"]` | Elements having that attribute |
| `[attr^="x"]` | starts with | `a[href^="https"]` |
| `[attr$="x"]` | ends with | `a[href$=".pdf"]` |
| `[attr*="x"]` | contains | `a[href*="google"]` |
| `[attr~="x"]` | word in space-separated list | `[class~="btn"]` |
| `[attr\|="x"]` | exact or followed by `-` | `[lang\|="en"]` |
| `:is()` / `:where()` | `:is(h1,h2) span {}` | Shorter grouping (`:where` has 0 specificity) |
| `:not()` | `p:not(.intro) {}` | Exclude elements |
| `:has()` | `div:has(img) {}` | Parent selector (select parent that contains…) |

---

## 3. Units & Values

### Absolute units
| Unit | Meaning | Use |
|---|---|---|
| `px` | pixel | Borders, small fixed sizes |
| `cm`, `mm`, `in`, `pt`, `pc` | physical units | Mostly print CSS |

### Relative units
| Unit | Relative to | Why use |
|---|---|---|
| `%` | Parent's value | Fluid layouts |
| `em` | Parent/own font-size | Scalable spacing inside components |
| `rem` | Root (`html`) font-size | **Best for font sizes**; consistent, accessible |
| `vw` / `vh` | 1% of viewport width/height | Full-screen sections |
| `vmin` / `vmax` | smaller/larger of vw, vh | Responsive squares |
| `svh`, `lvh`, `dvh` | small/large/dynamic viewport height | Fix mobile browser-bar issues |
| `ch` | width of "0" character | Limit line length (`max-width: 65ch`) |
| `ex` | x-height | Rare |
| `fr` | fraction of free space | Grid columns only |

### Value types
- **Keywords:** `auto`, `none`, `inherit`, `initial`, `unset`, `revert`
- **Numbers:** `0`, `1.5`
- **Strings:** `"text"`
- **URLs:** `url("img.png")`

### Global values (work on every property)
| Value | Meaning |
|---|---|
| `inherit` | Take parent's value |
| `initial` | Reset to the CSS default |
| `unset` | `inherit` if property is inheritable, else `initial` |
| `revert` | Roll back to browser default stylesheet |

---

## 4. Colors & Backgrounds

### Color formats
| Format | Example |
|---|---|
| Name | `red`, `tomato`, `rebeccapurple` |
| HEX | `#ff0000`, `#f00`, `#ff000080` (with alpha) |
| RGB / RGBA | `rgb(255 0 0)`, `rgba(255,0,0,0.5)` |
| HSL / HSLA | `hsl(0 100% 50%)` (hue, saturation, lightness) |
| `transparent` | fully transparent |
| `currentColor` | uses the element's `color` value |
| Modern | `oklch()`, `lab()`, `color-mix()` |

### `color`
- **Why:** Sets **text** color. **Values:** any color. Inherited.

### `opacity`
- **Why:** Transparency of the entire element (including children).
- **Values:** `0` (invisible) to `1` (solid).

### Background properties
| Property | Why | Values |
|---|---|---|
| `background-color` | Fill color | any color |
| `background-image` | Image/gradient behind content | `url()`, `linear-gradient()`, `radial-gradient()`, `conic-gradient()`, `none` |
| `background-repeat` | Tiling | `repeat`, `no-repeat`, `repeat-x`, `repeat-y`, `space`, `round` |
| `background-position` | Placement | `center`, `top`, `bottom`, `left`, `right`, `10px 20px`, `50% 50%` |
| `background-size` | Scaling | `auto`, `cover` (fill, may crop), `contain` (fit entirely), `100px 50px`, `50%` |
| `background-attachment` | Scroll behavior | `scroll`, `fixed` (parallax), `local` |
| `background-origin` | Where position starts | `padding-box`, `border-box`, `content-box` |
| `background-clip` | Where bg is painted | `border-box`, `padding-box`, `content-box`, `text` (gradient text) |
| `background-blend-mode` | Blend layers | `multiply`, `screen`, `overlay`, `darken`, `lighten`… |
| `background` (shorthand) | All in one | `background: #fff url(a.png) no-repeat center/cover;` |

```css
.hero {
  background: linear-gradient(to right, #667eea, #764ba2);
}
.gradient-text {
  background: linear-gradient(90deg, red, blue);
  -webkit-background-clip: text;
  background-clip: text;
  color: transparent;
}
```

---

## 5. Box Model

Every element is a box: **content → padding → border → margin**.

```
┌──────────── margin ────────────┐
│ ┌──────── border ──────────┐   │
│ │ ┌───── padding ───────┐  │   │
│ │ │       content       │  │   │
│ │ └─────────────────────┘  │   │
│ └──────────────────────────┘   │
└────────────────────────────────┘
```

### `width` / `height`
- **Why:** Size of the content box (by default).
- **Values:** `auto`, `px`, `%`, `rem`, `vw`, `vh`, `fit-content`, `min-content`, `max-content`.

### `min-width`, `max-width`, `min-height`, `max-height`
- **Why:** Set limits. `max-width: 100%` makes images responsive; `min-height: 100vh` makes full-screen sections.

### `box-sizing`
- **Why:** Decides whether padding/border are *added to* or *included in* width.
- **Values:** `content-box` (default; padding adds extra size), `border-box` (**recommended**; padding+border included).
```css
*, *::before, *::after { box-sizing: border-box; }
```

### `margin` (outside space)
- **Why:** Space *between* elements.
- **Values:** length, `%`, `auto` (centers block horizontally), negative values.
- Properties: `margin-top`, `margin-right`, `margin-bottom`, `margin-left`.
- Shorthand: `margin: 10px;` (all) · `10px 20px;` (vertical horizontal) · `10px 20px 30px;` (top, horizontal, bottom) · `10px 20px 30px 40px;` (top, right, bottom, left — clockwise).
- **Margin collapse:** vertical margins of adjacent blocks merge into the larger one.
- **Logical:** `margin-inline`, `margin-block`, `margin-inline-start`, etc. (support RTL languages).

### `padding` (inside space)
- **Why:** Space between content and border. Same shorthand rules as margin. No negative or `auto` values.
- `padding-top/right/bottom/left`, `padding-inline`, `padding-block`.

### `border`
| Property | Why | Values |
|---|---|---|
| `border-width` | Thickness | `thin`, `medium`, `thick`, `2px` |
| `border-style` | Line type | `none`, `solid`, `dashed`, `dotted`, `double`, `groove`, `ridge`, `inset`, `outset`, `hidden` |
| `border-color` | Color | any color |
| `border` | Shorthand | `border: 2px solid #333;` |
| `border-top/right/bottom/left` | Single side | `border-bottom: 1px solid red;` |
| `border-radius` | Rounded corners | `5px`, `50%` (circle), `10px 20px`, `999px` (pill) |
| `border-collapse` | Table borders merge | `collapse`, `separate` |
| `border-image` | Image as border | `border-image: url(b.png) 30 round;` |

### `outline`
- **Why:** Line **outside** the border; doesn't take space. Used for **focus indicators** (accessibility).
- **Properties:** `outline`, `outline-width`, `outline-style`, `outline-color`, `outline-offset` (gap from border).
- **Warning:** never do `outline: none` without providing another focus style.

### `overflow`
- **Why:** What happens when content is bigger than its box.
- **Values:** `visible` (default), `hidden` (clip), `scroll` (always scrollbars), `auto` (scrollbars when needed), `clip`.
- Axis-specific: `overflow-x`, `overflow-y`.
- Related: `text-overflow`, `overscroll-behavior`, `scroll-behavior`.

### `aspect-ratio`
- **Why:** Keep width:height proportion. **Values:** `16 / 9`, `1 / 1`, `auto`.

### `object-fit` & `object-position`
- **Why:** Control how `<img>`/`<video>` fills its box.
- **Values:** `fill`, `contain`, `cover`, `none`, `scale-down`. Position: `center`, `top`, `20% 50%`.

---

## 6. Text & Fonts

### Font properties
| Property | Why | Values |
|---|---|---|
| `font-family` | Typeface | `"Poppins", Arial, sans-serif` (always give fallbacks; generic: `serif`, `sans-serif`, `monospace`, `cursive`, `system-ui`) |
| `font-size` | Text size | `16px`, `1rem`, `120%`, `larger`, `smaller`, `clamp(1rem, 2vw, 2rem)` |
| `font-weight` | Boldness | `normal`(400), `bold`(700), `100`–`900`, `lighter`, `bolder` |
| `font-style` | Slant | `normal`, `italic`, `oblique` |
| `font-variant` | Small caps etc. | `normal`, `small-caps` |
| `font-stretch` | Width of glyphs | `condensed`, `expanded`, `75%`–`125%` |
| `font` (shorthand) | All in one | `font: italic bold 16px/1.5 Arial, sans-serif;` |
| `font-display` (in `@font-face`) | Loading behavior | `swap`, `block`, `fallback`, `optional` |

### `@font-face` (custom fonts)
```css
@font-face {
  font-family: "MyFont";
  src: url("my.woff2") format("woff2");
  font-display: swap;
}
```

### Text properties
| Property | Why | Values |
|---|---|---|
| `text-align` | Horizontal alignment | `left`, `right`, `center`, `justify`, `start`, `end` |
| `text-align-last` | Last line alignment | same as above |
| `text-decoration` | Underline etc. | `none`, `underline`, `overline`, `line-through`, `underline wavy red` |
| `text-decoration-line/color/style/thickness` | Fine control | `solid`, `double`, `dotted`, `dashed`, `wavy` |
| `text-underline-offset` | Gap of underline | `4px` |
| `text-transform` | Change case | `none`, `uppercase`, `lowercase`, `capitalize` |
| `text-indent` | First-line indent | `2em` |
| `text-shadow` | Shadow behind text | `2px 2px 4px rgba(0,0,0,.5)` (x y blur color) |
| `text-overflow` | Clipped text indicator | `clip`, `ellipsis` (needs `overflow:hidden; white-space:nowrap`) |
| `letter-spacing` | Space between letters | `1px`, `0.05em` |
| `word-spacing` | Space between words | `5px` |
| `line-height` | Line spacing | `1.5` (unitless best), `24px` |
| `white-space` | Wrapping/whitespace | `normal`, `nowrap`, `pre`, `pre-wrap`, `pre-line`, `break-spaces` |
| `word-break` | Break long words | `normal`, `break-all`, `keep-all` |
| `overflow-wrap` (`word-wrap`) | Break overflow | `normal`, `break-word`, `anywhere` |
| `hyphens` | Auto hyphenation | `none`, `manual`, `auto` |
| `direction` | Text direction | `ltr`, `rtl` |
| `writing-mode` | Vertical text | `horizontal-tb`, `vertical-rl`, `vertical-lr` |
| `vertical-align` | Inline/table-cell vertical alignment | `baseline`, `top`, `middle`, `bottom`, `sub`, `super`, `text-top` |
| `text-wrap` | Balanced headings | `wrap`, `nowrap`, `balance`, `pretty` |
| `line-clamp` (`-webkit-line-clamp`) | Limit lines | `3` (with `display:-webkit-box`) |
| `tab-size` | Tab width in `<pre>` | `4` |
| `user-select` | Allow text selection | `auto`, `none`, `text`, `all` |
| `caret-color` | Cursor color in inputs | any color |
| `accent-color` | Checkbox/radio color | any color |
| `color-scheme` | Light/dark UI parts | `light`, `dark`, `light dark` |

```css
.ellipsis { white-space: nowrap; overflow: hidden; text-overflow: ellipsis; }
.clamp-3 { display:-webkit-box; -webkit-line-clamp:3; -webkit-box-orient:vertical; overflow:hidden; }
```

---

## 7. Display & Positioning

### `display`
**Why:** Defines how an element behaves in layout.
| Value | Behavior |
|---|---|
| `block` | Full width, starts new line; width/height work |
| `inline` | Flows with text; width/height/vertical margin ignored |
| `inline-block` | Inline flow but accepts width/height |
| `none` | Removed from layout entirely (not rendered) |
| `flex` / `inline-flex` | Flexbox container |
| `grid` / `inline-grid` | Grid container |
| `table`, `table-row`, `table-cell` | Table behavior |
| `contents` | Element's box disappears; children stay |
| `list-item` | Like `<li>` with marker |
| `flow-root` | Creates new formatting context (clearfix) |

### `visibility`
- **Why:** Hide but keep space. **Values:** `visible`, `hidden`, `collapse`.
- `display:none` removes space; `visibility:hidden` keeps it; `opacity:0` keeps it and stays clickable.

### `position`
| Value | Behavior |
|---|---|
| `static` | Default; normal flow; top/left ignored |
| `relative` | Offset from its normal position; reserves original space; becomes anchor for absolute children |
| `absolute` | Removed from flow; positioned to nearest positioned ancestor |
| `fixed` | Positioned to viewport; stays on scroll (navbars) |
| `sticky` | Acts relative until scroll threshold, then sticks (sticky headers) |

- **Offsets:** `top`, `right`, `bottom`, `left`, `inset` (shorthand for all four). Values: length, `%`, `auto`.
- **`z-index`:** stacking order; integer (higher is on top); works on positioned elements (and flex/grid items).

```css
.parent { position: relative; }
.badge  { position: absolute; top: 0; right: 0; }
.center { position:absolute; inset:0; margin:auto; width:200px; height:100px; }
```

### `float` & `clear` (legacy layout)
- `float`: `left`, `right`, `none` — wraps text around images.
- `clear`: `left`, `right`, `both`, `none` — stops wrapping.

### `isolation`
- `isolation: isolate;` creates new stacking context so z-index doesn't leak.

### `contain`, `content-visibility`
- Performance hints: `content-visibility: auto;` skips rendering off-screen content.

---

## 8. Flexbox
**Why:** One-dimensional layout (row OR column) — alignment, spacing, centering, equal heights.

### Container properties (`display: flex`)
| Property | Why | Values |
|---|---|---|
| `flex-direction` | Main axis | `row`, `row-reverse`, `column`, `column-reverse` |
| `flex-wrap` | Wrap to new lines | `nowrap`, `wrap`, `wrap-reverse` |
| `flex-flow` | Shorthand | `row wrap` |
| `justify-content` | Align along **main** axis | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `space-evenly` |
| `align-items` | Align along **cross** axis | `stretch`, `flex-start`, `flex-end`, `center`, `baseline` |
| `align-content` | Multi-line cross spacing | `flex-start`, `flex-end`, `center`, `space-between`, `space-around`, `stretch` |
| `gap`, `row-gap`, `column-gap` | Space between items | `10px`, `1rem 2rem` |

### Item properties
| Property | Why | Values |
|---|---|---|
| `flex-grow` | Share extra space | `0` (default), `1`, `2` |
| `flex-shrink` | Shrink when tight | `1` (default), `0` (never shrink) |
| `flex-basis` | Starting size | `auto`, `200px`, `30%`, `0` |
| `flex` | Shorthand | `flex: 1;` (= `1 1 0`), `flex: 0 0 200px;`, `flex: auto;`, `flex: none;` |
| `align-self` | Override align-items for one item | `auto`, `flex-start`, `center`, `flex-end`, `stretch`, `baseline` |
| `order` | Visual order | integer (default `0`, negative allowed) |

```css
/* Perfect centering */
.center { display:flex; justify-content:center; align-items:center; min-height:100vh; }
/* Navbar */
.nav { display:flex; justify-content:space-between; align-items:center; }
```

---

## 9. Grid
**Why:** Two-dimensional layout (rows AND columns) — page layouts, galleries, dashboards.

### Container properties (`display: grid`)
| Property | Why | Values |
|---|---|---|
| `grid-template-columns` | Define columns | `200px 1fr 1fr`, `repeat(3, 1fr)`, `repeat(auto-fit, minmax(250px, 1fr))` |
| `grid-template-rows` | Define rows | `100px auto`, `repeat(2, 1fr)` |
| `grid-template-areas` | Named layout | `"header header" "sidebar main" "footer footer"` |
| `grid-template` | Shorthand | rows / columns |
| `grid-auto-rows` / `grid-auto-columns` | Size of auto-created tracks | `100px`, `minmax(100px, auto)` |
| `grid-auto-flow` | Auto-placement | `row`, `column`, `dense` |
| `gap`, `row-gap`, `column-gap` | Gutters | `20px` |
| `justify-items` | Align items horizontally inside cells | `start`, `end`, `center`, `stretch` |
| `align-items` | Align items vertically inside cells | `start`, `end`, `center`, `stretch` |
| `place-items` | Shorthand (align + justify) | `center` |
| `justify-content` | Align whole grid horizontally | `start`, `end`, `center`, `space-between`, `space-around`, `space-evenly` |
| `align-content` | Align whole grid vertically | same |
| `place-content` | Shorthand | `center` |

### Item properties
| Property | Why | Values |
|---|---|---|
| `grid-column` | Span columns | `1 / 3`, `span 2`, `1 / -1` (full width) |
| `grid-row` | Span rows | `2 / 4`, `span 2` |
| `grid-column-start/end`, `grid-row-start/end` | Long form | line number / `span n` |
| `grid-area` | Place in named area or by lines | `header` or `1 / 1 / 3 / 3` |
| `justify-self`, `align-self`, `place-self` | Align one item | `start`, `end`, `center`, `stretch` |

### Grid functions
- `repeat(n, size)` — repeat tracks
- `minmax(min, max)` — size range
- `fit-content(size)`
- `auto-fit` (collapses empty tracks) vs `auto-fill` (keeps empty tracks)
- `subgrid` — inherit parent's tracks

```css
.layout {
  display: grid;
  grid-template-columns: 250px 1fr;
  grid-template-areas:
    "header header"
    "sidebar main"
    "footer footer";
  gap: 1rem;
}
header{grid-area:header} aside{grid-area:sidebar} main{grid-area:main} footer{grid-area:footer}

/* Responsive cards with no media query */
.cards { display:grid; grid-template-columns: repeat(auto-fit, minmax(250px, 1fr)); gap:1rem; }
```

### Flexbox vs Grid
| Flexbox | Grid |
|---|---|
| 1D (row or column) | 2D (rows + columns) |
| Content-driven | Layout-driven |
| Navbars, buttons, centering | Page layout, galleries |

---

## 10. Lists, Tables and Misc

### Lists
| Property | Why | Values |
|---|---|---|
| `list-style-type` | Marker shape | `disc`, `circle`, `square`, `decimal`, `lower-alpha`, `upper-roman`, `none` |
| `list-style-position` | Marker inside/outside | `outside`, `inside` |
| `list-style-image` | Custom marker | `url(icon.png)` |
| `list-style` | Shorthand | `none` (remove bullets for menus) |
| `counter-reset`, `counter-increment`, `counter()` | Custom numbering | `counter-increment: section;` |

### Tables
| Property | Why | Values |
|---|---|---|
| `border-collapse` | Merge cell borders | `collapse`, `separate` |
| `border-spacing` | Gap between cells | `5px` |
| `caption-side` | Caption location | `top`, `bottom` |
| `empty-cells` | Show empty cell borders | `show`, `hide` |
| `table-layout` | Column width algorithm | `auto`, `fixed` (faster, predictable) |

### Cursor & interaction
| Property | Why | Values |
|---|---|---|
| `cursor` | Mouse pointer | `default`, `pointer` (links/buttons), `text`, `move`, `grab`, `grabbing`, `not-allowed`, `wait`, `help`, `zoom-in`, `crosshair`, `progress`, `url()` |
| `pointer-events` | Ignore clicks | `auto`, `none` |
| `user-select` | Text selection | `none`, `text`, `all` |
| `resize` | User-resizable | `none`, `both`, `horizontal`, `vertical` |
| `touch-action` | Touch gestures | `auto`, `none`, `pan-x`, `pan-y`, `manipulation` |
| `appearance` | Remove native styling | `none`, `auto` |
| `scroll-behavior` | Smooth anchor scroll | `auto`, `smooth` |
| `scroll-snap-type` / `scroll-snap-align` | Snap carousels | `x mandatory`, `start`, `center` |
| `scroll-margin` / `scroll-padding` | Offset for sticky headers | `80px` |
| `overscroll-behavior` | Stop scroll chaining | `auto`, `contain`, `none` |
| `will-change` | Hint for performance | `transform`, `opacity` |

### Content / generated content
| Property | Why | Values |
|---|---|---|
| `content` | Insert content via `::before/::after` | `"text"`, `url()`, `attr(title)`, `counter()`, `""` |
| `quotes` | Quote marks style | `"«" "»"` |

### Print
- `@media print {}`, `page-break-before/after/inside` (now `break-before/after/inside`), `@page { margin: 2cm; }`.

---

## 11. Effects

### `box-shadow`
- **Why:** Depth/elevation on boxes.
- **Syntax:** `offset-x offset-y blur spread color [inset]`
```css
box-shadow: 0 4px 10px rgba(0,0,0,.2);
box-shadow: inset 0 0 5px #000;           /* inner shadow */
box-shadow: 0 1px 2px #000, 0 8px 20px #0003; /* multiple */
```

### `filter` (applies to element itself)
| Function | Effect |
|---|---|
| `blur(5px)` | Blur |
| `brightness(1.2)` | Lighter/darker |
| `contrast(150%)` | Contrast |
| `grayscale(100%)` | Black & white |
| `sepia(80%)` | Vintage |
| `saturate(2)` | Color intensity |
| `hue-rotate(90deg)` | Shift hues |
| `invert(100%)` | Invert colors |
| `opacity(50%)` | Transparency |
| `drop-shadow(2px 2px 4px #000)` | Shadow following shape (works on PNG transparency) |

### `backdrop-filter`
- **Why:** Blur/effects on what's *behind* element (glassmorphism). `backdrop-filter: blur(10px);`

### `mix-blend-mode`
- Blend element with what's behind: `multiply`, `screen`, `overlay`, `difference`, etc.

### `clip-path`
- **Why:** Cut element into shapes. `circle(50%)`, `ellipse()`, `polygon(50% 0, 100% 100%, 0 100%)`, `inset(10px round 5px)`.

### `mask` / `mask-image`
- Hide parts using an image/gradient alpha.

### Gradients
```css
linear-gradient(45deg, red, blue)
radial-gradient(circle at center, #fff, #000)
conic-gradient(from 0deg, red, yellow, green, red)
repeating-linear-gradient(45deg, #000 0 10px, #fff 10px 20px)
```

---

## 12. Transforms, Transitions, Animations

### `transform`
**Why:** Move/rotate/scale without disturbing layout (GPU-accelerated).
| Function | Meaning |
|---|---|
| `translate(x, y)`, `translateX()`, `translateY()`, `translateZ()` | Move |
| `scale(1.2)`, `scaleX()`, `scaleY()` | Resize |
| `rotate(45deg)`, `rotateX()`, `rotateY()`, `rotateZ()` | Rotate |
| `skew(20deg, 10deg)` | Slant |
| `matrix()`, `matrix3d()` | Combined |
| `perspective(500px)` | 3D depth |

Related: `transform-origin` (`center`, `top left`, `50% 50%`), `transform-style` (`flat`, `preserve-3d`), `perspective`, `perspective-origin`, `backface-visibility` (`visible`, `hidden`), and individual `translate`, `rotate`, `scale` properties.

### Transitions — smooth change between states
| Property | Why | Values |
|---|---|---|
| `transition-property` | What to animate | `all`, `color`, `transform`, `opacity` |
| `transition-duration` | How long | `0.3s`, `300ms` |
| `transition-timing-function` | Speed curve | `ease`, `linear`, `ease-in`, `ease-out`, `ease-in-out`, `cubic-bezier(.4,0,.2,1)`, `steps(4)` |
| `transition-delay` | Wait before start | `0.1s` |
| `transition` | Shorthand | `transition: transform .3s ease-in-out;` |

### Animations — keyframe-based
```css
@keyframes slide {
  0%   { transform: translateX(0); }
  100% { transform: translateX(200px); }
}
.box { animation: slide 2s ease-in-out 0s infinite alternate both; }
```
| Property | Why | Values |
|---|---|---|
| `animation-name` | Keyframes name | identifier |
| `animation-duration` | Length | `2s` |
| `animation-timing-function` | Speed curve | same as transition |
| `animation-delay` | Start delay | `1s` |
| `animation-iteration-count` | Repeats | number, `infinite` |
| `animation-direction` | Direction | `normal`, `reverse`, `alternate`, `alternate-reverse` |
| `animation-fill-mode` | Style before/after | `none`, `forwards`, `backwards`, `both` |
| `animation-play-state` | Pause/play | `running`, `paused` |
| `animation-timeline` | Scroll-driven animations | `scroll()`, `view()` |
| `animation` | Shorthand | name duration timing delay count direction fill |

> **Tip:** Animate `transform` and `opacity` for best performance. Respect `@media (prefers-reduced-motion: reduce)`.

---

## 13. Responsive Design

### Viewport meta (in HTML)
```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

### Media queries
```css
@media (max-width: 768px) { /* tablets and below */ }
@media (min-width: 1024px) { /* desktop up */ }
@media (orientation: landscape) { }
@media (prefers-color-scheme: dark) { }
@media (prefers-reduced-motion: reduce) { }
@media (hover: hover) { }
@media print { }
@media screen and (min-width: 600px) and (max-width: 900px) { }
```
**Common breakpoints:** 480px (mobile), 768px (tablet), 1024px (laptop), 1200px+ (desktop).
**Mobile-first:** write base styles for mobile, then use `min-width` queries for larger screens.

### Other at-rules
| At-rule | Why |
|---|---|
| `@container (min-width: 400px)` | Style based on **parent container** size (`container-type: inline-size`) |
| `@supports (display:grid)` | Feature detection |
| `@layer` | Control cascade order |
| `@property` | Register typed custom properties |
| `@font-face`, `@keyframes`, `@import`, `@media`, `@namespace` | As described elsewhere |

### Responsive helpers
- `clamp(min, preferred, max)` — fluid font: `font-size: clamp(1rem, 2.5vw, 2rem);`
- `min()`, `max()`
- `max-width: 100%; height: auto;` for images
- `<picture>`/`srcset` in HTML for image variants

---

## 14. Pseudo-classes & Pseudo-elements

### Pseudo-classes (`:`) — element **state**
| Pseudo-class | When it matches |
|---|---|
| `:hover` | Mouse over |
| `:active` | Being clicked |
| `:focus` | Focused (keyboard/click) |
| `:focus-visible` | Focused via keyboard (best for outlines) |
| `:focus-within` | Element or child focused |
| `:visited`, `:link`, `:any-link` | Link states (order: LVHA — link, visited, hover, active) |
| `:checked`, `:disabled`, `:enabled`, `:required`, `:optional` | Form states |
| `:valid`, `:invalid`, `:in-range`, `:out-of-range` | Validation |
| `:placeholder-shown`, `:read-only`, `:read-write` | Input states |
| `:first-child`, `:last-child`, `:only-child` | Position among siblings |
| `:nth-child(n)` | `2n`, `odd`, `even`, `3n+1`, `-n+3` |
| `:nth-last-child(n)` | Counting from end |
| `:first-of-type`, `:last-of-type`, `:nth-of-type()` | By tag type |
| `:empty` | No children |
| `:root` | `<html>` (for variables) |
| `:target` | URL `#hash` target |
| `:not()`, `:is()`, `:where()`, `:has()` | Logical |
| `:lang()`, `:dir()` | Language/direction |
| `:fullscreen`, `:popover-open`, `:modal` | UI states |

### Pseudo-elements (`::`) — **part** of an element
| Pseudo-element | Why |
|---|---|
| `::before` / `::after` | Insert decorative content (needs `content`) |
| `::first-letter` | Drop caps |
| `::first-line` | Style first line |
| `::selection` | Highlighted text |
| `::placeholder` | Input placeholder text |
| `::marker` | List bullet/number |
| `::backdrop` | Behind `<dialog>`/fullscreen |
| `::file-selector-button` | File input button |
| `::cue` | Video captions |
| `::part()`, `::slotted()` | Web components |
| `::-webkit-scrollbar` | Custom scrollbar (WebKit) |

Also modern scrollbar styling: `scrollbar-width: thin|none|auto;` `scrollbar-color: thumb track;`

---

## 15. Variables and Functions

### Custom properties (CSS variables)
**Why:** Reuse values, easy theming (dark mode).
```css
:root { --primary: #3498db; --gap: 1rem; }
.btn  { background: var(--primary); padding: var(--gap); }
.x    { color: var(--missing, black); } /* fallback */
[data-theme="dark"] { --primary: #1abc9c; }
```

### Functions
| Function | Use |
|---|---|
| `calc()` | Math with mixed units: `width: calc(100% - 40px)` |
| `min()`, `max()`, `clamp()` | Responsive limits |
| `var()` | Use custom property |
| `attr()` | Read HTML attribute (in `content`) |
| `url()` | Resource path |
| `rgb()`, `hsl()`, `oklch()`, `color-mix()` | Colors |
| `linear-gradient()` etc. | Gradients |
| `repeat()`, `minmax()` | Grid |
| `translate()`, `rotate()`… | Transform |
| `counter()` | Counters |
| `env()` | Safe-area insets: `env(safe-area-inset-top)` |
| `round()`, `mod()`, `sin()`, `cos()`, `pow()`, `sqrt()` | Math functions |

### Nesting (native CSS)
```css
.card {
  padding: 1rem;
  & h2 { font-size: 1.5rem; }
  &:hover { box-shadow: 0 4px 10px #0003; }
}
```

---

## 16. Specificity, Cascade, Inheritance

### Specificity (higher wins)
| Selector | Weight |
|---|---|
| Inline style | 1000 |
| ID `#id` | 100 |
| Class, attribute, pseudo-class | 10 |
| Element, pseudo-element | 1 |
| `*`, `:where()` | 0 |

`!important` overrides everything (avoid it). If equal → **last rule wins**.

### Cascade order
1. Origin & importance (user-agent → author → `!important`)
2. `@layer` order
3. Specificity
4. Source order

### Inheritance
- **Inherited by default:** `color`, `font-*`, `line-height`, `text-align`, `visibility`, `cursor`, `list-style`, `letter-spacing`.
- **Not inherited:** `margin`, `padding`, `border`, `background`, `width`, `height`, `display`, `position`.
- Force with `inherit`.

---

## 17. Quick Cheat Sheet

### Modern CSS reset
```css
*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { scroll-behavior: smooth; }
body { line-height: 1.5; font-family: system-ui, sans-serif; }
img, video { max-width: 100%; height: auto; display: block; }
button, input { font: inherit; }
```

### Common patterns
```css
/* Center a block */          .box { margin: 0 auto; max-width: 960px; }
/* Center anything */         .c { display:grid; place-items:center; }
/* Sticky header */           header { position: sticky; top: 0; z-index: 100; }
/* Circle image */            img { width:100px; height:100px; border-radius:50%; object-fit:cover; }
/* Button hover */            .btn { transition: .3s; } .btn:hover { transform: translateY(-2px); }
/* Overlay */                 .overlay { position:fixed; inset:0; background:#0008; }
/* Truncate text */           .t { white-space:nowrap; overflow:hidden; text-overflow:ellipsis; }
/* Dark mode */               @media (prefers-color-scheme: dark) { :root { --bg:#111; --text:#eee; } }
```

### Property groups at a glance
| Category | Key properties |
|---|---|
| Layout | `display`, `position`, `float`, `flex*`, `grid*`, `z-index`, `overflow` |
| Box | `width`, `height`, `margin`, `padding`, `border`, `box-sizing`, `outline` |
| Typography | `font-*`, `text-*`, `line-height`, `letter-spacing`, `white-space` |
| Visual | `color`, `background*`, `box-shadow`, `opacity`, `filter`, `clip-path` |
| Motion | `transform`, `transition*`, `animation*` |
| Interaction | `cursor`, `pointer-events`, `user-select`, `resize`, `scroll-*` |

### Best practices
1. Use **external stylesheet** and meaningful class names (BEM: `.card__title--active`).
2. Use `rem` for fonts, `%`/`fr` for layout, `px` for borders.
3. Always set `box-sizing: border-box`.
4. Go **mobile-first**; use Flexbox/Grid, not floats.
5. Keep specificity low; avoid `!important` and ID selectors for styling.
6. Use CSS variables for colors/spacing.
7. Keep accessibility: visible focus, enough contrast (4.5:1), respect `prefers-reduced-motion`.

---
*End of notes. Practice by building small layouts: navbar, card grid, hero section, form, and a responsive footer.*