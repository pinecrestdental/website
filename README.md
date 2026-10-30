# pinecrestdentalcare.com

The website for Pinecrest Dental Care, our family practice in northeast Bend.
Live at https://pinecrestdentalcare.com.

## Stack

- [Hugo](https://gohugo.io) 0.169 (extended), with our own theme in `themes/pinecrest/`
- Plain HTML templates and one stylesheet; no JavaScript, no build tools beyond Hugo
- Hosted on GitHub Pages, built by GitHub Actions on every push to `main`

## Running it locally

Install Hugo extended 0.169 or newer (`brew install hugo` on a Mac), then:

```bash
hugo server        # http://localhost:1313, reloads as you edit
```

To check the production build:

```bash
hugo --gc --minify  # writes the site to public/
```

## Where things live

```
hugo.toml                  site title, address, phone, email, main menu
data/hours.yaml            office hours (footer and contact page)
data/team.yaml             team bios and portraits (Meet Our Team page)
content/
  _index.md                home page copy and the three highlight cards
  services.md
  new-patients.md
  insurance-financing.md
  team.md                  intro text below the bios
  contact.md
  blog/                    one Markdown file per post
static/
  CNAME                    custom domain for GitHub Pages
  images/                  logo, illustrations and portraits (SVG)
themes/pinecrest/
  layouts/                 page templates and partials (header, footer, structured data)
  static/css/main.css      all styles
```

### Changing hours, phone or address

Hours live in `data/hours.yaml`; the phone, address and email live under `[params]` in
`hugo.toml`.

### Adding a blog post

Create `content/blog/<slug>.md` with `title`, `date`, `author` and `description` in the front
matter. It shows up on the blog index, the home page and the sitemap automatically.

## Deploying

Push to `main`. The **Deploy site to GitHub Pages** workflow (`.github/workflows/pages.yml`)
builds the site with Hugo and publishes it. In the repository settings, **Pages → Source**
must be set to **GitHub Actions**, and the custom domain to `pinecrestdentalcare.com`.

Questions about the site: ask Tessa.
