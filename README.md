# Outliner

Drop a term's worth of course-outline PDFs and get back the dates that matter and how you're graded — a weekly calendar with exams, quizzes and due-date countdowns, a mark-breakdown calculator that handles "better of two schemes" grading, and a contact sheet with office hours.

Live demo: https://outliner-ebon.vercel.app

Everything runs in the browser. PDFs are read with pdf.js on your device, parsed by a local heuristic parser, and saved to IndexedDB. Nothing is uploaded anywhere; there is no server and no login.

Source code is in the private [`code`](https://github.com/danielkim1213/outliner-code) submodule.

## Run it

```sh
npm install
npm run dev        # http://localhost:5173
npm run build      # static output in dist/
npm run preview    # serve dist/ locally
```

Deploy `dist/` to any static host. `public/_redirects` (Netlify, Cloudflare Pages) and `vercel.json` rewrite all paths to `index.html` so deep links work.

## Flow

1. **Landing** — Get Started, or reopen a term already saved on this device.
2. **Upload** — name the term (defaults to Fall 2026), drop up to 8 text-based PDFs. Each file shows reading / saved / needs review, or a red X if no text layer could be read (scanned PDFs are not supported).
3. **Review** — one page per course. Pick your section when the outline lists several; every extracted fact (meetings, people, weights, dates) is editable. Mark schemes are all kept — the app always reports whichever gives the higher grade.
4. **Dashboard** — Schedule (week / day / list, clash badges, exams & quizzes, hourly due-date countdowns, add / edit / hide one-off and weekly events), Grades (per-scheme current / projected / max, "what do I need on X"), Course Info (instructors, TAs, copyable emails, office hours, where & when).

Term settings (top-right) let you switch terms, change dates and visible hours, and export / import a JSON backup.
