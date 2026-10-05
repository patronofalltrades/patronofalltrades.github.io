Let recruiters get my CV in one click from the page they land on, without emailing me first. This turns the site from a profile into a recruiting tool.
- Branch: `add-cv-download`
- Commit message: "Add Download CV button to Home and Contact pages"

- Move Hanif-Ramadhan-CV.pdf to assets/files/Hanif-Ramadhan-CV.pdf. Do not modify the PDF.
- In _config.yml add: cv_file: /assets/files/Hanif-Ramadhan-CV.pdf
- Create _includes/cv-button.html: an <a> element styled as a button with the text "Download CV (PDF)", href = site.cv_file passed through relative_url, the download attribute, and aria-label="Download Hanif Ramadhan's CV (PDF, 84 KB)".
- Include it in the Home page hero directly under the intro line, and at the top of contact.md under the intro sentence.
- Add button styles to assets/css/site.css: black background (#000), white text, square corners, comfortable padding, a visible focus outline, a subtle hover state, and full width on screens under 480px. Keep contrast accessible.
- No JavaScript. Do not change any other page text.
