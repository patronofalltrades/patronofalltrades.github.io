# Hanif Ramadhan: personal website

This repository contains the source files for the personal website of Hanif Ramadhan.

- **Live site:** <https://patronofalltrades.github.io>
- **Tools:** Jekyll (a static site generator) and GitHub Pages (free hosting from GitHub)
- **Languages:** Markdown, HTML, CSS, and YAML. The site does not use JavaScript.

This README is for readers who are new to Jekyll and GitHub Pages. It tells you how the site works and how to change it.

---

## 1. How the site works

1. You write the page text in Markdown files (`.md`).
2. You keep repeated data (jobs, readings, menu links) in YAML files in the `_data` folder.
3. Jekyll joins the text, the data, and the HTML templates into finished web pages.
4. GitHub Pages runs Jekyll automatically each time a change arrives on the `main` branch.
5. The new version of the site is live after approximately 1 to 3 minutes.

You do not need to build the site on your computer. GitHub Pages builds it for you.

---

## 2. Folder structure

| File or folder | What it contains |
|---|---|
| `index.md` | The text of the Home page. |
| `about.md` | The text of the About page. |
| `work-experience.md` | The template of the Work Experience page. The job data is in `_data/experience.yml`. |
| `reading.md` | The template of the Reading page. The reading data is in `_data/reading.yml`. |
| `contact.md` | The text of the Contact page. |
| `_data/navigation.yml` | The links in the top menu, in the order that they show. |
| `_data/experience.yml` | One entry for each job. |
| `_data/reading.yml` | One entry for each essay or book. |
| `_layouts/` | The HTML templates for full pages (`default`, `home`, `page`). |
| `_includes/` | Small HTML parts that many pages use (header data, menu, footer, CV button). |
| `assets/css/site.css` | All the visual styles (colors, fonts, spacing). |
| `assets/fonts/` | The Inter font files. The site supplies the fonts itself for speed. |
| `assets/files/` | Files for download, for example the CV (PDF). |
| `assets/favicon.svg` | The small icon in the browser tab. |
| `assets/og-image.jpg` | The image that shows when you share a link to the site. |
| `_config.yml` | The site settings (title, address, plugins, excluded files). |
| `Gemfile` | The list of Ruby packages for a local preview. |
| `Change1.md`, `Change2.md` | The plans for the two improvements in this course project. |

**Note:** Files and folders that start with `_` are special to Jekyll. Jekyll does not publish them as pages.

---

## 3. Common tasks

### 3.1 Change the text of a page

1. Open the `.md` file of the page (for example `about.md`).
2. Do not change the block between the two `---` lines at the top. This block is the "front matter". It tells Jekyll the layout, the title, and the address of the page.
3. Change the text below the second `---` line.
4. Save and commit the change.

### 3.2 Add a job

1. Open `_data/experience.yml`.
2. Copy one complete entry. An entry starts with `- title:`.
3. Paste the copy at the top of the list.
4. Change the values. Keep the same indentation (two spaces).
5. Save and commit the change.

### 3.3 Add an essay or a book

1. Open `_data/reading.yml`.
2. Copy one complete entry. An entry starts with `- title:`.
3. Paste the copy at the top of the list.
4. Change the values. If there is no author, use `author: ""`.
5. Save and commit the change.

### 3.4 Replace the CV

1. Put the new PDF in `assets/files/`.
2. If the file name is different, change `cv_file` in `_config.yml` to the new name.
3. If the file size is different, change the size in `aria-label` in `_includes/cv-button.html`.
4. Save and commit the change.

**Caution:** The CV is public. Remove private data (for example a phone number) before you add a new CV.

### 3.5 Add a new page

1. Make a new file in the root folder, for example `projects.md`.
2. Put this front matter at the top of the file:

   ```yaml
   ---
   layout: page
   title: "Projects"
   description: "One sentence about this page for search engines."
   permalink: /projects/
   ---
   ```

