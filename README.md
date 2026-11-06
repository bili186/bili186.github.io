# Xu Zhe - Personal Portfolio
A modern, minimalist portfolio website for showcasing academic research, AI projects and mathematical modeling work, built with HTML5, CSS3, JavaScript, and GSAP animations.

---

## 🔗 Quick Access
- **Live Demo**: [Click to View My Portfolio](https://bili186.github.io/)
- Designed by Xu Zhe

---

## ✨ Features
- Clean, minimalist design focusing on academic projects & research
- Fully responsive layout compatible with all devices
- Smooth scroll animations and interactive effects powered by GSAP
- Project grid gallery for showcasing AI & CV works
- Independent detailed project detail pages
- Comprehensive about section including skills, awards and education
- Hosted contact form (Formsubmit) that delivers straight to the inbox — no mail client needed on the visitor's side
- Mobile-friendly navigation menu

---

## ✉️ Contact Form
The form in `index.html` (`#contact-form`) posts to a hosted form service, so the message lands in the inbox even if the visitor has no mail client configured.

- **Endpoint**: `action="https://formspree.io/f/<FORM_ID>"`. This is the only place the endpoint lives — the script reads it and posts to it directly, so changing accounts means editing one attribute.
- **Not configured yet**: the attribute currently holds the placeholder `YOUR_FORM_ID`. The submit handler detects that and refuses to post, showing "This form is not connected yet", so a visitor never fires a message at a non-existent form.
- **First run**: Formspree emails a confirmation link on the first submission; messages start arriving after it is clicked. Free plan allows 50 submissions per month.
- **Failure behaviour**: errors stay on the page as a red status line (no redirect), and the fields keep their contents so the visitor can retry. Only a browser with JavaScript disabled does a native form POST, returning via `_next` to `?sent=1`.
- **Spam**: a hidden `_gotcha` honeypot field is sent; Formspree silently drops submissions that fill it.
- **Why not Formsubmit**: it was the original choice (no signup needed), but its origin went down — every request returned Cloudflare 522 for 20 s. Formspree is reachable and was verified end-to-end from this machine.

---

## 🛠️ Technologies Used
- HTML5
- CSS3 with Tailwind CSS
- Vanilla JavaScript
- GSAP (GreenSock Animation Platform)
- Font Awesome icons

---

## 👨‍💻 About Me
- Undergraduate at Northeastern University
- Major: Mathematics and Applied Mathematics
- Minor: Computer Science
- Research Interests: Artificial Intelligence, Computer Vision, Mathematical Modeling

---

## 📁 Project Categories
- Metric Learning & Face Recognition (RipPLE, under review)
- Text-Based Person Search (GLAW, first-author manuscript)
- Medical Image Classification
- Computer Vision Applications
- Mathematical Modeling Competitions
- Academic Research & Papers

---

## 🗂️ Pages
Project pages are named after the project rather than numbered, so a URL stays readable when shared:

| File | Project |
|---|---|
| `index.html` | Home — project grid, about, contact |
| `works/ripple.html` | RipPLE: Concentric Hypersphere Loss for Robust Face Recognition |
| `works/glaw.html` | GLAW: Text-Based Person Search (first author) |
| `works/uav.html` | UAV auto-aiming — OpenVINO + ROS 2 |
| `works/thyroid.html` | Thyroid carcinoma classification |
| `works/weld.html` | Weld image recognition |
| `works/mathmodel.html` | Mathematical modeling competitions |

---

## 🖼️ Assets
- `assets/covers/` — 5 project cover plates, numbered 02–06, hand-authored SVG (vector, ~2500–5300 bytes each), no external dependencies. The retired `ripple.svg` and `reid-interpretability.svg` plates have been removed from the repo; the RipPLE card now uses the paper's own concept figure
- `assets/images/` — portrait, architecture diagram, the RipPLE paper figures and logo, and the GLAW figures, taken from the paper repositories. `ripple_concept.png` (741×458) doubles as the RipPLE card cover, shown with `object-contain` so none of its labels get cropped; `ripple_logo.png` (transparent PNG) heads the RipPLE project page; `glaw_fig1.png` (2161×769, transparent, rendered at 300 dpi from `Paper of GLAW/figs/fig1_glaw.pdf`) is the GLAW card cover
- `assets/favicon.svg` — site icon

The SVG covers stay sharp at any density and can be edited in place; when a real figure is used instead, keep the card height at `h-64` and let the image `object-contain` rather than `object-cover`, otherwise figure labels near the edges get cut.