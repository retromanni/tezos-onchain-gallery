# SECURITY.md

## Security Overview

This project is a **static, client-side HTML gallery** that reads publicly available data from the Tezos blockchain via the TzKT API.

There is:

* No backend server
* No database
* No authentication system
* No wallet connection
* No form input or user submission

As a result, the attack surface is intentionally minimal.

---

## What This Template Does

* Fetches NFT metadata from the TzKT API
* Renders on-chain media (images, SVG, HTML NFTs)
* Displays metadata (name, description, attributes, owner)
* Runs entirely in the user's browser

---

## Built-in Security Measures

### 1. Content Security Policy (CSP)

A strict CSP is defined in the HTML:

* Blocks all external scripts
* Restricts network requests to TzKT only
* Disallows form submissions
* Prevents base tag injection
* Restricts frames and images to safe sources

Inline scripts are allowed (`'unsafe-inline'`) **only because this is a single-file app**, and:

* No user input is executed as code
* No dynamic script injection is used

---

### 2. Safe Data Handling

All blockchain data is treated as untrusted input.

Protections include:

* `textContent` used instead of `innerHTML` where possible
* `escHtml()` used to sanitize displayed strings
* No use of `eval()` or dynamic code execution

---

### 3. Sandboxed Execution for HTML NFTs

Interactive NFTs (`data:text/html`) are rendered in iframes with:

```html
sandbox="allow-scripts"
```

This ensures:

* No access to the parent page
* No access to cookies or storage
* No same-origin privileges

---

### 4. SVG Isolation

SVGs are rendered via `blob:` URLs inside sandboxed iframes to:

* Prevent inline script execution in the main document
* Allow animation safely
* Isolate potentially malicious SVG content

---

### 5. Network Restrictions

All API requests go through a validated helper:

* Only allows requests to:

  * https://api.tzkt.io
* Blocks unexpected origins (prevents SSRF-style misuse)

---

### 6. Resource Limits

To prevent abuse or crashes:

* Maximum token processing limit
* Maximum data URI size limit
* Stricter limit for HTML NFTs

Oversized or malformed assets are skipped.

---

### 7. Rate Limiting Protection

Owner lookups are:

* Throttled
* Queued
* Retried with backoff on HTTP 429

This prevents API abuse and improves reliability.

---

## What This Template Does NOT Protect Against

This project does **not** provide protection against:

* Malicious content embedded inside NFTs themselves
* Browser vulnerabilities
* Compromised third-party APIs (e.g. TzKT)
* Social engineering via NFT metadata

Users should treat all on-chain content as **untrusted media**.

---

## Responsible Usage

If you modify this template:

* Do not remove the CSP without understanding the risks
* Do not introduce `eval()` or dynamic script execution
* Be cautious when adding external scripts or APIs
* Maintain sandboxing for iframe content

---

## Reporting Security Issues

If you discover a vulnerability or security concern:

1. Do **not** open a public issue immediately
2. Contact the maintainer privately (via GitHub or other contact method)
3. Provide:

   * Description of the issue
   * Steps to reproduce
   * Potential impact

---

## Disclaimer

This software is provided **“as is”**, without warranty of any kind.

Use at your own risk.