3. Write the page text below the front matter.
4. Open `_data/navigation.yml` and add the page:

   ```yaml
   - title: Projects
     url: /projects/
   ```

5. Save and commit the changes.

---

## 4. Preview the site on your computer (optional)

You need Ruby and Bundler on your computer. Do these steps in a terminal, in the root folder of this repository:

1. Install the packages:

   ```sh
   bundle install
   ```

2. Start the preview server:

   ```sh
   bundle exec jekyll serve
   ```

3. Open <http://127.0.0.1:4000/> in a browser.
4. To stop the server, push `Ctrl` + `C` in the terminal.

The `Gemfile` uses the `github-pages` package. Thus the local preview uses the same Jekyll version as GitHub Pages.

---

## 5. How changes go live

This repository uses branches and pull requests for each change:

1. Make a new branch from `main`. Give the branch a name that tells the change (for example `add-reading-collection`).
2. Make the change on the new branch. Write the plan in a `ChangeN.md` file.
3. Commit the change and push the branch to GitHub.
4. On GitHub, open a pull request from the branch into `main`.
5. Examine the changes. Write a comment that tells what you changed.
6. Merge the pull request.
7. GitHub Pages builds and publishes the site from `main`, folder `/` (root).

**Note:** `_config.yml` excludes `README.md`, `Change1.md`, and `Change2.md` from the published site. These files stay in the repository only.

**Settings:** Repository **Settings** > **Pages** > **Source:** Deploy from a branch > **Branch:** `main` > **Folder:** `/ (root)`.

---

## 6. Check the quality of the site

Do a Lighthouse check after each large change:

1. Open the live site in Google Chrome.
2. Open DevTools (`Cmd` + `Option` + `I` on Mac, `F12` on Windows).
3. Select the **Lighthouse** tab.
4. Select **Mobile**. Then select **Analyze page load**.
5. Do the check again with **Desktop**.
6. Do steps 4 and 5 for each page.

The minimum score is **90** in each category: Performance, Accessibility, Best Practices, and SEO.

Also do these checks:

- Make sure that each menu link opens the correct page.
- Make sure that the layout is correct at a width of 375 px (phone) and 1280 px (laptop). In DevTools, use the device toolbar (`Cmd` + `Shift` + `M`).

---

## 7. If a problem occurs

| Problem | Possible cause | Action |
|---|---|---|
| The site does not show. | The repository is private, or the Pages settings are incorrect. | Make the repository public. Examine **Settings** > **Pages**. |
| A change does not show on the live site. | The change is not on `main`, or the build is not complete. | Make sure that the pull request is merged. Wait 3 minutes. Refresh the page. |
| The page has no styles, or links are broken. | `baseurl` or `url` in `_config.yml` is incorrect. | Make sure that `baseurl: ""` and `url: "https://patronofalltrades.github.io"`. |
| The build fails after a YAML change. | The indentation in the YAML file is incorrect. | Use spaces, not tabs. Compare your entry with an entry that works. |

---

## 8. Words used in this README

| Word | Meaning |
|---|---|
| **Jekyll** | A program that makes web pages from text files and templates. |
| **GitHub Pages** | A free GitHub service that publishes a website from a repository. |
| **Markdown** | A simple text format. For example, `# Title` makes a heading. |
| **YAML** | A simple text format for data. It uses `key: value` lines and indentation. |
| **Front matter** | The YAML block between two `---` lines at the top of a page file. |
| **Branch** | A separate line of work. You can change files on it without a change to `main`. |
| **Pull request** | A request to merge the changes from one branch into another branch. |
| **Commit** | A saved set of changes, with a short message that tells what changed. |

---

## 9. Credits

- **Font:** [Inter](https://rsms.me/inter/) by Rasmus Andersson, under the SIL Open Font License. See `assets/fonts/OFL.txt`.
- **Build:** The first version was made with Replit Agent for the Intro to Code course (MBA 296C) at UC Berkeley Haas, Fall 2026.
