# Hanif Ramadhan — Portfolio

A static Jekyll site published with GitHub Pages.

## Update content

- Edit `index.md` for the Home page, or edit `about.md`, `work-experience.md`, and `contact.md` for their pages. Preserve each page's YAML front matter and permalink.
- Add, edit, or reorder work history in `_data/experience.yml`.
- Change the navigation labels, URLs, or order in `_data/navigation.yml`. When adding a page, add its matching URL there.

## Preview locally

Install Ruby and Bundler, then run these commands from the repository root:

```sh
bundle install
bundle exec jekyll serve
```

Open `http://127.0.0.1:4000/` in a browser. The `Gemfile` uses the `github-pages` gem so the local preview uses GitHub Pages-compatible Jekyll dependencies.

## Publish with GitHub Pages

GitHub Pages publishes from the `main` branch and the repository root (`/`). Pushing a commit to `main` triggers the Jekyll build and publication at <https://patronofalltrades.github.io/>.

`README.md`, `Change1.md`, and `Change2.md` are excluded from the generated site by `_config.yml`; they remain available in the Git repository.

## Check performance with Lighthouse

In Chrome, open DevTools and select **Lighthouse**. Run an audit in both **Mobile** and **Desktop** mode. Repeat for the Home, About, Work Experience, and Contact pages. The target is a **Performance score of 90 or higher** in both modes.
