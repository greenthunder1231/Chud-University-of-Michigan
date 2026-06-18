# Chud University of Michigan

**The totally existent university.**
*Campuses in Climax, Michigan and Oblong, Illinois.*
**Ranked #1 by the Gooning Association of America (2025)**

> "Excellence in Gooning, Psychology & Digital Governance."

---

## About the University

Founded in 1969 in the historic gooning pavilions of Climax, Michigan, Chud
University of Michigan is the premier institution for certified chuds, incels,
gooners, and the finest basement-dwellers.

We offer rigorous training in misunderstood disciplines, fostering intellectual
honesty, digital fluency, and mastery of environments most "normies" fear to
enter. Graduates go on to moderate 68+ Discord servers, achieve 94% goon
placement rates, and produce world-class manifestos.

**Motto:** *Ascend through the basement. Govern through the meme.*

### Academic Programs

- **Gooning Studies (B.G., M.G.)** - the flagship program. 1,142 current majors.
- **Psychology (B.A., Ph.D.)** - online male identity formation and incel
  phenomenology. 687 majors.
- **Discord Moderation (Certificate, B.S.)** - rule adjudication, meme
  governance, server diplomacy. 1,018 students.

---

## What changed in this version

The site used to be a single HTML file with a Discord webhook hardcoded in the
browser JavaScript. That meant anyone could read the page source (or open
DevTools) and grab the webhook to spam the channel. This version fixes that and
organizes the project into a proper structure.

- The webhook now lives **server-side** in a Cloudflare Pages Function
  (`functions/api/apply.js`), read from an encrypted environment secret. The
  browser POSTs to `/api/apply` and never sees the URL.
- CSS and JS are split out of the HTML into `public/css/` and `public/js/`.
- Added server- and client-side validation, a honeypot field, basic rate
  limiting, security headers (`public/_headers`), meta/OG tags, a favicon,
  accessibility fixes (focus trap, visible focus, reduced-motion), and a
  loading state on submit.

> **Security note:** the old webhook URL is compromised - it was committed to a
> public repo. **Delete it in Discord and generate a new one** before deploying.
> Reusing the old URL means anyone who scraped it still has access.

---

## Project structure

    chud/
      public/                  static site (Pages serves this)
        index.html
        css/styles.css
        js/main.js
        assets/                logos / favicon
        _headers               security headers (CSP, HSTS, etc.)
      functions/
        api/apply.js           POST /api/apply - holds the webhook secret
      wrangler.toml
      .dev.vars.example        copy to .dev.vars for local dev
      .gitignore

---

## Local development

```bash
npm install -g wrangler           # if not already installed
cp .dev.vars.example .dev.vars    # then paste your NEW webhook into .dev.vars
wrangler pages dev public         # serves site + functions at localhost:8788
```

`.dev.vars` is gitignored - it never gets committed.

## Deploying to Cloudflare Pages

1. Push this repo to GitHub.
2. In the Cloudflare dashboard: **Workers & Pages -> Create -> Pages -> Connect to Git**.
3. Set the build output directory to `public`. No build command needed.
4. Under **Settings -> Variables and Secrets**, add `DISCORD_WEBHOOK_URL` as a
   **Secret** (not a plaintext variable) with your new webhook URL.
5. Deploy. The form will POST to `/api/apply` automatically.

---

## Tech stack

- Static HTML5 + Tailwind (CDN) + Font Awesome + Google Fonts
- Vanilla JavaScript
- Cloudflare Pages Function for the form backend

**Note on Tailwind:** this uses the CDN build, which is fine for a project like
this but prints a console warning and isn't optimized for production. If you want
that gone, switch to a build step with the Tailwind CLI - ask and I'll set it up.
