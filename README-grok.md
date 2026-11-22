# blog-grok (local draft)

A plain HTML/CSS guide site for the Grok side of Makerly Paper Co.

**Status:** Owner approved this draft for publish on 22 November 2026 (Asia/Saigon), after a final QA pass. Intended repo and URL below.

Intended future location, after approval:

- Repo: `makerlypaperco/blog-grok`
- Public URL: https://makerlypaperco.github.io/blog-grok/

This site is separate from the main blog at https://makerlypaperco.github.io (Jekyll). The two blogs can share the same Gumroad shop. Articles here should not copy posts on the main blog.


## QA score (final pass, 22 November 2026, Asia/Saigon)

**99 / 100** (was 97 / 100 before this pass).

What changed in the final pass:

- Buttons use official brand colors only: navy `#28364D` background and cream `#F9F4EB` text (contrast 11.11:1). Hover is the reverse, same pair. The unofficial darkened coral `#9A4F35` was removed.
- Body links use navy text with a coral underline, so the coral stays visible without being used as small text (coral on cream is 2.63:1, below 4.5:1).
- SEO: `og:locale`, `og:image:alt`, `twitter:site` (`@MakerlyPaperCo`), `robots`, JSON-LD (WebSite, AboutPage, BlogPosting), breadcrumbs, and internal links between the two guides, About, and home. Canonical URLs already pointed at `https://makerlypaperco.github.io/blog-grok/`.
- Mobile: wrapping nav, 44px tap targets, tighter padding, and horizontal scroll for the example table.
- Header and footer logos keep empty `alt` text because the brand name sits next to them. The hero logo keeps a visible alt.

Checks that still pass: no invented numbers; sources cited; one product link per guide with `utm_source=grokblog&utm_medium=blog&utm_campaign=<slug>`; no em dashes; keyword in title, intro, and one H2; keyword density under 3%; no 3-word phrase more than 5 times; titles 35-65 characters; meta 115-155 characters; Flesch-Kincaid about 5-6; word counts 1,299 and 1,274; no income or health promises; AI and shop-template disclosures present; relative links only for in-site files.

The remaining 1 point is a small residual: the logo mark used on white and cream pages has the original cream backdrop removed for placement (the mark itself is not redrawn or recolored).

## What is in this folder

| File | Role |
|---|---|
| `index.html` | Home, lists the guides |
| `about-grok.html` | Short About page |
| `posts/snowball-vs-avalanche.html` | Guide: snowball vs avalanche |
| `posts/yearly-goal-planner.html` | Guide: yearly goal planner |
| `assets/css/style-grok.css` | Brand styles (navy, coral, cream, sage, mist, sand; Lexend + Inter) |
| `assets/fonts/` | Inter and Lexend, SIL Open Font License 1.1 (see `LICENSE-OFL-grok.txt`) |
| `assets/img/logo.png` | Owner's official logo, original file (copied, not redrawn or recolored) |
| `assets/img/logo-mark-grok.png` / `logo-icon-grok.png` / `logo-header-grok.png` | Same mark with the cream backdrop removed so it sits on white or cream; not recolored |
| `assets/img/*-grok.png` | Favicon, Open Graph cards (logo at bottom left) |
| `sitemap.xml` | Future canonical URLs under `/blog-grok/` |
| `robots.txt` | Points to that sitemap |
| `.nojekyll` | Tells GitHub Pages to serve these files as plain HTML |
| `preview/` | Local full-page screenshots for review (not for the public repo) |

Relative links are used everywhere so the site works at the root or at the `/blog-grok/` subpath.

## Preview on this machine

From `/workspace/makerly`:

```bash
python3 -m http.server 8765
```

Then open:

- http://127.0.0.1:8765/blog-grok/
- http://127.0.0.1:8765/blog-grok/posts/snowball-vs-avalanche.html
- http://127.0.0.1:8765/blog-grok/about-grok.html

## Guides in this draft

1. **How to choose snowball vs avalanche with your numbers**  
   Keyword: `snowball vs avalanche`  
   Product (live, HTTP 200 on 22 November 2026): [Debt Payoff Tracker](https://makerlypaperco.gumroad.com/l/debt-payoff-tracker?utm_source=grokblog&utm_medium=blog&utm_campaign=snowball-vs-avalanche) ($9)

2. **Write a yearly goal planner you can keep in 2027**  
   Keyword: `yearly goal planner`  
   Product (live, HTTP 200 on 22 November 2026): [2027 Goal Planner](https://makerlypaperco.gumroad.com/l/2027-goal-planner?utm_source=grokblog&utm_medium=blog&utm_campaign=yearly-goal-planner) ($7)

Every Gumroad link uses `utm_source=grokblog&utm_medium=blog&utm_campaign=<post-slug>` (or `home` / `about-grok` on those pages). Each guide has exactly one product link in the article body, plus the shop button in the header and footer. Disclosure and the AI-assistance line are on each guide.

The Free 2027 Goal Plan Page is live but is not linked in these two guides, so each article stays at one product link.

## Publish only after the owner approves

Do not run these steps until the owner says yes to this exact draft.

1. On GitHub, signed in as the `makerlypaperco` account, create a new **public** repository named `blog-grok`. Do not add a README, license, or `.gitignore` in the GitHub form (those files already exist here). Do not touch `makerlypaperco/makerlypaperco.github.io`.
2. On the machine that has this folder, initialize git if needed, add the remote, and push the site files:

   ```bash
   cd /workspace/makerly/blog-grok
   git init
   git add .
   # preview/ is gitignored; leave it out of the public repo
   git commit -m "Add blog-grok draft site"
   git branch -M main
   git remote add origin https://github.com/makerlypaperco/blog-grok.git
   git push -u origin main
   ```

3. In the new repo: **Settings → Pages**. Source: **Deploy from a branch**. Branch: **main**, folder: **/ (root)**. Save.
4. Wait for the Pages build, then check https://makerlypaperco.github.io/blog-grok/ and one post URL. Confirm the shop links still carry the UTM tags.
5. Optional: remove this "local draft" wording from the README after the site is live.

If GitHub Pages ever tries to run Jekyll, `.nojekyll` is already in the folder so the plain HTML is served as-is.
