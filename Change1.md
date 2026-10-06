# Change 1: Add a Reading page

## Goal

Show recruiters the subjects that I read about, not only my jobs. A short reading list shows my interests: AI, business models, cities, careers with many disciplines, and science fiction. The list also gives topics for interviews.

## Changes

1. Add a new page, `reading.md`, at the address `/reading/`. The page uses the `page` layout. The page title is "Reading".
2. Add a new data file, `_data/reading.yml`, with five entries. Each entry has these fields: title, author, type, link, summary, personal note, and tags.
3. Show each entry as a card. Use the same style as the Work Experience page:
   - A type label (Essay or Book).
   - The title, with a link to the source. The link uses `rel="noopener"`.
   - The author, the summary, and the personal note (in italics).
   - The tags, with the same style as the tags on the Work Experience page.
4. Add a line at the end of the page with a link to my Goodreads profile.
5. Add "Reading" to `_data/navigation.yml`, between Work Experience and Contact. Thus the link shows in the menu on each page.

**Result:** To add a new essay or book, edit one YAML file. Do not edit HTML.

## Not included

- No images.
- No JavaScript.
- No external embedded content.
- No changes to the text of other pages.

## Checks

1. In Preview, make sure that "Reading" shows in the menu.
2. Make sure that the menu marks "Reading" as the current page on the Reading page.
3. Make sure that the page shows five cards.
4. Make sure that each link opens the correct source.
5. Make sure that the layout is correct at 375 px and 1280 px.
6. After the merge, make sure that the page is live at <https://patronofalltrades.github.io/reading/>.
7. Make sure that `sitemap.xml` includes the page.
8. Make sure that the Lighthouse score is 90 or more in each of the four categories.

## Branch and commit

- **Branch:** `readings`
- **Commit message:** "Add Reading collection page with curated essays and books"
- **Pull request:** [#1](https://github.com/patronofalltrades/patronofalltrades.github.io/pull/1)
