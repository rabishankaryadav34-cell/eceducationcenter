# AGENTS.md

## Project overview
Static single-page site for a Nepali Teaching License exam preparation center ("Education Center"). No build step, no framework — plain HTML/CSS/JS.

## Architecture
- `index.html` — entire site: markup, inline `<style>`, and inline quiz-scoring `<script>`. The mock test is scored client-side by comparing radio input `value="correct"` attributes.
- `thank-you.html` — redirect target for the admission form.
- Netlify Forms: the admission form uses `name="admission"` with `data-netlify="true"`, a honeypot (`bot-field`), and `action="/thank-you"`. Form registration happens at deploy time by HTML parsing — no skeleton file needed since the site is static.

## Conventions
- All user-facing copy is in Nepali (Devanagari); brand name stays in English.
- Colors: primary `#0c4a60` (dark teal), accent `#efd07b` (gold). Keep new UI consistent with these.
- No build commands; deployment serves the static files directly.

## Netlify
- Netlify Forms feature is enabled (`admission` form).
