# 🔥 NeonBite — Fast Food Drag & Drop Menu

A visually rich, animated fast food ordering interface built with pure **HTML, CSS, and JavaScript** — no frameworks, no dependencies.

---

## 📸 Overview

NeonBite is a single-page drag-and-drop menu app where users can build a custom fast food order by dragging items from a **Menu** column into an **Order** column. It features a dark neon aesthetic, fluid animations, floating emoji particles, and a confetti celebration on checkout.

---

## 🚀 Features

| Feature | Description |
|---|---|
| 🖱️ Drag & Drop | Drag food items from Menu → Order and back |
| ✕ Remove Button | Click the ✕ on any order card to return it to the menu |
| ⚡ 5-Item Cap | Animated warning fires when the order limit is reached |
| 💰 Live Total | Running price updates instantly as items are added or removed |
| 🎉 Confetti | Canvas-based confetti burst fires on "Order Now" |
| 🔔 Toast Notifications | Slide-up toasts confirm every add/remove action |
| 🌊 Floating Particles | Food emoji drift upward in the background continuously |
| 📱 Responsive | Two-column layout collapses to single column on mobile |

---

## 🍽️ Menu Items

| Item | Price | Calories |
|---|---|---|
| 🍕 Pizza | $9.99 | 285 kcal |
| 🍗 Crispy Chicken | $7.49 | 320 kcal |
| 🍔 Cheese Burger | $8.99 | 490 kcal |
| 🍟 Fries | $3.49 | 365 kcal |
| 🥤 Soda | $2.49 | 150 kcal |

---

## 🎨 Design System

**Theme:** Dark neon / cyberpunk diner

**Typography:**
- Display: `Righteous` (Google Fonts) — used for headings, totals, badges
- Body: `DM Sans` (Google Fonts) — used for card info and UI text

**Color Palette:**

| Token | Value | Usage |
|---|---|---|
| `--bg` | `#0b0c10` | Page background |
| `--panel` | `#13151c` | Column panels |
| `--card` | `#1b1e2b` | Food cards |
| `--orange` | `#ff6b2b` | Menu accents, hover glows |
| `--yellow` | `#ffcc00` | Gradient highlights |
| `--teal` | `#00e5c3` | Order column, total price |
| `--pink` | `#ff3f7a` | Remove button, warnings |

---

## 📂 Project Structure

```
neonbite/
├── DragDemo.html     # All-in-one HTML/CSS/JS file
└── README.md         # This file
```

> The entire application lives in a **single self-contained HTML file** — no build tools, no npm, no bundler required.

---

## 🛠️ Getting Started

### Option 1 — Open directly in browser

```bash
# Just double-click DragDemo.html
# Or open via terminal:
open DragDemo.html          # macOS
start DragDemo.html         # Windows
xdg-open DragDemo.html      # Linux
```

### Option 2 — Serve with a local server (recommended)

```bash
# Python 3
python3 -m http.server 8080

# Node.js (npx)
npx serve .

# Then visit:
# http://localhost:8080/DragDemo.html
```

---

## 🗂️ Git Setup

```bash
# Initialize repository
git init

# Stage files
git add DragDemo.html README.md

# First commit
git commit -m "Initial commit: NeonBite drag-and-drop menu"

# Connect to remote (GitHub / GitLab / etc.)
git remote add origin https://github.com/your-username/neonbite.git
git branch -M main
git push -u origin main
```

---

## ⚙️ How It Works

### Drag & Drop
The app uses the native **HTML5 Drag and Drop API**. Each food card is set to `draggable="true"`. `dragstart`, `dragend`, `dragover`, `dragleave`, and `drop` events are wired to both the Menu and Order drop zones.

### State Management
Two plain JavaScript data structures manage state:
- `menuSet` — a `Set` of item IDs currently available in the menu
- `orderList` — an `Array` of item IDs currently in the order

On every add/remove, both zones are fully re-rendered from state.

### Animations
All animations are **CSS-only** (keyframes + transitions), except:
- **Confetti** — drawn frame-by-frame on an HTML5 `<canvas>` element using `requestAnimationFrame`
- **Floating particles** — DOM elements injected with randomized CSS animation durations

---

## 🌐 External Resources

| Resource | Usage |
|---|---|
| [Google Fonts](https://fonts.google.com) | Righteous + DM Sans typefaces |
| [Unsplash](https://unsplash.com) | Food photography (loaded via URL params) |

> No JavaScript libraries or CSS frameworks are used. Zero external JS dependencies.

---

## 🔧 Customization

**Add a new menu item** — extend the `ITEMS` array in the `<script>` block:

```js
{ id:'hotdog', name:'Hot Dog', price:4.99, cal:'290 kcal', emoji:'🌭',
  img:'https://images.unsplash.com/photo-XXXX?w=140&h=140&fit=crop' }
```

**Change the item cap** — find this line and update the number:

```js
if(orderList.length >= 5) { ... }
```

**Swap the color theme** — edit the CSS variables at the top of the `<style>` block:

```css
:root {
  --orange: #ff6b2b;
  --teal:   #00e5c3;
  /* etc. */
}
```

---

## 📋 Browser Support

| Browser | Support |
|---|---|
| Chrome 90+ | ✅ Full |
| Firefox 88+ | ✅ Full |
| Safari 14+ | ✅ Full |
| Edge 90+ | ✅ Full |
| IE 11 | ❌ Not supported |

---

## 📄 License

MIT — free to use, modify, and distribute.
