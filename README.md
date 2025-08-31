# Bootstrap 5 – Modern Form Generator

A single-file, multilingual, drag-and-drop form builder powered by **Bootstrap 5**. Build forms from a palette, edit properties, preview live, and export **HTML / JS / JSON**. Includes five selectable themes and a Dark/Light UI toggle.

> Languages: **English**, **Hungarian**, **French**, **German**

---

## Table of Contents
- [Features](#features)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Export & Embedding](#export--embedding)
- [JSON Schema](#json-schema)
- [Internationalization (i18n)](#internationalization-i18n)
- [Themes](#themes)
- [Troubleshooting](#troubleshooting)
- [Browser Support](#browser-support)
- [Roadmap](#roadmap)
- [Contributing](#contributing)
- [License](#license)

---

## Features
- **Drag & drop** field palette:
  - text, email, password, number, textarea, select, radio group, checkbox list, switch, date, time, range, file, heading, divider
- **Properties panel**:
  - label, name, placeholder, required, help text, column width (1–12), rows (textarea), min/max/step (number/range), regex pattern, options (select/radio/checkbox), inline/multiple
- **Live Preview** in a modal
- **Export**: HTML, JS, JSON & **Import** from JSON
- **AJAX submit example** (fetch; auto-detect JSON/text response)
- **Multilingual UI** (EN/HU/FR/DE) with language switcher
- **Five themes**: Default, Glass, Soft, Bordered, Underline
- **Dark/Light** UI toggle
- **Auto-save** of editor state (localStorage)

---

## Quick Start
1. Clone or download the repository.
2. Open the main HTML file (e.g., `index.html`) in your browser.
3. Choose a **language** and **theme**.
4. Drag fields from the **palette** and edit them in the **properties** panel.
5. Use **Preview** and then **Export** (HTML/JS/JSON).

> Tip: If you prefer a local server, try `npx serve` or VS Code **Live Server**.

---

## Usage
- **Add a field** by clicking it in the palette (or drag & drop).
- **Reorder** fields using the grip icon on each field card.
- **Edit** a field by clicking its card; the right panel shows all options.
- **Export** from the right tabs (HTML / JS / JSON).
- **Import** by pasting JSON into the JSON tab and clicking **Load**.
- **Theme** selector (left panel) applies to Preview and exported HTML.

---

## Export & Embedding

### 1) HTML (drop-in)
The generator produces a `<form id="generatedForm" class="form-theme-…">` plus a scoped `<style>` block targeting `#generatedForm` for the selected theme.

```html
<!-- ===== Generated with FormBuilder (Bootstrap 5) ===== -->
<style>/* theme-specific CSS injected by the generator */</style>
<form id="generatedForm" class="form-theme-soft" action="/req/submit.php" method="POST">
  <h4 class="mb-3">Contact</h4>
  <!-- generated rows and fields -->
  <div class="mt-3 d-flex gap-2">
    <button class="btn btn-primary" type="submit">Send</button>
    <button class="btn btn-outline-secondary" type="reset">Reset</button>
  </div>
</form>
