# DevOps Portfolio — Single-File Site

A self-contained, single-file personal portfolio website for a DevOps & Cloud Infrastructure Engineer. The entire site (HTML, CSS, JS, avatar image, and resume PDF) is bundled into one `portfolio.html` file — no build step, no dependencies, no server required.

## ✨ Features

- **Single-file deployment** — open `portfolio.html` directly in any browser, or drop it on any static host
- **Embedded assets** — avatar image and resume PDF are inlined as base64 data URIs
- **Responsive design** — works on mobile, tablet, and desktop
- **SEO optimized** — meta tags, Open Graph, semantic HTML, single H1, alt text, JSON-LD ready
- **Smooth scroll animations** — `IntersectionObserver`-driven reveals for skills and timeline
- **Animated skill bars** — proficiency bars fill in as the section enters the viewport
- **Interactive certifications** — clickable cards linking to credential verification pages
- **Downloadable resume** — one-click PDF download from the embedded data URI
- **Accessible** — semantic landmarks, keyboard-friendly nav, sufficient color contrast

## 📑 Sections

1. **Hero** — name, title, tagline, primary CTAs
2. **About** — short bio and background
3. **Tech Stack** — tools and platforms (AWS, Kubernetes, Terraform, etc.)
4. **Core Skills** — grouped skill bars with animated proficiency levels
5. **Experience** — vertical timeline of roles and accomplishments
6. **Projects** — featured infrastructure and automation projects
7. **Certifications** — clickable cards with "Verify credential →" links
8. **Resume** — embedded PDF with download button
9. **Get in Touch** — contact links (email, LinkedIn, GitHub)

## 🚀 Usage

### Open locally
```bash
open portfolio.html        # macOS
xdg-open portfolio.html    # Linux
start portfolio.html       # Windows
```

### Deploy
Upload `portfolio.html` to any static host:
- GitHub Pages
- Netlify (drag-and-drop)
- Vercel
- Cloudflare Pages
- S3 + CloudFront
- Any web server (`nginx`, `apache`, `python -m http.server`)

No build, no bundler, no `node_modules`.

## 🛠️ Customization

Everything lives in `portfolio.html`. Open it in any editor and look for these sections:

| What to change | Where to look |
|---|---|
| Name, title, tagline | `<title>`, hero section, JSON-LD block |
| Meta description / OG tags | `<head>` meta tags |
| Tech stack items | `stackData` array in `<script>` |
| Skill groups & levels | `skillsData` array |
| Timeline entries | `timelineData` array |
| Projects | `projectsData` array |
| Certifications + verify URLs | `certsData` array (each item has `url`) |
| Avatar image | replace the `data:image/png;base64,...` in the avatar `<img>` |
| Resume PDF | replace the `data:application/pdf;base64,...` in the resume link |
| Colors / theme | CSS variables at the top of the `<style>` block |

### Replacing the embedded avatar / resume
Convert your file to base64 and paste it into the existing data URI:
```bash
# Avatar (PNG)
base64 -i avatar.png | tr -d '\n'

# Resume (PDF)
base64 -i resume.pdf | tr -d '\n'
```

## 🧱 Tech

- Vanilla **HTML5**, **CSS3**, **JavaScript** (no framework)
- **IntersectionObserver** for scroll-triggered animations
- **CSS custom properties** for theming
- **Base64 data URIs** for asset embedding

## 📂 Project Structure

```
portfolio.html    # The entire site — that's it.
README.md         # This file.
```

## 📝 License

Personal portfolio — use as inspiration, swap in your own content.
