# Change 1: Add a Reading collection page

## Goal
Show recruiters what I read and think about, not only where I have worked. A short, curated reading list signals my interests (AI, business models, cities, multi-disciplinary careers, science fiction) and gives conversation starters for interviews.

## What will change
- New page `reading.md` at `/reading/` titled "Reading", using the existing `page` layout.
- New data file `_data/reading.yml` holding the five entries (title, author, type, link, one-line summary, my personal note, tags), so I can add a new read later by editing one YAML file instead of HTML.
- Each entry renders as a card in the existing style: type label (Essay or Book), title linked to the source (opens the original, with `rel="noopener"`), author, summary, my note in italics, and the same outlined tag chips used on Work Experience.
- A closing line linking to my Goodreads profile for the full list.
- "Reading" added to `_data/navigation.yml` between Work Experience and Contact, so it appears in the header on every page.

## Out of scope
No images, no JavaScript, no external embeds, no changes to other pages' content.

## How I will check it
- Preview: the Reading link appears in the navigation and is highlighted on the Reading page; all five cards show; every link opens the right source.
- Layout works at 375px and 1280px wide.
- After merging: the page is live at https://patronofalltrades.github.io/reading/ and listed in sitemap.xml; Lighthouse stays at 90+ in all four categories.

## Branch and commit
- Branch: `readings`
- Commit message: "Add Reading collection page with curated essays and books"
