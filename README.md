# istimartasukma.com — static site

A static HTML/CSS/JS rebuild of the site, ready to push to GitHub and publish with GitHub Pages.

## Structure

```
index.html            Home
techno-realism.html    Techno-Realism
research.html          Research and Publications
grants.html            Grants and Scholarships
conferences.html       Conference Presentations
industry.html          Industry Experience
methods.html           Methods and Certifications
teachings.html         Teachings
media.html             Media
contact.html           Contact
assets/style.css       All styling
assets/script.js       Nav toggle + active-link highlighting
```

## Publish with GitHub Pages

1. Create a new repository on GitHub (e.g. `istimartasukma.github.io` for a user site, or any name for a project site).
2. Push these files to the repository root (on the `main` branch):
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**, set **Source** to `main` branch, `/ (root)` folder, and save.
4. Your site will be live at `https://<you>.github.io/<repo>/` (or your custom domain, once configured — GitHub Pages supports this under **Settings → Pages → Custom domain**, if you want to point `istimartasukma.com` at it).

## Notes

- **Images are hotlinked** from your existing WordPress media library (the `wp-content/uploads/...` URLs). This keeps the repo small and the images update-free, but it does mean the images depend on that WordPress site staying up. If you'd rather host them yourself, download each image into an `assets/images/` folder and update the `src` attributes to point there instead.
- **The contact form has no backend.** Right now it just shows a "Thank you" message locally. To actually receive submissions, wire it up to a form service such as Formspree, Getform, or Basin (most just need you to change the `<form>`'s `action` attribute to a URL they give you), or replace the JS handler in `contact.html` with a `fetch()` call to your own endpoint.
- All nine subpages share `assets/style.css` and `assets/script.js`, so editing either updates every page at once.
