# Zhenghao Lu | 鲁正豪 — Personal Academic Homepage

Clean, static academic homepage modeled on [caijiting.github.io](https://caijiting.github.io/) (derived from Jon Barron's classic template).

## File Structure

```text
homepage/
├── index.html                  # Main homepage HTML
├── stylesheet.css              # Stylesheet (Lato font, responsive 800px layout)
├── .nojekyll                   # Bypass Jekyll processing on GitHub Pages
├── .gitignore                  # Ignore OS/editor temporary files
├── README.md                   # This guide
└── images/
    ├── favicon.svg             # Browser tab icon ("ZL")
    ├── profile-placeholder.svg # Placeholder avatar (replace with profile.jpg)
    └── publications/
        ├── dict.png            # DiCT teaser figure (arXiv:2611.32344)
        ├── larf.png            # LARF pipeline figure (arXiv:2507.18631)
        └── safework_r1.png     # SafeWork-R1 figure (arXiv:2507.18576)
```

## Local Preview

```bash
cd /data/zhenghao/homepage
python3 -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

## Customization Checklist

1. **Profile photo**: Place your portrait photo at `images/profile.jpg` (a square crop works best; CSS automatically applies `aspect-ratio: 1 / 1; object-fit: cover; border-radius: 50%;`) and update both `href` and `src` in `index.html` from `images/profile-placeholder.svg` to `images/profile.jpg`.
2. **CV & additional links**: Create `files/CV.pdf` and uncomment the optional links inside `<p class="links">` in `index.html`.
3. **Motto, Awards, Misc, Visitor Map**: Uncomment the corresponding sections in `index.html` whenever you want to display them.

## Deploying to GitHub Pages

The local Git repository in `/data/zhenghao/homepage/` is already initialized on branch `main` with `origin` set to `https://github.com/HongYep/HongYep.github.io.git`.

1. Create an empty **Public** repository named `HongYep.github.io` at <https://github.com/new> (do not initialize with a README, `.gitignore`, or license).
2. Push from `/data/zhenghao/homepage/`:
   ```bash
   cd /data/zhenghao/homepage
   git push -u origin main
   ```
   (Authenticate using your GitHub username `HongYep` and a GitHub Personal Access Token, or switch `origin` to SSH `git@github.com:HongYep/HongYep.github.io.git` after adding an SSH key to GitHub.)
3. In GitHub repository **Settings → Pages**, verify **Source** is set to `Deploy from a branch` (`main` / `/ (root)`).
4. After ~1–2 minutes, your site will be live at <https://hongyep.github.io/>.
