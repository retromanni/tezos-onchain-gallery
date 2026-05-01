# On-Chain Tezos Art Gallery (Static HTML Template)

A fully self-contained HTML gallery that displays **your minted Tezos NFTs directly from the blockchain** — no backend, no build tools, no dependencies.

Designed to be:

* Easy to use (edit one line to get started)
* Fully on-chain (no IPFS or external media required)
* Fast and secure (with strict Content Security Policy)
* Customisable via clearly labelled sections in the code

---

## ✨ What this is

This template:

* Fetches your minted tokens from TzKT
* Groups them by collection
* Displays them in a responsive grid
* Supports:

  * PNG / GIF / JPEG
  * SVG (including animation)
  * Interactive HTML NFTs
* Includes:

  * Zoom viewer
  * Lazy loading
  * Infinite scroll
  * Owner lookup
  * Clean UI with neon theme

No frameworks. No installs. Just open the file.

---

## 🚀 Quick Start (2 minutes)

1. Download the HTML file
2. Open it in a code editor
3. Find this line:

```js
const WALLET = "tz1REPLACE_WITH_YOUR_ADDRESS";
```

4. Replace it with your wallet:

```js
const WALLET = "tz1YourRealWalletAddress";
```

5. Save the file
6. Open it in your browser

Done.

---

## 🎨 Customising the Design (Easy)

### 1. Change colours (global theme)

At the top of the `<style>` section:

```css
:root {
  --neon-pink:    #ff2d78;
  --neon-cyan:    #00f0ff;
  --neon-yellow:  #ffe600;
  --dark-bg:      #07000f;
  --card-bg:      #0d0020;
}
```

Change these values to instantly restyle the entire site.

Example:

```css
--neon-cyan: #00ff88;
```

---

### 2. Change fonts

In `<head>`:

```html
<link href="https://fonts.googleapis.com/css2?family=Orbitron&family=Share+Tech+Mono&display=swap" rel="stylesheet">
```

Replace with any Google Font.

Then update:

```css
font-family: 'Orbitron', sans-serif;
```

---

### 3. Edit the header text

Find:

```html
<div class="header-sub">
  fully on-chain / tezos blockchain / pixel art
</div>
```

Change to anything you want.

---

### 4. Footer link

Find:

```html
<a href="https://your-homepage-url.com">
```

Replace with your website or social link.

---

## ⚙️ Configuration Options

Inside the **CONFIGURATION section** in the script:

---

### Wallet address

```js
const WALLET = "tz1...";
```

This is the only required change.

---

### Hide specific collections

```js
const EXCLUDED_CONTRACTS = new Set([
  "KT1...",
]);
```

Add contract addresses you don’t want shown.

---

### Burned tokens (automatic)

Tokens sent to the burn address are automatically hidden:

```js
const BURN_ADDRESS = "tz1burnburn...";
```

Do not change this.

---

## 🧠 How the comments help you

The file is heavily commented so you can safely edit it even with minimal coding experience.

Look for sections like:

```
CONFIGURATION — edit this section
```

```
COLOURS — change these to restyle the entire site
```

```
FOOTER TEXT — update this link
```

These are **safe zones** to modify.

---

## ⚠️ What NOT to change (unless you know what you're doing)

Avoid editing:

* `safeFetch()`
* CSP meta tag
* Lazy loading logic
* Zoom modal logic
* Owner fetch queue

Changing these may break:

* security
* performance
* rendering

---

## 🌐 Deploying Your Site (Free)

### Option 1 — GitHub Pages

1. Create a repository
2. Upload your HTML file as `index.html`
3. Go to:

   * Settings → Pages
4. Enable Pages

Your site will be live at:

```
https://yourusername.github.io/repo-name
```

---

### Option 2 — Netlify (easiest)

1. Go to Netlify
2. Drag & drop your HTML file
3. Done

You’ll get a live URL instantly.

---

### Option 3 — Cloudflare Pages

1. Upload project
2. Deploy

Very fast global hosting.

---

## 🔗 Using your Tezos identity

You can link your site to your `.tez` name:

Using Tezos Domains:

* Add your site URL to your domain profile
* Use it as your on-chain identity link

---

## 🔒 Security Notes

* Strict Content Security Policy
* Only allows:

  * TzKT API
  * On-chain media
* Blocks:

  * external scripts
  * unsafe injections
* All user data is sanitized (`textContent`, no `eval`)

---

## 📦 What this template does NOT do

* No minting
* No wallet connection
* No marketplace features
* No backend storage

It is **display only**.

---

## 🧩 Advanced Customisation (optional)

If you want to go further:

* Change card layout → `.card` CSS
* Modify grid → `.grid`
* Adjust zoom behaviour → `computePixelPerfectSize()`
* Add filters → extend grouping logic

---

## 📄 Licence

MIT — free to use, modify, and distribute.

---

## 🙌 Credits

Built for the Tezos on-chain art ecosystem.

---

## 💡 Tip

If something breaks:

* Check browser console (F12)
* Undo recent changes
* Stick to commented sections

---

This template is designed so that:

> **you can safely customise it without needing to be a developer**

---
