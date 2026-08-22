# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Repository purpose

This is a **GitHub profile repository** — the repo name (`abusayed0206`) matches the GitHub username, so `README.md` renders directly on the owner's GitHub profile page (https://github.com/abusayed0206). There is no application code, build system, linter, or test suite. The repository is:

- `README.md` — the profile content: a dual-audience technical hub combining a Civil/Structural Engineering academic background (education, research, publications, engineering software skills) with a software portfolio (shipped Windows/web apps), plus reviews and contact info.
- `flag.png` — Bangladesh flag image, linked at the bottom of the README.
- `NXT_bkash.png` — image asset referenced in the README.
- `sayed.asc` — PGP public key block for `hello@sayed.page`.

"Development" here means editing `README.md` directly and, when needed, adding image assets referenced from it. Nothing to compile, lint, or test.

## README structure

1. **Header** — name, degree tagline, one-line specialization, links to `sayed.page` (full academic CV) and `sayed.app` (full project catalog).
2. **Jump to** — anchor nav; keep in sync whenever a `##` heading is added, renamed, or removed.
3. **Civil & Structural Engineering Background** — Education, Research Interests, Notable Academic Work, Experience, Certifications, Engineering Skills. A summary, not the full CV — `sayed.page` is the source of truth for detail.
4. **Project Portfolio & Statistics** — Microsoft Store user count and a Cloudflare traffic snapshot, followed by three tables: **Windows Applications**, **Web Applications & Extensions**, **Other Projects**.
5. **User Reviews** — short testimonials, each attributed with a name/source and date.
6. **Contact Information** — split into "Reply Expected (Two-Way)" (email, Signal, WhatsApp), "Receiver Only" (app/product issue inbox), and "Professional Profiles" (LinkedIn, ORCID, ResearchGate, Kaggle).
7. **Footer** — `_Last Updated: <Month Day, Year>_` line, a closing Bengali line, and the flag image.

## Editing guidance

- **Tables** (Windows Applications / Web Applications & Extensions / Other Projects) use columns `Name | Description | Link`. Match the existing badge/link style per table (Microsoft Store badge for Windows apps, `[Visit Web App]` for web apps, `[View Repository]`/`[View Crate]` for Other Projects). Append new rows at the bottom — table order is roughly chronological, don't re-sort existing rows.
- **Cross-verify before adding anything** — fetch the actual target URL and confirm it resolves to the correct product; base descriptions on what the live listing says today, not on stale or user-supplied claims; don't invent numbers (users, downloads, etc.) that aren't confirmed by the source.
- **Store listings and `sayed.page` sit behind Cloudflare bot protection** — plain `WebFetch` only returns a bare `<title>` or a 403. Use `curl` with a real browser `User-Agent` instead: for Store listings, read the `<meta name="description">`/`og:description` tags from the raw HTML; for `sayed.page`, request the markdown export (e.g. `https://sayed.page/index.md`, or `Accept: text/markdown` on other routes) for the structured CV content.
- **`sayed.page` is authoritative** for education, research, publications, academic projects, certifications, and engineering skills — cross-check any civil-engineering claim against it rather than inventing or guessing. Keep the README's Civil & Structural Engineering Background section a concise summary that links out to `sayed.blog` write-ups and `public.sayed.page` report PDFs, not a full CV dump.
- **GitHub repo metadata** can be checked without auth via `curl https://api.github.com/repos/abusayed0206/<repo>` (or `.../users/abusayed0206/repos`) — use this to confirm a repo exists and what it's about before linking it in Other Projects.
- **Testimonials from private channels** (email, DM, etc.) must have the sender's personal identifying info obfuscated before publishing (e.g. mask an email as `ah********83@gmail.com`) — never paste a raw private address into the public README.
- **Footer date**: bump `_Last Updated: <Month Day, Year>_` whenever a substantive content change is made.
- The Cloudflare traffic table is a manually-pasted snapshot with a "Last checked" date beneath it — update only when the user supplies a new snapshot, never compute or estimate it.
