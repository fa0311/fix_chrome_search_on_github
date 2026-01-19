# fix_chrome_search_on_github

This repository provides a **stable, reliable workaround** for a GitHub UI bug on Chrome, as shown in the screenshot below. The fix is applied via a **user style (User CSS)** and is designed to work consistently once enabled.

![screenshot](docs/img/1691174639670.png)

---

## What this does

When GitHub’s search pages break in Chrome (overlapping layouts, an unusable page, unexpected layers covering the UI, etc.), this user style restores a normal, usable layout.

This fix works by ensuring only the intended top-level content container remains visible, preventing the broken/duplicated top-layer containers from interfering with the page.

---

## Installation (Recommended: Stylus)

Since Chrome does not provide a convenient built-in way to apply per-site CSS, using a dedicated extension is the easiest and most stable approach.

### 1) Install Stylus
Install the **Stylus** browser extension from the Chrome Web Store.

### 2) Create a new style for GitHub
1. Click the Stylus icon
2. Choose **New style**
3. Set the target to `github.com` (or restrict it to search pages only — recommended)
4. Paste the CSS below
5. Save and enable

---

## CSS

```css
body>div:nth-child(n+2) {
    display: none;
}

---

## Update (Added later)

**This issue has already been fixed on GitHub’s side.**

This repository (and the User CSS snippet) is kept for historical reference and for anyone who might still encounter similar rendering regressions in specific environments (e.g., older Chrome builds, cached assets, enterprise-managed browsers, etc.).

If you are no longer seeing the bug, you can safely disable or remove the style.
