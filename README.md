BOOTSTRAP 5 – MODERN FORM GENERATOR (EN)

Overview

A single-file, multilingual, drag-and-drop form builder powered by Bootstrap 5.

Build forms from a palette, tweak properties, preview live, and export HTML/JS/JSON.

Languages: Hungarian, English, French, German.

Themes: Default, Glass, Soft, Bordered, Underline. Dark/Light UI toggle.

Features

Field palette: text, email, password, number, textarea, select, radio group, checkbox list, switch, date, time, range, file, heading, divider.

Properties: label, name, placeholder, required, help text, column width (1–12), rows (textarea), min/max/step (number/range), regex pattern, options (select/radio/checkbox), inline/multiple.

Live Preview (modal).

Export: HTML, JS, JSON. Import from JSON.

Optional AJAX submit example (fetch; auto-detect JSON/text).

Multilingual UI with a language switcher; auto-save (localStorage).

Five selectable form themes that are embedded into the exported HTML for easy drop-in use.

Quick Start

Open the HTML file in a browser.

Pick a language and a theme.

Add fields from the palette, then click a field to edit its properties.

Use Preview to test; use Export to copy/download HTML/JS/JSON.

Usage Tips

Reorder fields by dragging the “grip” on each field card.

Edit a field by clicking its card; the right panel shows all properties.

JSON tab: paste a saved JSON and click Load to restore a design.

Theme selector (left panel) updates both the preview and exported HTML.

Embedding (what you export)

HTML: A <form id="generatedForm" class="form-theme-…"> block plus a small <style> scoped to #generatedForm with the selected theme’s CSS.

JS (optional): The AJAX example attaches a submit handler, posts FormData to your endpoint, and shows a basic “Thank you!” alert.

Minimal backend example (PHP)

Return JSON with 200 OK. Always add server-side validation and CSRF in production.

<?php
header('Content-Type: application/json; charset=utf-8');
http_response_code(200);
echo json_encode(['ok'=>true,'message'=>'Thanks! We received your form.']);


JSON Schema (export format)

{
  "title": "Contact",
  "action": "/req/submit.php",
  "method": "POST",
  "ajax": true,
  "validate": true,
  "theme": "soft",
  "fields": [
    {
      "id": "fabc123",
      "type": "text|email|password|number|textarea|select|radio|checkbox|switch|date|time|range|file|heading|divider",
      "label": "Name",
      "name": "name",
      "placeholder": "Type your name…",
      "help": "We use this in our response.",
      "required": true,
      "col": 12,
      "rows": 3,
      "pattern": "^.{3,}$",
      "min": "",
      "max": "",
      "step": "",
      "inline": false,
      "multiple": false,
      "options": [{ "label": "Option 1", "value": "option1" }]
    }
  ]
}


Internationalization (i18n)

UI strings live in an i18n object: hu, en, fr, de.

The language selector persists the choice in localStorage ('fb_lang').

To add a new language, copy the en block and translate keys (including types).

Themes

Default — standard Bootstrap look.

Glass — translucent, saturated blur, vivid focus ring.

Soft — larger border-radius, gentle focus; rounded buttons.

Bordered — strong 2px borders; uppercase labels.

Underline — borderless inputs with only a bottom border.

Troubleshooting

“Invalid or unexpected token” during build:

Don’t put real line breaks inside single-quoted strings. Use \n or join with ['…','…'].join('\n').

Preview scripts not running:

Don’t inject <script> via innerHTML. Insert a real <script> element and set its textContent to the JS string.

“g is not defined”:

Comes from a broken regex replace (e.g., malformed /…/g inside a template). The current preview approach avoids this entirely.

Browser Support

Modern evergreen browsers (Chromium 100+, Firefox 100+, Safari 15.4+).

Internet Explorer is not supported.

Roadmap

Accent color picker for themes.

Masked inputs (phone, IBAN).

Validation profiles (common patterns).

reCAPTCHA / hCaptcha option.

Export “HTML only” and “JS only” modes.

License

MIT

Contributing

Fork → feature branch → PR.

Keep translations consistent (keys under i18n.xx and i18n.xx.types).

Keep functions short and readable; no build step required.
