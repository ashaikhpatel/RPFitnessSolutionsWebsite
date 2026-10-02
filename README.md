# RP Fitness Solutions Website

A multi-page business website for **RP Fitness Solutions**, a Chicago-area company that repairs, maintains, and assembles fitness equipment. The site helps customers find the services they need, see examples of past work, check whether their suburb is covered, and send a quote request.

Built with plain **HTML, CSS, and JavaScript** (no frameworks or build step).

| Before | After |
| :---: | :---: |
| ![Before](images/before_treadmil1.jpg) | ![After](images/after_treadmil1.jpg) |

*A before and after example from the site's gallery.*

## Features

- **Home page** with a services overview, recent work gallery, before/after comparisons, customer reviews, service coverage, and a contact section
- **6 service pages** for treadmill, elliptical, exercise bike, and home gym repair, gym equipment assembly, and preventive maintenance
- **30 local area pages** (Chicago, Niles, Evanston, Skokie, Naperville, and more) generated from a single template
- **Contact form** that sends quote requests by email through [Web3Forms](https://web3forms.com/), with phone number validation and success/error messages
- **Responsive design** with breakpoints for tablet and mobile and a collapsible mobile navigation menu
- **Scroll reveal animations** using the Intersection Observer API
- **SEO setup** including page titles and meta descriptions, canonical URLs, Open Graph tags, JSON-LD structured data (LocalBusiness and FAQ), `sitemap.xml`, and `robots.txt`
- **Google Analytics** tracking on the area pages

## How the area pages work

Instead of writing 30 separate pages by hand, each page in `areas/` shares the same HTML template. On load, `js/area-page.js` reads the page's filename (for example `skokie.html`), looks up that area in an `AREA_DATA` object, and fills in the page text, SEO tags, structured data, and links to nearby areas.

To add a new area:

1. Copy `areas/_template.html` to `areas/<area-name>.html`
2. Add an entry for the area in `AREA_DATA` in `js/area-page.js`
3. Add the page to `sitemap.xml`

## Project structure

```
.
├── index.html              # Home page
├── about.html              # About page
├── services/               # 6 service pages
├── areas/                  # 30 area pages + _template.html
├── css/style.css           # Site styles
├── js/
│   ├── main.js             # Navigation, scroll animations, contact form
│   └── area-page.js        # Fills in area page content from AREA_DATA
├── images/                 # Logos, favicon, and repair photos
├── sitemap.xml
├── robots.txt
├── netlify.toml            # Security and caching headers
└── _redirects              # Forces HTTPS and the www domain
```

## Running locally

No install is needed. Clone the repo and open `index.html` in a browser, or serve the folder with a simple local server:

```bash
git clone https://github.com/ashaikhpatel/<repo-name>.git
cd <repo-name>
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deployment

The site is static and set up for [Netlify](https://www.netlify.com/):

- `netlify.toml` publishes the root folder and adds security headers (X-Frame-Options, X-Content-Type-Options, Referrer-Policy) plus long-term caching for images, CSS, and JS
- `_redirects` sends all HTTP and non-www traffic to `https://www.rpfitnesssolutions.com`

## Built with

- HTML5
- CSS3 (custom properties, flexbox, grid, media queries)
- Vanilla JavaScript
- Web3Forms for the contact form
- Netlify for hosting configuration
- Git and GitHub for version control

## Author

**Asiyah Shaikh**
[GitHub](https://github.com/ashaikhpatel) · [LinkedIn](https://www.linkedin.com/in/asiyah-shaikh-444a663a7/) · [Portfolio](https://asiyah-personal-website.vercel.app/)
