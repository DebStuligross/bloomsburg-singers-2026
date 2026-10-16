# Bloomsburg Singers — Project Context for AI Agents

## What this is

A static rehearsal-resource website for the Bloomsburg Singers choral group, maintained by Deb Stuligross. One concert season per year. The site is the information hub for singers heading into the concert: repertoire notes, upcoming activities, logistics, and a weekly digest of the director's email.

- **Live URL:** `https://debstuligross.github.io/bloomsburg-singers-2026`
- **Repo:** `DebStuligross/bloomsburg-singers-2026` on GitHub
- **Deployment:** GitHub Pages — pushing to `master` deploys automatically. No build step.
- **Stack:** Single-page static site. `index.html` + `styles.css`. No frameworks, no npm, no bundler.

---

## File structure

```
index.html       — the entire site (one file, ~1500 lines)
styles.css       — all styles
AGENTS.md        — this file
.gitignore
```

---

## CSS class conventions (don't rename these)

| Class | Purpose | Visual |
|-------|---------|--------|
| `.focus-note` | Director's rehearsal note for a piece | Red left-border callout |
| `.focus-note.praise` | Pure compliment from the director | Green left-border callout |
| `.focus-label` | Date/label inside a focus note | Small caps header |
| `.call-time` | "Next up" pill in the page header | Red pill badge |
| `.verse-notes` / `.verse-row` | Verse-by-verse instructions | Compact table-like rows |
| `.cut-label` | Marks a cut verse or section | Red strikethrough badge |
| `.section-header` | Concert program section divider in the repertoire list | Bold separator row |
| `.activities-table` | Upcoming rehearsals/events table | Styled table |
| `.checklist` | Singer checklist bullets | Styled list |

---

## Weekly update workflow (recurring task)

Each week, the director Joe Stuligross sends a "This Week in Bloomsburg Singers" email. Updates to `index.html` follow this pattern:

1. **Focus notes** — Add Joe's piece-specific notes as `.focus-note` callouts inside the relevant `<li>` in the repertoire list. Use `.focus-note.praise` for pure compliments (no critique). Include a `<span class="focus-label">` with "Joe's note — [Month Day]" or "Joe's focus — [Month Day]". Decide per piece whether to replace the prior week's note or stack a new dated one on top.

2. **Email Digest** — Add the full email text as a new `<details>` block at the top of the `#emails` section (newest first).

3. **"Next up" pill** — Update the `.call-time` pill in the header. It's a rolling pointer ("Next up: Rehearsal — Tues, June 10 · 7:00 PM"), not a standing call time. Advance it as events pass.

4. **Upcoming Activities table** — Update the `#upcoming` table. Drop past rehearsals; add newly confirmed events.

5. **Singer Checklist** — Update `#checklist` if Joe adds or changes instructions.

6. **Cuts** — Apply confirmed cuts in the repertoire list (add `.cut-label` to the verse row) and remove the cut piece's `video_ids` entry from the "Play All" YouTube URL in the playlist note.

---

## Privacy rule (critical)

**Never put personal contact information on the page:**
- No personal email addresses
- No personal/cell phone numbers

**Allowed:**
- Organizational, church, or business phone numbers
- Sign-up form links (Google Forms, etc.)

---

## Analytics

Microsoft Clarity is wired into the `<head>` of `index.html` (project ID: `x5i9ovvwwa`). Do not remove or modify this script.

---

## Repo owner

Deb Stuligross (`debstuligross@gmail.com`). Do not commit or push without her instruction.
