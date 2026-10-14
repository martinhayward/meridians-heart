# Meridian's Heart — static site

A plain HTML/CSS rebuild of meridiansheart.com (formerly on Squarespace), ready
to deploy to any static host. No build step, no framework, no dependencies
other than one Google Fonts stylesheet link.

## Structure

```
index.html              Home — about the book, cover, buy link, author blurb
about-the-author.html
excerpts.html
on-writing.html
contact.html             Contact form (mailto: — see note below)
teachers-guide.html
historical.html
cover-art.html
css/styles.css           Single shared stylesheet
images/                  header_image_01.png, main_cover.png, buynow.png
.claude/launch.json      Local preview config (python3 -m http.server)
```

All eight pages share the same header/nav and footer, pulled from the
original Squarespace site (About The Author, Excerpts, On Writing, Contact in
the top nav; Teacher's Guide, Historical References, Cover Art in the
footer).

## Preview locally

```bash
cd /Users/martinhayward/Documents/Claude/Meridians_Heart
python3 -m http.server 4173
```

Then open http://localhost:4173/.

## Contact form

Squarespace's form posted to Squarespace's own backend, which a static host
doesn't have. The rebuilt form uses `mailto:` so it opens the visitor's email
client pre-filled — zero dependencies, but not the smoothest UX and doesn't
work for visitors without a configured mail client.

If you want a real inbox-style submission without running a server, swap the
form's `action` for a free form backend such as:
- **Formspree** (formspree.io) — free tier, just change the `action` URL to
  the one they give you after signup, keep the same field names.
- **Web3Forms** (web3forms.com) — free, no signup beyond an access key.

## Free, secure hosting options

All of these give you free HTTPS and a global CDN for a static site like
this one:

| Host | Notes |
|---|---|
| **Cloudflare Pages** | Generous free tier, fast CDN, trivial custom-domain setup, drag-and-drop or git-based deploys. Good default choice. |
| **GitHub Pages** | Free with any GitHub repo (public repos; private repos need a GitHub Pro/Team plan for Pages). Push this folder to a repo and flip on Pages in settings. |
| **Netlify** | Free tier, drag-and-drop deploys or git-based CI, easy custom domain + HTTPS. |
| **Vercel** | Same category as Netlify, also free for static sites. |

Any of the four work well here since this is plain static HTML/CSS with no
server code. Cloudflare Pages or Netlify are the easiest for a "drag the
folder in" deploy; GitHub Pages is the easiest if you're already comfortable
with git and want deploys tied to commits.

## Attribution kept from the original site

- Cover art: "The Venetian Harpy" sculpture by Forest Rogers
  (forestrogers@gmail.com / forestrogers.com), used by permission — carried
  over on `cover-art.html`.
