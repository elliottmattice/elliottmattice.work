# Elliott Mattice - Jekyll Website

Professional website for Elliott Mattice - Executive advisor, systems-risk strategist, and creator of Upstream Risk Translation.

**Live site:** https://elliottmattice.work

---

## Quick Start

### 1. Clone & Setup

```bash
# Clone this repo
git clone https://github.com/YOUR-USERNAME/elliottmattice.github.io.git
cd elliottmattice.github.io

# Install dependencies
bundle install

# Preview locally (optional)
bundle exec jekyll serve
# Opens at http://localhost:4000
```

### 2. Deploy to GitHub Pages

```bash
# Push to GitHub
git push origin main

# GitHub Actions will build and deploy automatically
# Site live at: https://YOUR-USERNAME.github.io
```

### 3. Add Custom Domain

1. **In repo settings:**
   - Go to Settings → Pages
   - Custom domain: `elliottmattice.work`
   - Save

2. **Update DNS (at your domain registrar):**
   ```
   CNAME record: www → YOUR-USERNAME.github.io
   A records:
   185.199.108.153
   185.199.109.153
   185.199.110.153
   185.199.111.153
   ```

3. **Wait 15-30 minutes** for DNS propagation

---

## Creating Content

### Writing a Blog Post

**1. Create new Markdown file in `_posts/`:**

```bash
# File naming: YYYY-MM-DD-title.md
touch _posts/2026-02-20-geopolitical-analysis.md
```

**2. Add front matter and content:**

```markdown
---
title: "Your Post Title Here"
date: 2026-02-20
category: analysis
excerpt: "Brief description of the post (appears in previews)"
download: "/assets/frameworks/your-framework.pdf"  # Optional
---

Your content here in Markdown...

## Section Heading

Content with **bold** and *italic* text.

- Bullet points
- More bullets

[Links work like this](https://example.com)

![Images work like this](/assets/images/chart.png)
```

**3. Commit and push:**

```bash
git add _posts/2026-02-20-geopolitical-analysis.md
git commit -m "New post: Geopolitical analysis"
git push origin main

# Live in 60 seconds
```

### Saving Drafts

**Keep unpublished posts in `_drafts/`:**

```bash
# Create draft (no date in filename)
touch _drafts/work-in-progress.md

# Work on it, commit to save progress
git add _drafts/work-in-progress.md
git commit -m "Draft: Work in progress"
git push

# When ready to publish, move to _posts/ with date
mv _drafts/work-in-progress.md _posts/2026-02-25-work-in-progress.md
git add .
git commit -m "Publish: Work in progress"
git push
```

### Adding Images

**1. Add image to `assets/images/`:**

```bash
cp ~/Downloads/chart.png assets/images/
git add assets/images/chart.png
git commit -m "Add chart image"
```

**2. Reference in post:**

```markdown
![Description of image](/assets/images/chart.png)
```

### Adding PDFs (Frameworks, Position Papers)

**1. Add PDF to `assets/pdfs/` or `assets/frameworks/`:**

```bash
cp ~/Documents/framework.pdf assets/frameworks/
git add assets/frameworks/framework.pdf
git commit -m "Add framework PDF"
```

**2. Link in post:**

```markdown
Download the full framework: [PDF](/assets/frameworks/framework.pdf)
```

**Or use front matter for automatic download CTA:**

```yaml
---
title: "Post Title"
download: "/assets/frameworks/framework.pdf"
---
```

### Embedding Videos

**YouTube:**

```html
<iframe width="560" height="315" 
  src="https://www.youtube.com/embed/VIDEO_ID" 
  frameborder="0" allowfullscreen>
</iframe>
```

**Self-hosted video:**

```html
<video controls style="max-width: 100%;">
  <source src="/assets/videos/your-video.mp4" type="video/mp4">
</video>
```

---

## Markdown Quick Reference

### Headings

```markdown
## Level 2 Heading
### Level 3 Heading
```

### Text Formatting

```markdown
**bold text**
*italic text*
`inline code`
```

### Lists

```markdown
- Bullet point
- Another bullet

1. Numbered item
2. Another number
```

### Links & Images

```markdown
[Link text](https://example.com)
![Image alt text](/assets/images/photo.jpg)
```

### Blockquotes

```markdown
> This is a quote
```

### Code Blocks

````markdown
```python
def hello():
    print("Hello world")
```
````

---

## File Structure

```
elliottmattice.github.io/
├── _posts/              # Published blog posts
│   └── 2026-02-16-cmmc-upstream-signals.md
├── _drafts/             # Unpublished drafts
│   └── draft-post.md
├── _layouts/            # Page templates (don't edit unless redesigning)
│   ├── default.html
│   ├── post.html
│   └── page.html
├── assets/              # Media files
│   ├── css/
│   ├── images/          # Your images
│   ├── pdfs/            # Position papers
│   ├── frameworks/      # Framework PDFs
│   └── videos/          # Video files
├── index.html           # Homepage
├── analysis.html        # Blog index
├── speaking.md          # Speaking page
├── frameworks.md        # Frameworks page
├── about.md             # About page
├── _config.yml          # Site config
├── CNAME                # Custom domain
└── README.md            # This file
```

---

## Updating Pages

### Homepage (`index.html`)

Edit sections:
- Hero text
- About section
- Frameworks descriptions
- Contact information

### Static Pages

- **About:** `about.md`
- **Speaking:** `speaking.md`
- **Frameworks:** `frameworks.md`
- **Analysis (blog index):** `analysis.html`

Just edit the Markdown/HTML, commit, push. Live in 60 seconds.

---

## Adding Your Photo

**Replace placeholder on homepage and about page:**

