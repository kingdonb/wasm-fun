# WASM Fun - WebAssembly to NASA Animation

A fun morphing animation that transforms "WASM" into "NASA" using authentic NASA typography.

## 🚀 Live Demo

**Visit the live animation:** https://kingdonb.github.io/wasm-fun/

## 📖 About

This project features a smooth animated sequence that:

1. **Stage 1**: Shows the WebAssembly logo
2. **Stage 2**: Overlays "WASM" text on the logo
3. **Stage 3**: Displays "WASM" in purple standalone text
4. **Stage 4**: Transforms to "WASM" in NASA's iconic "worm" font style
5. **Stage 5**: Morphs into "NASA" using the same worm font
6. **Stage 6**: Concludes with the classic NASA insignia

The animation uses the authentic `Nasa.ttf` font file to ensure the text matches NASA's official "worm" logo typography from the 1970s-1990s era.

## 🛠 Technical Details

- **Frontend**: Pure HTML, CSS, and JavaScript
- **Typography**: Custom `@font-face` loading of `Nasa.ttf`
- **Animation**: CSS keyframes with precise timing
- **Hosting**: GitHub Pages
- **Font Fallbacks**: Inter, Arial Black, sans-serif

## 📁 Project Structure

```
wasm-fun/
├── index.html          # Main animation page
├── Nasa.ttf           # Authentic NASA worm font
├── README.md          # This documentation
└── assets/            # Additional resources
    ├── NASA_logo.svg
    ├── webassembly.svg
    └── screenshots/
```

## 🌐 GitHub Pages Setup Process

This project was deployed to GitHub Pages using the following steps:

### 1. Repository Setup
```bash
# Created public GitHub repository
gh repo create wasm-fun --public
```

### 2. File Preparation
```bash
# Renamed main file for GitHub Pages default serving
mv wasm-to-nasa-animation.html index.html
git add index.html
git commit -m "Rename to index.html for GitHub Pages"
```

### 3. Remote Configuration
```bash
# Added GitHub as remote origin
git remote add origin https://github.com/kingdonb/wasm-fun.git

# Pushed code to GitHub
git push -u origin main
```

### 4. GitHub Pages Activation
```bash
# Enabled GitHub Pages via GitHub API
echo '{"source":{"branch":"main","path":"/"}}' | gh api repos/kingdonb/wasm-fun/pages -X POST --input -
```

### 5. Verification
```bash
# Checked deployment status
gh api repos/kingdonb/wasm-fun/pages
```

## 🎨 Font Integration

The project uses the authentic NASA "worm" font through a custom `@font-face` declaration:

```css
@font-face {
    font-family: 'Nasa';
    src: url('./Nasa.ttf') format('truetype');
    font-weight: normal;
    font-style: normal;
}
```

Applied to the worm-style text elements:
```css
.wasm-worm, .nasa-worm {
    font-family: 'Nasa', 'Inter', 'Arial Black', sans-serif;
    /* ... other styles ... */
}
```

## 🔄 Auto-Restart Feature

The animation includes an auto-restart mechanism that replays the sequence every 21 seconds, plus a manual restart button for user control.

## 🚀 Local Development

To run locally:

1. Clone the repository:
   ```bash
   git clone https://github.com/kingdonb/wasm-fun.git
   cd wasm-fun
   ```

2. Open `index.html` in your browser, or serve via local server:
   ```bash
   python -m http.server 8000
   # or
   npx serve .
   ```

3. Visit `http://localhost:8000`

## 📝 Credits

- **Concept**: "WASM" not "WebAssembly" - Keep the ASM in WASM
- **NASA Font**: Authentic NASA "worm" logotype typography
- **WebAssembly Logo**: Official WebAssembly SVG logo
- **NASA Insignia**: Official NASA logo from Wikimedia Commons

## 📄 License

This project is for educational and demonstration purposes. NASA logos and fonts are used under fair use for non-commercial purposes.