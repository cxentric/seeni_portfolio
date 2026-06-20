# cxentric.in — Portfolio Site

A single-page portfolio built with plain HTML/CSS/JS — no build step, no framework. Ready to deploy on GitHub Pages with your custom domain.

## Files

- `index.html` — the whole site (markup, styles, and script in one file)
- `CNAME` — tells GitHub Pages to serve this repo at `cxentric.in`

## 1. Deploy to GitHub Pages

1. Create a new GitHub repo (any name is fine, e.g. `cxentric-portfolio`).
2. Upload `index.html` and `CNAME` to the root of the repo.
3. Go to **Settings → Pages**, set source to your main branch, root folder.
4. Under **Custom domain**, enter `cxentric.in` (this should auto-fill from the CNAME file). Save.
5. Wait for the DNS check to pass, then enable **Enforce HTTPS**.

## 2. Point GoDaddy at GitHub

In GoDaddy DNS management for `cxentric.in`:

- Add four **A records** (host `@`) pointing to:
  `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
- Add a **CNAME record** (host `www`) pointing to `<your-github-username>.github.io`
- Remove any existing parking-page A records or forwarding GoDaddy set up by default.

DNS changes can take anywhere from a few minutes to a few hours to propagate.

## 3. Customize the content

Open `index.html` and replace anything in `[brackets]`:

- Hero: your name, role, and one-line summary
- About: bio paragraphs and skill tags
- Work: your three (or more) project cards
- Experience: your real roles and dates
- Contact: your real email, LinkedIn/GitHub links, and resume link

## 4. Make the contact form actually work

GitHub Pages only serves static files — it can't process form submissions. The form is already wired to [Formspree](https://formspree.io) syntax:

1. Create a free Formspree account and a new form.
2. Copy your form ID and replace `YOUR_FORM_ID` in the `<form action="...">` line in `index.html`.

Alternatively, you can remove the form entirely and rely on the `mailto:` email link, which works with no setup.

## 5. Favicon (optional)

There's no favicon set up yet. Drop a `favicon.ico` or `favicon.png` in the repo root and add this to the `<head>`:

```html
<link rel="icon" href="favicon.png">
```