1. **Add your headshot:**
   ```bash
   cp ~/headshot.jpg assets/images/elliott-mattice.jpg
   ```

2. **Update `index.html`** (line ~250):
   ```html
   <!-- Find this line: -->
   <img src="https://via.placeholder.com/400x400..." alt="Elliott Mattice" class="headshot">
   
   <!-- Change to: -->
   <img src="/assets/images/elliott-mattice.jpg" alt="Elliott Mattice" class="headshot">
   ```

3. **Update `about.md`** (line ~40):
   ```html
   <!-- Same change -->
   <img src="/assets/images/elliott-mattice.jpg" alt="Elliott Mattice">
   ```

4. **Commit and push:**
   ```bash
   git add assets/images/elliott-mattice.jpg index.html about.md
   git commit -m "Add headshot photo"
   git push
   ```

---

## Adding Hero Video

**1. Add video file:**

```bash
# Add your video to assets/videos/
cp ~/Blue-Tech-Video.webm assets/videos/
git add assets/videos/Blue-Tech-Video.webm
git commit -m "Add hero video"
git push
```

**2. Uncomment video code in `index.html`:**

Find this section (around line 220):

```html
<!-- Video Background (add your video file to assets/videos/) -->
<!-- <video autoplay muted loop playsinline class="hero-video-bg">
    <source src="/assets/videos/Blue-Tech-Futuristic-Artificial-Intelligence-Video.webm" type="video/webm">
</video> -->
```

Remove the comment tags:

```html
<!-- Video Background -->
<video autoplay muted loop playsinline class="hero-video-bg">
    <source src="/assets/videos/Blue-Tech-Video.webm" type="video/webm">
</video>
```

**3. Adjust video opacity if needed:**

In same file, find CSS around line 120:

```css
.hero-video-bg {
    opacity: 0.7; /* Adjust 0.3 to 0.9 */
}
```

---

## Local Preview (Optional)

**To preview changes before pushing:**

```bash
# Install Jekyll (one-time)
gem install jekyll bundler
bundle install

# Run local server
bundle exec jekyll serve

# Open browser to http://localhost:4000
# Edit files, see changes live
```

**Ctrl+C to stop server**

---

## Git Workflow

### Daily Content Publishing

```bash
# 1. Create/edit post
vim _posts/2026-02-21-new-analysis.md

# 2. Preview locally (optional)
bundle exec jekyll serve

# 3. Commit
git add .
git commit -m "New post: Analysis title"

# 4. Push (publishes to live site)
git push origin main

# 5. Site updates in 30-60 seconds
```

### Working on Multiple Drafts

```bash
# Keep drafts in _drafts/ folder
git add _drafts/draft-1.md _drafts/draft-2.md
git commit -m "Update drafts"
git push

# These won't appear on live site until moved to _posts/
```

---

## Customization

### Changing Colors

Edit `_layouts/default.html` around line 20:

```css
:root {
    --purple: #667eea;        /* Main accent color */
    --purple-light: #764ba2;  /* Hover states */
    /* ... other colors ... */
}
```

### Changing Fonts

Edit `_layouts/default.html` around line 15:

```html
<!-- Replace Google Fonts URL -->
<link href="https://fonts.googleapis.com/css2?family=YOUR-FONT&display=swap" rel="stylesheet">
```

Then update CSS variables:

```css
--font-display: 'Your Font', sans-serif;
--font-body: 'Your Font', sans-serif;
```

### Adding Navigation Links

Edit `_layouts/default.html` around line 80:

```html
<div class="nav-links">
    <a href="/analysis/" class="nav-link">Analysis</a>
    <a href="/frameworks/" class="nav-link">Frameworks</a>
    <a href="/speaking/" class="nav-link">Speaking</a>
    <a href="/your-new-page/" class="nav-link">New Page</a> <!-- Add this -->
</div>
```

---

## Troubleshooting

### Site not updating after push

**Clear GitHub cache:**
1. Go to repo → Actions
2. Find latest workflow run
3. Click "Re-run jobs"

**Or wait 2-3 minutes** - sometimes delayed

### Changes appear locally but not live

**Check GitHub Pages settings:**
1. Repo → Settings → Pages
2. Source: Deploy from branch `main`
3. Branch: `main` / `/ (root)`

### Images not loading

**Check file paths:**
- Correct: `/assets/images/photo.jpg`
- Wrong: `assets/images/photo.jpg` (missing leading `/`)

### Video not playing

**Browser compatibility:**
- Use `.webm` format (best browser support)
- Or provide multiple formats:
  ```html
  <source src="/assets/videos/video.webm" type="video/webm">
  <source src="/assets/videos/video.mp4" type="video/mp4">
  ```

---

## Performance Tips

### Image Optimization

**Before uploading images:**
- Resize to actual display size (max 1200px wide)
- Compress (use tinypng.com or similar)
- Target: Under 200KB per image

### PDF Optimization

**Compress PDFs before uploading:**
- Use Adobe Acrobat compression
- Or online tools like smallpdf.com
- Target: Under 5MB per PDF

---

## Security

### Keep Dependencies Updated

```bash
# Check for updates
bundle outdated

# Update
bundle update

# Commit updated Gemfile.lock
git add Gemfile.lock
git commit -m "Update dependencies"
git push
```

### Enable HTTPS

**Automatic with GitHub Pages + custom domain:**
1. Settings → Pages → Enforce HTTPS
2. Check the box
3. Wait 15 minutes

---

## Support

**Questions about:**
- Content strategy: contact@elliottmattice.work
- Technical issues: Check GitHub Pages documentation
- Customization: Edit files directly or reach out

---

## License

Content: © 2026 Elliott Mattice. All rights reserved.

Code: Feel free to fork and adapt for your own site.

---

**Last updated:** February 2026
