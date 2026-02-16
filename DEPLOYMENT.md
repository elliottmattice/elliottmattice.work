# 🚀 Deployment Quick Start

**Get your site live in 10 minutes.**

---

## Step 1: Create GitHub Repository

1. **Go to:** github.com
2. **Click:** New repository (green button)
3. **Repository name:** `YOUR-USERNAME.github.io`
   - Example: `elliottmattice.github.io`
   - Must match this pattern exactly
4. **Public** (required for free GitHub Pages)
5. **Do NOT** initialize with README (you already have one)
6. **Create repository**

---

## Step 2: Upload Your Site

**Option A: Using GitHub Web Interface (Easiest)**

1. **In your new repo**, click "uploading an existing file"
2. **Drag all files from this folder** into the upload box
   - Include hidden files (`.gitignore`, etc.)
3. **Commit message:** "Initial site deployment"
4. **Commit changes**

**Option B: Using Git Command Line**

```bash
cd /path/to/this/folder

git init
git add .
git commit -m "Initial site deployment"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io.git
git push -u origin main
```

---

## Step 3: Enable GitHub Pages

1. **Go to:** Repo → Settings → Pages (left sidebar)
2. **Source:** Deploy from a branch
3. **Branch:** main
4. **Folder:** / (root)
5. **Save**

**Your site is now live at:**
`https://YOUR-USERNAME.github.io`

*Wait 2-3 minutes for first deployment*

---

## Step 4: Add Custom Domain (elliottmattice.work)

### A. In GitHub:

1. **Settings → Pages**
2. **Custom domain:** `elliottmattice.work`
3. **Save**
4. **Wait for DNS check** (may show error initially - this is normal)

### B. In Your Domain Registrar (Dreamhost, etc.):

**Add these DNS records:**

```
Type: CNAME
Name: www
Value: YOUR-USERNAME.github.io
TTL: 3600

Type: A
Name: @
Value: 185.199.108.153
TTL: 3600

Type: A
Name: @
Value: 185.199.109.153
TTL: 3600

Type: A
Name: @
Value: 185.199.110.153
TTL: 3600

Type: A
Name: @
Value: 185.199.111.153
TTL: 3600
```

### C. Wait for DNS Propagation:

- **Time:** 15 minutes to 24 hours (usually 30 min)
- **Check status:** dnschecker.org

### D. Enable HTTPS:

1. **Settings → Pages**
2. **Enforce HTTPS** (check the box)
3. **Wait 15 minutes** for certificate

---

## Step 5: Verify Everything Works

**Visit these URLs:**

- ✅ Homepage: https://elliottmattice.work
- ✅ Analysis: https://elliottmattice.work/analysis/
- ✅ Speaking: https://elliottmattice.work/speaking/
- ✅ Frameworks: https://elliottmattice.work/frameworks/
- ✅ About: https://elliottmattice.work/about/
- ✅ Sample post: https://elliottmattice.work/cmmc-upstream-signals/

**All should load with:**
- Your design (dark theme, purple accents, grain texture)
- Fast performance (<1 second)
- HTTPS (green lock icon)

---

## Step 6: Customize Your Site

### Replace Placeholder Photo:

**File:** `index.html` and `about.md`

**Find:**
```html
<img src="https://via.placeholder.com/400x400..." 
```

**Replace with:**
```html
<img src="/assets/images/elliott-mattice.jpg"
```

**Then upload your photo:**
```bash
cp ~/your-headshot.jpg assets/images/elliott-mattice.jpg
git add assets/images/elliott-mattice.jpg index.html about.md
git commit -m "Add headshot"
git push
```

### Update Contact Info:

**Files to check:**
- `index.html` (contact section)
- `about.md` (contact section)
- `_layouts/default.html` (footer)

**Make sure:**
- Email address is correct
- Phone number is correct
- LinkedIn URL is correct

---

## Step 7: Publish Your First Post

**Create new file in IDE:**

```markdown
_posts/2026-02-20-your-first-post.md
```

**Content:**

```markdown
---
title: "Your First Analysis Post"
date: 2026-02-20
category: analysis
excerpt: "Brief description here"
---

Your content here...
```

**Publish:**

```bash
git add _posts/2026-02-20-your-first-post.md
git commit -m "First post"
git push
```

**Live in 60 seconds at:**
`https://elliottmattice.work/your-first-post/`

---

## 🎯 You're Live!

**Your site is now:**
- ✅ Hosted on GitHub Pages (free, fast, reliable)
- ✅ Custom domain (elliottmattice.work)
- ✅ HTTPS enabled
- ✅ Ready for content
- ✅ $0/month hosting cost

**Next steps:**
1. Read `README.md` for full documentation
2. Add your headshot photo
3. Publish your first real analysis post
4. Share on LinkedIn

---

## 🆘 Troubleshooting

**Site not loading?**
- Wait 5 minutes, try again
- Check Settings → Pages shows "Your site is live"
- Clear browser cache (Ctrl+Shift+R)

**Custom domain not working?**
- DNS takes 15-60 minutes
- Check dnschecker.org
- Verify DNS records in your registrar

**Images not showing?**
- Check file path starts with `/` 
- Example: `/assets/images/photo.jpg` (correct)
- Example: `assets/images/photo.jpg` (wrong)

**Changes not appearing?**
- Wait 2-3 minutes after push
- Check Actions tab for build status
- Hard refresh browser (Ctrl+Shift+R)

---

**Questions?** See `README.md` or email contact@elliottmattice.work

**Congratulations! Your professional site is live. 🎉**
