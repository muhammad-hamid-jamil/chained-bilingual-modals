# 🌐 Chained Bilingual Modals  EN/AR

> **Production-ready**, zero-dependency modal component with automatic English/Arabic language detection, RTL support, and responsive design. Drop-in embed for any website.

[![Author](https://img.shields.io/badge/Author-Muhammad%20Hamid-D4AF37?style=flat-square)](mailto:muhammadhamidjamil0@gmail.com)
[![Full Stack Dev](https://img.shields.io/badge/Role-Full%20Stack%20Dev-0A0A0A?style=flat-square)](tel:+923317900924)
[![License](https://img.shields.io/badge/License-MIT-blue?style=flat-square)](LICENSE)

---

## What Are These Modals?

Two **chained announcement modals** that appear on page load:

| Modal | Purpose | Use Case |
|-------|---------|----------|
| **Modal 1** | Important notice / Branch closure / Service update | Announcements, policy changes, location updates |
| **Modal 2** | New feature / Online service / CTA | Promotions, feature launches, signup flows |

**Flow:** Page load → Modal 1 → User closes → Modal 2 auto-opens → User closes → Done

---

## Features

-  **Bilingual (EN/AR)**  Auto-detects from URL (`/ar-ae`) or `lang="ar"` / `dir="rtl"`
-  **RTL Layout**  Proper Arabic right-to-left with Tajawal font
-  **Responsive**  Scrollable body, no overflow on 100% zoom or mobile
-  **Zero Dependencies**  Pure HTML, CSS, JS — no jQuery, React, or frameworks
-  **Copy-Paste Ready**  Single-file embed for Webflow, WordPress, Shopify, PHP, static sites
-  **Accessible**  `role="dialog"`, `aria-modal`, Escape key, click-outside to close
-  **Google Translate**  Suppresses browser translation popup
-  **Customizable**  CSS variables, `data-i18n` for translations

---

##  Who Can Use This?

| Audience | Use Case |
|----------|----------|
| **Clients / Businesses** | Announce branch closures, service updates, promotions, new features |
| **Developers** | Quick embed for any project; template for custom modals |
| **Agencies** | White-label component for client websites |
| **Startups** | Fast MVP for announcement flows without building from scratch |

---

## How to Add to Your Site

### 1️⃣ Webflow

1. Add **Embed** element (footer, hero, or any div)
2. Paste entire contents of `form.html`
3. Publish

**Pro tip:** Use Webflow’s locale system — Arabic pages at `/ar-ae` will auto-show Arabic content.

---

### 2️⃣ WordPress

**Option A -> Custom HTML block**

1. Add **Custom HTML** block
2. Paste `form.html` content

**Option B -> Theme / child theme**

```php
// In footer.php or a template
<?php echo file_get_contents(get_template_directory() . '/path/to/form.html'); ?>
```

**Option C -> Shortcode**

```php
// functions.php
function bilingual_modals_shortcode() {
    ob_start();
    include get_template_directory() . '/modals/form.html';
    return ob_get_clean();
}
add_shortcode('bilingual_modals', 'bilingual_modals_shortcode');

// Use in post/page: [bilingual_modals]
```

---

### 3️⃣ Shopify

1. **Theme → Edit Code**
2. Open `theme.liquid` or `base.liquid`
3. Add before `</body>`:

```liquid
{% include 'bilingual-modals' %}
```

4. Create `snippets/bilingual-modals.liquid` and paste `form.html` content

---

### 4️⃣ PHP / Laravel

```php
// Blade
@include('components.bilingual-modals')

// Or raw PHP
<?php include 'path/to/form.html'; ?>
```

---

### 5️⃣ Static HTML / Any CMS

Copy paste the content between the `<!-- PASTE EVERYTHING BELOW -->` comment and `</body>` into your HTML.

---

## ⚡ Quick Customization

| What to Change | Where |
|----------------|-------|
| **Contact info** | Search for `+923317900924`, `muhammadhamidjamil0@gmail.com` |
| **Logo / Brand** | `.age-logo-text` or replace with `<img src="…">` |
| **Colors** | `:root` CSS variables (`--age-gold`, `--age-black`, etc.) |
| **Text / Translations** | `var t = { en: {...}, ar: {...} }` in script |
| **Links** | `href` on `.age-link-branch`, `.age-link-wps` |

---

## 📁 File Structure

```
table/
├── form.html    # Main component (modals + script)
├── LICENSE
└── README.md
```

---

## 🔧 Technical Details

- **Language detection:** `pathname.indexOf('/ar-ae')` or `html lang="ar"`
- **RTL:** `dir="rtl"` + `age-rtl` class on modals
- **Scroll:** `max-height: calc(100vh - 32px)` + `overflow-y: auto` on body
- **Animation:** CSS `ageSlideUp`, `ageFadeIn`

---

## 📞 Contact

**Muhammad Hamid** — Full Stack Developer

- 📧 [muhammadhamidjamil0@gmail.com](mailto:muhammadhamidjamil0@gmail.com)
- 📱 [+923317900924](tel:+923317900924)

---

## 📄 License

MIT -> Use freely. Attribution appreciated.
