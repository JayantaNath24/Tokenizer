# Token Space — Interactive Tokenization & Semantic 3D Vector Space

> An interactive educational tool that visualizes how text is split into tokens and how example sentences relate geometrically in a 3D semantic vector space.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Three.js](https://img.shields.io/badge/Three.js-r128-black?logo=three.js)](https://threejs.org/)
[![HTML5](https://img.shields.io/badge/HTML5-Single--File_App-orange?logo=html5)](index.html)

---

## 🌟 Overview

**Token Space** is a self-contained, responsive web application designed to help users explore text tokenization, compare example sentences, and build intuition for semantic distance and vector spaces.

The app features a dark navy dashboard inspired by technical AI tools (OpenAI Tokenizer, Embedding Projector), pairing browser-based deterministic subword tokenization with an interactive 3D WebGL semantic vector space.

---

## 🚀 Key Features

### 1. Left Panel: Sentence & Tokenization
- **Live Textarea Analysis**: Real-time character count, word count, token count, and UTF-8 byte count.
- **Subword BPE-Style Segmentation**: Decomposes text into word roots, prefixes (`un-`, `re-`, `sub-`, etc.), and suffixes (`-tion`, `-ment`, `-able`, etc.), preserving leading whitespace markers (`_`).
- **Category Color Coding**:
  - 🟣 **Subwords / Affixes** (`#c084fc`)
  - 🔵 **Nouns & Core Concepts** (`#22d3ee`)
  - 🟢 **Syntax & Grammar** (`#34d399`)
  - 🟡 **Punctuation & Delimiters** (`#fbbf24`)
  - 🔴 **Special & Numbers** (`#f43f5e`)
- **Working Collection**: Manage and inspect added sentences, complete with cluster tags, coordinate previews, and individual remove controls.
- **Preset Chips**: One-click quick load examples:
  - `🦊 Fox & Dog`
  - `🧠 LLM Concept`
  - `🧩 Subwords`
  - `⚡ Deep Neural`
  - `☕ Espresso`
  - `🌌 Cosmos`

### 2. Center Panel: Interactive 3D Visualization
- **3D Perspective Scene**: Powered by Three.js with OrbitControls (and an automated HTML5 Canvas 3D Perspective Projection fallback if WebGL or external CDN is unavailable).
- **Semantic Clusters**: Glowing spherical nodes colored by domain:
  - 💠 *AI & Computation*
  - 🌿 *Animals & Nature*
  - ☕ *Daily Life & Food*
  - 🔤 *Linguistics*
  - 🌌 *Science & Cosmos*
  - 🧠 *Philosophy*
- **Dynamic Connection Lines**: Real-time connecting lines between the selected sentence and all other nodes, colored and weighted by similarity, accompanied by floating distance tags (`d=... (% Sim)`).
- **Selection Ring**: Pulsing animated 3D torus tracking the active sentence.
- **Controls & Toolbar**:
  - **3D Space / 2D Plane Mode Toggle**: Smoothly animates points flattening onto a 2D ground plane and back.
  - **Metric Selector**: Switch between Euclidean ($L_2$), Cosine Distance, and Manhattan ($L_1$).
  - **Labels Toggle**: Show / hide floating 3D text billboards.
  - **Auto-Orbit**: Continuous smooth rotation (honoring `prefers-reduced-motion`).
  - **Focus & Reset**: Camera interpolation to focus on the selected point or reset to isometric view.

### 3. Right Panel: Vocabulary & Inspector
- **Sentence Inspector**: Comprehensive metrics grid (**Tokens**, **Chars**, **Bytes**, **Chars/Token Ratio**) with interactive token chips.
- **Coordinate Progress Bars**: Relative $X$, $Y$, and $Z$ positions in the $[-4.0, +4.0]$ space.
- **16-D Simulated Embedding Slice**: Demonstrates how high-dimensional vectors look prior to 3D projection.
- **Ranked Distance Comparison List**: Shows closest-to-furthest neighbors with similarity percentage meters and quick-select buttons.
- **Collection Vocabulary Cloud**: Unique token count, category breakdown bar, search filter, and clickable token pills that highlight matching sentences.
- **Collapsible Subword Reference & Sandbox**: Interactive sandbox to test live subword splitting on any arbitrary word.

### 4. Data Honesty & Transparency
- Accessible via the **Guide & Honesty** modal in the header.
- Clearly states that 3D positions and distances are *deterministic geometric demonstrations* designed for educational visualization rather than measured weights from a live multi-billion parameter neural network.

---

## 💻 Getting Started

This project is completely self-contained in a single file (`index.html`) with zero build steps or package managers required.

### Quick Start

1. Clone the repository:
   ```bash
   git clone https://github.com/JayantaNath24/Tokenizer.git
   cd Tokenizer
   ```

2. Open `index.html` in your web browser:
   - **macOS**: `open index.html`
   - **Linux**: `xdg-open index.html`
   - **Windows**: `start index.html`

3. Or run a local HTTP server:
   ```bash
   python3 -m http.server 8080
   ```
   Navigate to [http://localhost:8080](http://localhost:8080).

---

## 🛠️ Tech Stack

- **HTML5 & CSS3**: Vanilla CSS Custom Properties (Variables), Flexbox, CSS Grid, Glassmorphism, and responsive breakpoints.
- **JavaScript (ES6+)**: Custom client-side subword tokenizer, deterministic hashing, matrix projection engine, and state management.
- **Three.js (r128)**: WebGL rendering, OrbitControls, and custom shader/sprite materials.
- **HTML5 Canvas Fallback**: Lightweight custom 3D perspective projection engine ensuring 100% functionality without external network dependencies.

---

## 📄 License

This project is open-source and available under the [MIT License](LICENSE).
