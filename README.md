# WASM Fun - WebAssembly to NASA Animation

A fun morphing animation that transforms "WASM" into "NASA" using authentic NASA typography.

## 🚀 Live Demo

**Status: Currently Offline** 🚫

The GitHub Pages deployment has been temporarily disabled for development and legal compliance review.

<!-- When enabled: https://kingdonb.github.io/wasm-fun/ -->

## 📖 About

This project features a smooth animated sequence that:

1. **Stage 1**: Shows the WebAssembly logo
2. **Stage 2**: Overlays "WASM" text on the logo
3. **Stage 3**: Displays "WASM" in purple standalone text
4. **Stage 4**: Transforms to "WASM" in NASA's iconic "worm" font style
5. **Stage 5**: Morphs into "NASA" using the same worm font
6. **Stage 6**: Concludes with the classic NASA insignia

The animation uses a "free for personal use" facsimile of NASA's "worm" font created by Daryl Schimmel to recreate the iconic typography from the 1970s-1990s era.

## 🛠 Technical Details

- **Frontend**: Pure HTML, CSS, and JavaScript
- **Typography**: Custom `@font-face` loading of facsimile `Nasa.ttf` font
- **Animation**: CSS keyframes with precise timing
- **Hosting**: GitHub Pages
- **Font Fallbacks**: Inter, Arial Black, sans-serif

## 📁 Project Structure

```
wasm-fun/
├── index.html          # Main animation page
├── Nasa.ttf           # NASA worm font facsimile by Daryl Schimmel
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

## 🚫 Disabling GitHub Pages

To temporarily disable the GitHub Pages deployment (useful during development or for legal compliance):

### Method 1: Via GitHub CLI (Recommended)
```bash
# Delete the GitHub Pages site entirely
gh api repos/kingdonb/wasm-fun/pages -X DELETE

# Verify pages are disabled (should return 404)
gh api repos/kingdonb/wasm-fun/pages
# Returns: 404 There isn't a GitHub Pages site here.
```

### Method 2: Via GitHub Web Interface
1. Go to repository Settings → Pages
2. Under "Source", select "None"
3. Click "Save"

### Re-enabling GitHub Pages
```bash
# Re-enable GitHub Pages from main branch
echo '{"source":{"branch":"main","path":"/"}}' | gh api repos/kingdonb/wasm-fun/pages -X POST --input -
```

**Note**: The GitHub API does **not** support setting `"source":"none"` - this is not a valid value. The only way to disable Pages via API is to DELETE the entire Pages site, which can then be recreated later.

**Reference**: [GitHub Docs - Deleting a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/deleting-a-github-pages-site#deleting-your-site-by-changing-the-source)

## 🎨 Font Integration

The project uses a NASA "worm" font facsimile through a custom `@font-face` declaration. The font is a "free for personal use" recreation by Daryl Schimmel, available from [font.download](https://font.download/font/nasa):

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

## � Development History

This project was developed through collaborative AI assistance across multiple platforms:

- **ChatGPT Conversation**: https://chatgpt.com/c/69020ab1-26e8-8331-a4ed-c22e7d6f3954 *(unpublished)*
  - Initial project conceptualization and basic implementation
- **Claude Conversation**: https://claude.ai/chat/eae92346-9a0c-4c85-9e05-2be688fa3b37 *(unpublished)*
  - Advanced enhancements and technical refinements that ChatGPT couldn't resolve
  - GitHub Pages setup and deployment automation
  - Font integration and animation timing improvements

## �📝 Credits & Legal Disclaimers

- **Concept**: "WASM" not "WebAssembly" - Keep the ASM in WASM
- **NASA Font**: Facsimile font by Daryl Schimmel - https://font.download/font/nasa (free for personal use)
- **WebAssembly Logo**: Used without permission from https://webassembly.org/ (https://webassembly.org/css/webassembly.svg)
- **NASA Insignia**: Used without permission from https://www.nasa.gov/nasa-brand-center/brand-guidelines/ - **sorry!** ⚠️

### ⚠️ Important Legal Notice

**This project uses NASA logos and branding without authorization.** According to NASA's brand guidelines (https://www.nasa.gov/nasa-brand-center/brand-guidelines/), unauthorized use of NASA logos, insignia, and branding is not permitted. This is a personal, non-commercial project created for fun and educational purposes, but users should be aware that:

- The NASA logos and insignia are protected and their use is restricted
- This project violates NASA's brand guidelines (sorry!)
- It's just a cute animation that turned out cool, not intended for any serious commercial use
- Anyone forking or using this code should consider the legal implications

If you're from NASA and would like this removed, please contact the repository owner.

## 📄 License

This project is for educational and demonstration purposes only. **Important**: This project uses copyrighted materials without permission, including NASA logos and WebAssembly branding. Use at your own risk and be aware of potential copyright and trademark issues. The font is free for personal use only.