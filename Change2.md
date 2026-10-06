# Change 2: Add a "Download CV" button

## Goal

Let recruiters get my CV with one click from each page. They do not have to send an email to me first. With this change, the site becomes a tool for recruitment, not only a profile.

## Changes

1. Add my CV as `assets/files/Hanif-Ramadhan-CV.pdf`.
   - The phone number is removed for privacy.
   - The email address and the LinkedIn address stay in the CV.
2. Add a new include file, `_includes/cv-button.html`. It shows a link with a button style and the text "Download CV (PDF)". The link:
   - Uses the `download` attribute. Thus the browser saves the file.
   - Uses the `relative_url` filter for the file address.
   - Has an accessible label that gives the file type and the file size.
3. Put the button in the top menu, next to Contact. Thus the button shows on each page.
4. Add the setting `cv_file` to `_config.yml`. To replace the CV, upload a new PDF. If the file name changes, change this one line.
5. Use this button style:
   - Black background and white text.
   - Square corners.
   - A visible focus ring for keyboard users.
   - Colors with sufficient contrast for accessibility.

## Not included

- No JavaScript.
- No count of downloads.
- No changes to the text of the pages.

## Checks

1. In Preview, make sure that the button shows in the menu on each page.
2. Make sure that you can go to the button with the `Tab` key.
3. Make sure that the button downloads the PDF.
4. Make sure that the layout is correct at 375 px and 1280 px.
5. After the merge, make sure that <https://patronofalltrades.github.io/assets/files/Hanif-Ramadhan-CV.pdf> opens the file.
6. Make sure that the Lighthouse score is 90 or more in each of the four categories.

## Branch and commits

- **Branch:** `add-cv-download`
- **Commit messages:**
  - "Add Download CV button to Home and Contact pages"
  - "Move compact CV download button beside Contact"
- **Pull request:** [#2](https://github.com/patronofalltrades/patronofalltrades.github.io/pull/2)

**Note:** The first commit put the button on the Home page and the Contact page. The second commit moved the button into the menu, so that it shows on each page.
