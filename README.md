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

- **Endpoint**: `action="https://formspree.io/f/moeebbvk"`. This is the only place the endpoint lives — the script reads it and posts to it directly, so changing accounts means editing one attribute.
- **Guard rail**: the submit handler validates the attribute against `^https://formspree\.io/f/[A-Za-z0-9]{6,}$`. If anyone later swaps in a placeholder or a malformed URL, it refuses to post and shows "This form is not connected yet" instead of firing at a dead endpoint.
- **Verified end-to-end**: a real submission from the page in headless Chrome returned HTTP 200 with `{"ok":true}` in ~1.5 s, the green confirmation banner rendered, the button returned to its idle state and the fields cleared. Free plan allows 50 submissions per month.
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
- `assets/covers/` — 4 project cover plates, numbered 02–06, hand-authored SVG (vector, ~2500–5300 bytes each), no external dependencies, plus one photographic cover. `uav.svg` is a top-down coverage plot: a quadcopter inside a 360° ring, three camera pods at left / right / rear carrying the sharpness IDs used to bind the devices (81 / 82 / 80), three detections with confidences, and a small notch at the front where no USB camera is mounted. `weld.jpg` (784×512) replaces the earlier `weld.svg` plate: the abstract diagram of a seam under a scan line read as an illustration of welding rather than evidence of it, so the card now carries one real frame from the dataset the model was trained on. The retired `ripple.svg` and `reid-interpretability.svg` plates have been removed from the repo; the RipPLE card now uses the paper's own concept figure
- `assets/images/` — portrait, architecture diagram, the RipPLE paper figures and logo, and the GLAW figures, taken from the paper repositories. `ripple_concept.png` (741×458) doubles as the RipPLE card cover, shown with `object-contain` so none of its labels get cropped; `ripple_logo.png` (transparent PNG) heads the RipPLE project page; `glaw_fig1.png` (2161×769, transparent, rendered at 300 dpi from `Paper of GLAW/figs/fig1_glaw.pdf`) is the GLAW card cover; `uav_pipeline.svg` (1200×560) is the pipeline flowchart in the UAV page's System Architecture section — a real decision node (reprojection-error gate) with a discard branch and a dashed watchdog path, replacing the earlier five-column `div` layout
- Assets lifted from `Documents/西湖大学暑研/西湖大学暑研面试.pptx` (the slides that were already used for the Westlake interview): `weld_dataset_grid.jpg` (1920×1464, 16 raw frames with capture-order filenames, weld page) and `weld_f1_curve.png` (203×449, the matplotlib chart cropped to its ink bounding box — the original 640×480 export was 2/3 white margin and turned to mush when scaled into a column); `uav_platform.jpg` (799×749, competition robot) and `uav_deploy_split.png` (1440×402, the miniPC / STM32 split as drawn in the team's design doc, Chinese labels kept because it is the real source figure — the caption translates both rails). Skipped deliberately: the YOLO training-curve PNG (a single logged point), the label-statistics plot and the detection grid (their axis / box text renders as mojibake), and a third-party Roboflow grid carrying a CSDN watermark
- `assets/favicon.svg` — site icon

The SVG covers stay sharp at any density and can be edited in place; when a real figure is used instead, keep the card height at `h-64` and let the image `object-contain` rather than `object-cover`, otherwise figure labels near the edges get cut. `weld.jpg` is the exception and uses `object-cover`: it is a photograph with no labels, exported at exactly the card's 1.53 ratio (784×512, 2× of 392×256) so no crop happens in the browser. It was cut from one cell of `weld_dataset_grid.jpg` — each cell is 480×366 with a 50 px filename bar on top, and the photograph inside occupies only 472×262 (the rest is flat grey filler, which shows up as a dead band if you crop to the cell rather than to the photo). The card crop takes a 210 px band of that height, lifted with `brightness(1.07) contrast(1.08) saturate(0.92)` so the steel sits closer to the tone of the neighbouring light plates.