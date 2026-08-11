# Face Pixelator 🥷

> **Precision, Browser-Native Interactive Shape Masking & Anonymization Tool**  
> *No AI required. 100% private, client-side HTML5 canvas pixelation.*

🚀 **Live Demo**: [https://bigcjat.github.io/facepixelate/](https://bigcjat.github.io/facepixelate/)

| Original Image (`xshroom.webp`) | Pixelated Output (`pixelated-face.png`) |
| :---: | :---: |
| <img src="xshroom.webp" width="360" alt="Original Image"> | <img src="pixelated-face.png" width="360" alt="Pixelated Output"> |

---

## 🌟 Overview

**Face Pixelator** is a lightweight, zero-dependency web application for selectively pixelating and anonymizing facial features, profile pictures, avatars, and artwork directly in your browser.

Unlike standard AI face-detection algorithms—which frequently fail on cartoon avatars, anime art, non-human ears, or angled profile shots—Face Pixelator gives you **full manual control** over the exact boundary of the pixelation mask. You can pixelate *only* eyes, mouth, or facial contours while preserving hair, clothing, background elements, and ears perfectly intact.

---

## ✨ Features

- **🔒 100% Private & Client-Side**: All image rendering and manipulation happens entirely in your local browser runtime. No images are ever uploaded to any server.
- **🎯 Dual Mask Geometries**:
  - **Ellipse / Oval Mode**: Quick adjustments for standard rounded faces using center, width, height, and angle handles.
  - **Custom Mesh (Polygon) Mode**: Add, drag, or delete vertex nodes to snugly trace complex contours (hair bangs, jawlines, cartoon ears).
- **🎛️ Mosaic & Feathering Controls**:
  - Adjustable **Mosaic Block Size** (from fine pixels to large blocky censorship).
  - Adjustable **Edge Softness (Feathering)** for smooth blending into surrounding image details.
- **📱 Fully Mobile Responsive**:
  - On desktop: Fixed side controls panel for rapid desktop workflows.
  - On mobile: Off-canvas slide-out drawer with a backdrop overlay, freeing 100% of screen real estate for touch interactions on the canvas.
- **⚡ Preloaded Sample Test Image**: Comes preloaded with `xshroom.webp` so you can test and experiment with masking controls instantly.
- **💾 PNG Export**: One-click export that generates high-resolution, uncompressed PNG outputs without vector guide overlays.

---

## 🧠 How It Works

Face Pixelator leverages native **HTML5 Canvas 2D Context** APIs and offscreen buffer rendering:

1. **Clipping Boundary Definition**:
   Interactive control nodes map normalized coordinates `(0.0 to 1.0)` relative to image dimensions. When adjusting nodes, a vector path is generated using `ctx.ellipse()` or `ctx.lineTo()` polygonal paths.

2. **Isolated Mosaic Downscaling & Upscaling**:
   When rendering the censored area, an offscreen canvas clips to the active shape boundary. The selected image region is rendered to a downscaled buffer canvas with `imageSmoothingEnabled = false`, then stretched back onto the clipped mask layer. This creates crisp, retro mosaic pixel blocks strictly within the vector boundary.

3. **Composite Layering**:
   The pixelated offscreen canvas is composited back on top of the raw base image in real-time at 60fps.

---

## 🚀 Getting Started

No installation, Node.js environment, or build step is required!

1. Clone or download this repository:
   ```bash
   git clone https://github.com/bigcjat/facepixelate.git
   ```
2. Open `face_pixelator_interactive_masking_tool.html` directly in any web browser (Chrome, Safari, Firefox, Edge, or mobile browsers).
3. Click **Select Image** to load your own image, or click **Sample** to reload the default test image.

---

## 🛠️ Built With

- **HTML5 Canvas API** - Offscreen buffer pixelation & path clipping
- **Vanilla JavaScript (ES6+)** - Reactive canvas state & touch/mouse interaction handlers
- **Tailwind CSS** - Glassmorphism UI styling & responsive layout grid
- **FontAwesome 6** - Icon system

---

## 📄 License

MIT License - feel free to use, modify, and distribute for personal or commercial projects.
