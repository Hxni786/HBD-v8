# 🎂 Happy Birthday — Interactive Web Experience V8

> A heartfelt, animated birthday greeting web app that delivers a personalized, multi-step surprise experience through beautiful UI transitions, typewriter effects, and a curated music backdrop.

---

## ✨ Features

| Feature | Description |
|---|---|
| 🎁 **Gift Reveal Animation** | An animated gift box greets the visitor; clicking it triggers the full experience |
| 🎵 **Background Music** | Auto-plays a birthday song once the gift is opened |
| ✍️ **Typewriter Messages** | Sequential birthday messages animate in with a lifelike typewriter effect |
| 🖼️ **Dynamic Wallpaper** | Background transitions and zooms to match each message stage |
| 🧸 **Animated Stickers** | Cute GIF stickers cycle through the experience to keep the mood festive |
| 💬 **Personalized Greeting** | Prompts the visitor for their name and tailors the greeting dynamically |
| 🎊 **Interactive Icons** | Four tappable emoji icons (🎂🎁🥳💖) must all be tapped to progress |
| 📱 **Mobile-Responsive** | Fully responsive layout that works on desktop and mobile browsers |
| 🍬 **SweetAlert2 Popups** | Polished modal dialogs for name input, confirmations, and celebration alerts |

---

## 📁 Project Structure

```
HAPPY-BIRTHDAY-V8/
│
├── index.html                    # Main entry point — layout & inline script logic
├── style.css                     # Full styling, animations, and responsive layout
├── a.js                          # Core JavaScript — flow control & typewriter sequences
│
├── Valentine-Surprise.png        # Gift box image (click-to-open trigger)
├── GiftBox.png                   # Alternative gift box asset
├── helo.png                      # Greeting image asset
├── v.png                         # Visual decoration asset
├── r.jpg                         # Background wallpaper image
├── 4a0a9d924fd271737c0813852160ae89.jpg  # Additional image asset
│
├── y2mate (mp3cut.net).mp3       # Background birthday music
└── 6364310540963.mp4             # Video asset
```

---

## 🚀 Getting Started

### Prerequisites

No build tools or server setup required. This is a **pure front-end** project — just open it in any modern browser.

### Running Locally

1. **Clone or download** this repository to your local machine.
2. Open `index.html` directly in your browser:

   ```bash
   # On Windows — just double-click index.html, or:
   start index.html

   # On macOS / Linux:
   open index.html
   ```

3. The experience begins immediately on page load.

> **Note:** Some GIF stickers are loaded from external CDN URLs (Tenor, GitHub Pages). An active internet connection is required for those assets to appear.

---

## 🎬 How It Works — User Flow

```
[Page Load]
    │
    ▼
[Gift Box Displayed] ──► User clicks gift
    │
    ▼
[Music Starts + Gift Explodes (scale animation)]
    │
    ▼
[SweetAlert2 Popup] ──► "What's your beautiful name?"
    │
    ▼
[Typewriter: "Happy Birthday, <Name>!"]
    │
    ▼
[Message Card Appears] ──► TypeIt animates opening message
    │
    ▼
[Emoji Icons (🎂🎁🥳💖)] ──► All 4 must be tapped to continue
    │
    ▼
[Sequential Typed Messages] ──► Multiple heartfelt birthday messages
    │
    ▼
[Confirmation Dialog] ──► "Celebrate in style?"
    │
    ▼
[Final Redirect] ──► ./love/index.html (bonus birthday surprise page)
```

---

## 🛠️ Technologies Used

| Technology | Purpose |
|---|---|
| **HTML5** | Page structure and layout |
| **CSS3** | Animations, transitions, glassmorphism effects |
| **Vanilla JavaScript** | Flow control, DOM manipulation, event handling |
| [**SweetAlert2 v11**](https://sweetalert2.github.io/) | Beautiful modal dialogs and alerts |
| [**TypeIt v8.7**](https://typeitjs.com/) | Realistic typewriter text animations |
| [**Google Fonts**](https://fonts.google.com/) | `Archivo`, `Dancing Script`, `Pacifico`, and more |

---

## 🎨 Design Highlights

- **Glassmorphism UI** — Semi-transparent cards with `backdrop-filter: blur()` for a modern frosted-glass look
- **Layered Background** — A gradient overlay (`#ffe1e1` → `#ff217d`) blended over a background image with smooth zoom transitions
- **CSS Keyframe Animations** — Custom animations: `heartMove`, `aniopa`, `rts`, `rto`, `jj` for stickers, icons, and transitions
- **Responsive Sticker Cycle** — Six sticker GIFs rotate progressively through the experience stages
- **Dark Blockquote Cards** — Message cards use `rgba(0,0,0,0.73)` background with rounded corners and white border glow

---

## 🔧 Customization Guide

### Change the Recipient's Name Prompt
In `index.html`, update the SweetAlert title:
```js
title: "What's your beautiful name?",
```

### Change Birthday Messages
Edit the `<p>` tags inside the `<blockquote>` in `index.html`:
```html
<p id="kalimat">Happy Birthday, gorgeous! Today is all about celebrating you.</p>
<p id="pesan2">You shine brighter every year! ✨</p>
<!-- ...and so on -->
```

### Change Background Music
Replace `y2mate (mp3cut.net).mp3` with your own `.mp3` file and update the `src` in:
```html
<audio src="./your-song.mp3" id="linkmp3" class="sembunyi"></audio>
```

### Change the Gift Image
Replace `Valentine-Surprise.png` with your preferred image and update:
```html
<img src="./your-image.png" alt="Open Gift Button" />
```

### Change the Final Redirect URL
In `a.js`, update the `menuju()` function:
```js
async function menuju(){
  await swals.fire('Yay!', 'Your message here!', 'success');
  window.location = "./your-next-page/index.html";
}
```

---

## 📦 Dependencies (CDN — No Install Needed)

All dependencies are loaded via CDN and require no local installation:

```html
<!-- SweetAlert2 -->
<script src="https://cdn.jsdelivr.net/npm/sweetalert2@11.0.19/dist/sweetalert2.all.min.js"></script>

<!-- TypeIt -->
<script src="https://unpkg.com/typeit@8.7.0/dist/index.umd.js"></script>

<!-- Google Fonts -->
<link href="https://fonts.googleapis.com/css2?family=Dancing+Script&display=swap" rel="stylesheet" />
```

---

## 🌐 Browser Compatibility

| Browser | Supported |
|---|---|
| Google Chrome | ✅ Full support |
| Microsoft Edge | ✅ Full support |
| Mozilla Firefox | ✅ Full support |
| Safari (iOS/macOS) | ✅ Full support |
| Opera | ✅ Full support |

> Requires a browser with support for CSS `backdrop-filter`, `async/await`, and ES6+.

---

## 📄 License

This project is open for **personal use**. Feel free to fork and customize it to create your own personalized birthday surprises. 💖

---

## 💡 Tips

- For the best experience, open on a mobile device and share the link directly with the birthday person.
- Make sure all local assets (`r.jpg`, `.mp3`, `.png`) are in the same directory as `index.html`.
- If hosting online (GitHub Pages, Netlify, Vercel), no additional configuration is needed — just upload the folder.

---

<div align="center">
  Made with 💖 to make someone's birthday a little more magical.
</div>
