# Triskel Labs website (team TriNova)

Single-page static site: HTML, CSS and vanilla JavaScript. No build step.

## Structure
```
index.html
assets/images/soumya.jpg
assets/resumes/            <- put the APPROVED public resume here as soumya-resume.pdf
```

## Before publishing
1. **Resume:** review `review/soumya-resume-public-DRAFT.pdf` (phone, email and address removed). When you approve it, copy it to `assets/resumes/soumya-resume.pdf`, then in `index.html` set `resumeApproved: true` in the `CONFIG` block. Until then the button is disabled. Never upload the original resume.
2. **Contact form:** it validates in the browser but sends nothing. To receive messages, create a free form endpoint (for example Formspree), paste its URL into `formEndpoint` in `CONFIG`. No email address appears in the page.
3. **Names:** change `company` and `team` in `CONFIG` to rename everywhere.
4. **Share image:** for link previews, change the `og:image` value in `<head>` to the full URL (for example `https://yourdomain.com/assets/images/soumya.jpg`).
5. **GitHub link:** none is shown. Add one in the founder card when you have it.

## Run locally
Open `index.html` in a browser, or run `python3 -m http.server` in this folder and visit http://localhost:8000.

## Upload to GitHub
1. Create a free account and a new empty repository (for example `triskel-labs`).
2. In this folder run:
```
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/triskel-labs.git
git push -u origin main
```
Do not commit the `review/` folder if the repository is public (add it to `.gitignore`).

## Deploy (recommended: Netlify or Vercel, both free)
**Netlify:** Add new site, Import from Git, pick the repo, leave build command empty and publish directory as `.`, then Deploy. Or drag the folder onto app.netlify.com/drop.
**Vercel:** Add New Project, import the repo, framework preset "Other", no build command, Deploy.
**GitHub Pages:** repo Settings, Pages, deploy from branch `main` and folder `/ (root)`.

After deploying, open the live URL and check the photo loads and the resume downloads.

## Custom domain
Buy a domain from any registrar. In Netlify (Domain management) or Vercel (Settings, Domains) add the domain, then create the DNS records they show you (usually an A record for the root and a CNAME for `www`). HTTPS is issued automatically within minutes to hours.
