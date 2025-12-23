# Complete Walkthrough: Building a Modern Jekyll Website from Scratch

A comprehensive guide to creating a beautiful, feature-rich personal website using Jekyll and Beautiful Jekyll theme.

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Project Overview](#project-overview)
3. [Initial Setup](#initial-setup)
4. [Configuration](#configuration)
5. [Creating Pages](#creating-pages)
6. [Adding Blog Posts](#adding-blog-posts)
7. [Customization](#customization)
8. [Modern Features](#modern-features)
9. [Deployment](#deployment)
10. [Troubleshooting](#troubleshooting)
11. [Advanced Tips](#advanced-tips)

---

## Prerequisites

Before starting, ensure you have:

- **Ruby** (version 2.5 or higher)
  ```bash
  ruby --version
  ```

- **Bundler**
  ```bash
  gem install bundler
  ```

- **Git**
  ```bash
  git --version
  ```

- **GitHub Account** (for hosting)

- **Text Editor** (VS Code, Sublime Text, etc.)

---

## Project Overview

### What We Built

A modern personal website with:
- **Home Page**: Gradient hero section, feature cards, topic tags
- **About Me Page**: Professional bio and interests
- **Projects Page**: Portfolio showcase
- **Contact Page**: Social links and contact information
- **Blog**: 4 example posts with archive page
- **Responsive Design**: Mobile-friendly
- **Modern Color Scheme**: Dark navy navbar, vibrant colors
- **SEO Optimized**: Meta tags, keywords, sitemap

### Technology Stack

- **Jekyll**: Static site generator
- **Beautiful Jekyll Theme**: Base theme (v6.0.1)
- **GitHub Pages**: Free hosting
- **Markdown**: Content writing
- **Liquid**: Templating
- **HTML/CSS**: Customization

---

## Initial Setup

### Step 1: Create New Jekyll Site

```bash
# Install Jekyll
gem install jekyll bundler

# Create new site (optional if using existing directory)
jekyll new my-website
cd my-website
```

### Step 2: Initialize Git Repository

```bash
git init
git add .
git commit -m "Initial commit"
```

### Step 3: Create GitHub Repository

1. Go to GitHub.com
2. Click "New repository"
3. Name it (e.g., `my-website`)
4. Don't initialize with README
5. Copy the remote URL

```bash
git remote add origin https://github.com/yourusername/your-repo-name.git
git branch -M main
git push -u origin main
```

### Step 4: Install Beautiful Jekyll Theme

Edit `Gemfile`:

```ruby
source "https://rubygems.org"

gem "beautiful-jekyll-theme", "6.0.1"
gem "github-pages", group: :jekyll_plugins

group :jekyll_plugins do
  gem "jekyll-feed", "~> 0.12"
end

gem "csv", "~> 3.3"
```

Install dependencies:

```bash
bundle install
```

---

## Configuration

### Step 5: Configure `_config.yml`

Create/edit `_config.yml` with essential settings:

```yaml
############################
# --- Required options --- #
############################

# Name of website
title: Your Website Name

# Your name to show in the footer
author: Your Name

# Base URL configuration for GitHub Pages
url: "https://yourusername.github.io"
baseurl: "/your-repo-name"  # Leave empty if using yourusername.github.io

###############################################
# --- List of links in the navigation bar --- #
###############################################

navbar-links:
  About Me: "aboutme"
  Projects: "projects"
  Contact: "contact"
  Resources:
    - Beautiful Jekyll: "https://beautifuljekyll.com"
    - Learn Markdown: "https://www.markdowntutorial.com/"
    - Jekyll Docs: "https://jekyllrb.com/docs/"
    - GitHub Pages: "https://pages.github.com/"

#####################################
# --- Footer social media links --- #
#####################################

social-network-links:
  # email: "your-email@example.com"
  rss: true
  github: yourusername
  # twitter: yourhandle
  # linkedin: yourprofile

######################################
# --- Colours / background image --- #
######################################

# Modern color scheme
page-col: "#F8F9FA"
text-col: "#2C3E50"
link-col: "#3498DB"
hover-col: "#E74C3C"
navbar-col: "#2C3E50"
navbar-text-col: "#ECF0F1"
navbar-border-col: "#34495E"
footer-col: "#34495E"
footer-text-col: "#BDC3C7"
footer-link-col: "#3498DB"
footer-hover-col: "#E74C3C"

###########################
# --- General options --- #
###########################

# SEO keywords
keywords: "your name,web development,blog,programming"

# RSS description
rss-description: Your site description for RSS feeds

# Timezone
timezone: "Your/Timezone"  # e.g., "America/New_York", "Asia/Kolkata"

# Date format
date_format: "%B %-d, %Y"

# Markdown and syntax highlighting
markdown: kramdown
highlighter: rouge
permalink: /:year-:month-:day-:title/
paginate: 5
```

---

## Creating Pages

### Step 6: Create About Me Page

Create `aboutme.html`:

```html
---
layout: page
title: About Me
permalink: /aboutme/
---

<div class="aboutme-section">
  <h1>About Me</h1>

  <p>Welcome! I'm [Your Name], and this is my personal space on the web.</p>

  <h2>Who I Am</h2>
  <p>
    Brief introduction about yourself...
  </p>

  <h2>What I Do</h2>
  <p>
    Your professional information...
  </p>

  <h2>My Interests</h2>
  <ul>
    <li>Interest 1</li>
    <li>Interest 2</li>
    <li>Interest 3</li>
  </ul>

  <h2>Get In Touch</h2>
  <p>
    Connect with me on <a href="https://github.com/yourusername">GitHub</a>.
  </p>
</div>
```

### Step 7: Create Projects Page

Create `projects.html`:

```html
---
layout: page
title: Projects
subtitle: My work and experiments
---

<div class="projects-section">
  <h2>Featured Projects</h2>

  <div class="project-item">
    <h3>Project Name</h3>
    <p class="project-meta">
      <strong>Tech Stack:</strong> Technologies used
    </p>
    <p>
      Project description...
    </p>
    <p>
      <a href="project-url" target="_blank" class="btn btn-primary">View Project</a>
    </p>
  </div>

  <!-- Add more projects -->
</div>

<style>
.project-item {
  margin: 2rem 0;
  padding: 1.5rem;
  background: #f8f9fa;
  border-radius: 8px;
}

.project-meta {
  color: #666;
  font-style: italic;
}

.btn-primary {
  display: inline-block;
  padding: 0.5rem 1rem;
  background: #008AFF;
  color: white;
  text-decoration: none;
  border-radius: 4px;
}
</style>
```

### Step 8: Create Contact Page

Create `contact.html`:

```html
---
layout: page
title: Contact
subtitle: Let's connect
---

<div class="contact-section">
  <h2>Get In Touch</h2>

  <p>I'd love to hear from you!</p>

  <div class="contact-methods">
    <div class="contact-item">
      <strong>GitHub:</strong>
      <a href="https://github.com/yourusername">@yourusername</a>
    </div>

    <div class="contact-item">
      <strong>Email:</strong>
      <p>your-email@example.com</p>
    </div>
  </div>
</div>

<style>
.contact-item {
  margin: 1.5rem 0;
  padding: 1rem;
  background: #f8f9fa;
  border-radius: 8px;
}
</style>
```

### Step 9: Create Blog Posts Archive

Create `posts.html`:

```html
---
layout: page
title: Blog Posts
subtitle: Articles and tutorials
---

<div class="posts-list">
  {% for post in site.posts %}
  <article class="post-preview">
    <a href="{{ post.url | relative_url }}">
      <h2 class="post-title">{{ post.title }}</h2>
    </a>

    {% if post.subtitle %}
    <h3 class="post-subtitle">{{ post.subtitle }}</h3>
    {% endif %}

    <p class="post-meta">
      Posted on {{ post.date | date: "%B %-d, %Y" }}
    </p>

    <div class="post-entry">
      {{ post.excerpt | strip_html | xml_escape | truncatewords: 50 }}
      <a href="{{ post.url | relative_url }}" class="post-read-more">Read More &rarr;</a>
    </div>

    {% if post.tags.size > 0 %}
    <div class="blog-tags">
      Tags:
      {% for tag in post.tags %}
      <a href="{{ '/tags' | relative_url }}#{{ tag | slugify }}">{{ tag }}</a>
      {% endfor %}
    </div>
    {% endif %}
  </article>
  {% endfor %}
</div>

<style>
.post-preview {
  background: white;
  padding: 2rem;
  margin-bottom: 2rem;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.08);
}

.post-title {
  color: #2C3E50;
}

.post-read-more {
  color: #3498DB;
  font-weight: 600;
}
</style>
```

### Step 10: Create Enhanced Home Page

Create `index.html`:

```html
---
layout: home
title: Welcome
subtitle: Your tagline here
---

<div class="intro-section">
  <div class="intro-card">
    <h2>👋 Hello, I'm [Your Name]</h2>
    <p>
      Welcome message...
    </p>
  </div>
</div>

<div class="features-grid">
  <div class="feature-card">
    <div class="feature-icon">📝</div>
    <h3>Blog Posts</h3>
    <p>Technical articles and tutorials</p>
    <a href="{{ '/posts' | relative_url }}" class="feature-link">Read Articles →</a>
  </div>

  <div class="feature-card">
    <div class="feature-icon">🚀</div>
    <h3>Projects</h3>
    <p>My latest work and experiments</p>
    <a href="{{ '/projects' | relative_url }}" class="feature-link">View Projects →</a>
  </div>

  <div class="feature-card">
    <div class="feature-icon">💡</div>
    <h3>About Me</h3>
    <p>Learn more about my background</p>
    <a href="{{ '/aboutme' | relative_url }}" class="feature-link">Learn More →</a>
  </div>

  <div class="feature-card">
    <div class="feature-icon">📬</div>
    <h3>Get In Touch</h3>
    <p>Let's connect!</p>
    <a href="{{ '/contact' | relative_url }}" class="feature-link">Contact Me →</a>
  </div>
</div>

<style>
.intro-card {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  color: white;
  padding: 2.5rem;
  border-radius: 12px;
  box-shadow: 0 10px 30px rgba(0,0,0,0.1);
  margin-bottom: 2rem;
}

.features-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
  gap: 1.5rem;
  margin: 3rem 0;
}

.feature-card {
  background: white;
  padding: 2rem;
  border-radius: 10px;
  box-shadow: 0 5px 15px rgba(0,0,0,0.08);
  transition: transform 0.3s;
  border-top: 4px solid #3498DB;
}

.feature-card:hover {
  transform: translateY(-5px);
}

.feature-icon {
  font-size: 3rem;
  text-align: center;
  margin-bottom: 1rem;
}

.feature-link {
  color: #3498DB;
  font-weight: 600;
  text-decoration: none;
}
</style>
```

---

## Adding Blog Posts

### Step 11: Create Blog Posts

Create `_posts` directory and add posts with naming: `YYYY-MM-DD-title.md`

Example: `_posts/2025-12-24-my-first-post.md`

```markdown
---
layout: post
title: "Your Post Title"
subtitle: "Optional subtitle"
date: 2025-12-24 12:00:00 +0530
categories: [category1, category2]
tags: [tag1, tag2, tag3]
---

## Introduction

Your content here...

### Subheading

More content...

```code
Code blocks work too!
```

## Conclusion

Final thoughts...
```

### Example Blog Post Topics

1. **Getting Started with Jekyll**
2. **Introduction to DevSecOps**
3. **My Development Setup**
4. **Web Development Best Practices**

---

## Customization

### Step 12: Modern Color Schemes

Choose from these modern palettes:

**Dark & Professional**
```yaml
page-col: "#F8F9FA"
text-col: "#2C3E50"
link-col: "#3498DB"
navbar-col: "#2C3E50"
navbar-text-col: "#ECF0F1"
```

**Vibrant & Energetic**
```yaml
page-col: "#FFFFFF"
text-col: "#1A1A1A"
link-col: "#FF6B6B"
navbar-col: "#4ECDC4"
navbar-text-col: "#FFFFFF"
```

**Minimal & Clean**
```yaml
page-col: "#FFFFFF"
text-col: "#333333"
link-col: "#0066CC"
navbar-col: "#F5F5F5"
navbar-text-col: "#333333"
```

### Step 13: Add Custom CSS

Create custom styles:

```yaml
# In _config.yml
site-css:
  - "/assets/css/custom-styles.css"
```

Create `assets/css/custom-styles.css`:

```css
/* Custom animations */
.feature-card {
  transition: all 0.3s ease;
}

.feature-card:hover {
  transform: translateY(-5px) scale(1.02);
  box-shadow: 0 15px 30px rgba(0,0,0,0.15);
}

/* Gradient text */
.gradient-text {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  -webkit-background-clip: text;
  -webkit-text-fill-color: transparent;
}

/* Custom scrollbar */
::-webkit-scrollbar {
  width: 10px;
}

::-webkit-scrollbar-track {
  background: #f1f1f1;
}

::-webkit-scrollbar-thumb {
  background: #3498DB;
  border-radius: 5px;
}

/* Responsive images */
img {
  max-width: 100%;
  height: auto;
  border-radius: 8px;
}
```

---

## Modern Features

### Step 14: Enable Google Analytics

1. Sign up at [Google Analytics](https://analytics.google.com/)
2. Create a property
3. Get Measurement ID (G-XXXXXXXXXX)

In `_config.yml`:
```yaml
gtag: "G-XXXXXXXXXX"
```

### Step 15: Enable Comments with Utterances

1. Enable Issues in your GitHub repository
2. Install [Utterances app](https://github.com/apps/utterances)
3. Configure in `_config.yml`:

```yaml
utterances:
  repository: "username/repo-name"
  issue-term: title
  theme: github-light
  label: blog-comments
```

### Step 16: Add Search Functionality

Enable post search:
```yaml
post_search: true
```

### Step 17: Social Sharing Buttons

```yaml
share-links-active:
  twitter: true
  facebook: true
  linkedin: true
```

### Step 18: RSS Feed

Automatically generated at `/feed.xml`

Configure description:
```yaml
rss-description: "Your site description"
```

### Step 19: SEO Optimization

```yaml
# Keywords
keywords: "your,keywords,here"

# Open Graph tags (automatic with Beautiful Jekyll)
# Just ensure title and description are set

# Sitemap (automatic with jekyll-sitemap plugin)
plugins:
  - jekyll-sitemap
```

---

## Deployment

### Step 20: Deploy to GitHub Pages

#### Method 1: Repository Settings (Easiest)

1. Push your code to GitHub
2. Go to repository Settings
3. Navigate to Pages (left sidebar)
4. Under "Build and deployment":
   - Source: Deploy from a branch
   - Branch: `main` / `(root)`
5. Click Save
6. Wait 2-3 minutes
7. Visit: `https://username.github.io/repo-name`

#### Method 2: GitHub Actions (Advanced)

Create `.github/workflows/pages.yml`:

```yaml
name: Deploy Jekyll site to Pages

on:
  push:
    branches: ["main"]
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: '3.1'
          bundler-cache: true
      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v4
      - name: Build with Jekyll
        run: bundle exec jekyll build
        env:
          JEKYLL_ENV: production
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```

### Step 21: Custom Domain (Optional)

1. Buy a domain (Namecheap, Google Domains, etc.)
2. Add DNS records:
   ```
   Type: A
   Host: @
   Value: 185.199.108.153
   Value: 185.199.109.153
   Value: 185.199.110.153
   Value: 185.199.111.153

   Type: CNAME
   Host: www
   Value: username.github.io
   ```
3. Create `CNAME` file in root:
   ```
   yourdomain.com
   ```
4. Update `_config.yml`:
   ```yaml
   url: "https://yourdomain.com"
   baseurl: ""
   ```

---

## Troubleshooting

### Common Issues

#### Issue 1: Site Not Building
```bash
# Check for errors
bundle exec jekyll build --verbose

# Common fixes:
bundle update
bundle clean --force
bundle install
```

#### Issue 2: Links Not Working Locally
- Use `bundle exec jekyll serve`
- Visit `http://127.0.0.1:4000/baseurl/`
- Check baseurl in _config.yml

#### Issue 3: Missing Include File
```
Error: Could not locate the included file 'filename.html'
```
**Fix**: Check `_includes` directory for typos

#### Issue 4: Liquid Exception
- Check Liquid syntax in templates
- Ensure proper `{% %}` and `{{ }}` usage

#### Issue 5: GitHub Pages Not Updating
- Check repository Settings → Pages
- View deployment status in Actions tab
- Clear browser cache
- Wait 5-10 minutes for first deployment

### Performance Tips

1. **Optimize Images**
   ```bash
   # Use compressed images
   # Recommended: TinyPNG, ImageOptim
   ```

2. **Enable Caching**
   ```yaml
   # In _config.yml
   sass:
     style: compressed
   ```

3. **Minimize Plugins**
   - Only use essential plugins
   - Each plugin adds build time

---

## Advanced Tips

### Tip 1: Custom 404 Page

Create `404.html`:
```html
---
layout: default
title: 404 - Page not found
permalink: /404.html
---

<div class="text-center">
  <h1>Whoops, this page doesn't exist.</h1>
  <img src="/assets/img/404.jpg" alt="404" />
  <p><a href="/">Return Home</a></p>
</div>
```

### Tip 2: Reading Time Indicator

In post layout:
```liquid
{% assign words = content | number_of_words %}
{% if words < 360 %}
  1 min read
{% else %}
  {{ words | divided_by:180 }} min read
{% endif %}
```

### Tip 3: Related Posts

```liquid
<h3>Related Posts</h3>
<ul>
  {% for post in site.related_posts limit:3 %}
    <li><a href="{{ post.url }}">{{ post.title }}</a></li>
  {% endfor %}
</ul>
```

### Tip 4: Dark Mode Toggle

Add JavaScript:
```javascript
// Toggle dark mode
const toggleDarkMode = () => {
  document.body.classList.toggle('dark-mode');
  localStorage.setItem('darkMode',
    document.body.classList.contains('dark-mode'));
};

// Load preference
if (localStorage.getItem('darkMode') === 'true') {
  document.body.classList.add('dark-mode');
}
```

### Tip 5: Progressive Web App (PWA)

Create `manifest.json`:
```json
{
  "name": "Your Website",
  "short_name": "YourSite",
  "start_url": "/",
  "display": "standalone",
  "background_color": "#ffffff",
  "theme_color": "#3498DB",
  "icons": [
    {
      "src": "/assets/img/icon-192.png",
      "sizes": "192x192",
      "type": "image/png"
    }
  ]
}
```

---

## Checklist: Before Going Live

- [ ] Update all placeholder content
- [ ] Add real social media links
- [ ] Set up Google Analytics
- [ ] Enable comment system
- [ ] Test all links
- [ ] Optimize images
- [ ] Add favicon
- [ ] Test on mobile devices
- [ ] Check SEO with [Google Search Console](https://search.google.com/search-console)
- [ ] Set up RSS feed
- [ ] Create at least 3-5 blog posts
- [ ] Add contact information
- [ ] Test site speed with [PageSpeed Insights](https://pagespeed.web.dev/)
- [ ] Proofread all content
- [ ] Set up custom domain (optional)

---

## Maintenance

### Regular Updates

```bash
# Update dependencies
bundle update

# Check for security issues
bundle audit

# Update GitHub Pages gem
bundle update github-pages
```

### Backup Strategy

1. **Git Repository**: Your primary backup
2. **Local Clone**: Keep local copy
3. **Export Content**: Periodically export posts

### Monitoring

1. **Google Analytics**: Track visitors
2. **Google Search Console**: Monitor SEO
3. **GitHub Issues**: Track comments (if using Utterances)

---

## Resources

### Documentation
- [Jekyll Docs](https://jekyllrb.com/docs/)
- [Beautiful Jekyll](https://beautifuljekyll.com/)
- [GitHub Pages](https://pages.github.com/)
- [Liquid Templating](https://shopify.github.io/liquid/)

### Tools
- [Markdown Guide](https://www.markdownguide.org/)
- [Jekyll Themes](https://jekyllthemes.io/)
- [Font Awesome Icons](https://fontawesome.com/)
- [Google Fonts](https://fonts.google.com/)

### Communities
- [Jekyll Talk](https://talk.jekyllrb.com/)
- [r/Jekyll](https://reddit.com/r/Jekyll)
- [Stack Overflow](https://stackoverflow.com/questions/tagged/jekyll)

---

## Summary of What We Built

### Pages Created
1. **Home** (`index.html`) - Gradient hero, feature cards
2. **About Me** (`aboutme.html`) - Bio and interests
3. **Projects** (`projects.html`) - Portfolio showcase
4. **Contact** (`contact.html`) - Social links
5. **Posts Archive** (`posts.html`) - Blog listing

### Blog Posts
1. Welcome to My Blog (Introduction)
2. Getting Started with Jekyll (Tutorial)
3. Introduction to DevSecOps (Technical)
4. My Development Setup (Personal)

### Features Implemented
- ✅ Modern color scheme (dark navbar, vibrant accents)
- ✅ Responsive design
- ✅ SEO optimization
- ✅ RSS feed
- ✅ Social media integration
- ✅ Blog with tags and categories
- ✅ Hover effects and animations
- ✅ Mobile-friendly navigation
- ✅ Comment system ready (Utterances)
- ✅ Analytics ready (Google Analytics)

### Design Elements
- Gradient backgrounds
- Card-based layouts
- Smooth transitions
- Modern color palette
- Clean typography
- Intuitive navigation

---

## Next Steps

1. **Content Creation**: Write more blog posts regularly
2. **Project Showcase**: Add real projects with screenshots
3. **Networking**: Share on social media
4. **SEO**: Submit to search engines
5. **Analytics**: Monitor and improve
6. **Community**: Engage with readers through comments
7. **Updates**: Keep dependencies updated

---

## Conclusion

You now have a complete, modern, feature-rich personal website built with Jekyll! This walkthrough covered everything from initial setup to deployment, including modern features and best practices.

Remember:
- **Content is King**: Regular, quality content matters most
- **Keep Learning**: Web development evolves constantly
- **Engage**: Respond to comments and feedback
- **Iterate**: Continuously improve based on analytics

Happy building! 🚀

---

**Created**: December 2025
**Version**: 1.0
**License**: Free to use and modify

---

## Quick Commands Reference

```bash
# Local development
bundle exec jekyll serve

# Build site
bundle exec jekyll build

# Update dependencies
bundle update

# Clean build
bundle exec jekyll clean

# Serve with drafts
bundle exec jekyll serve --drafts

# Serve on specific port
bundle exec jekyll serve --port 4001
```

## File Structure Reference

```
my-website/
├── _config.yml           # Main configuration
├── _includes/            # Reusable components
├── _layouts/             # Page templates
├── _posts/              # Blog posts
├── _data/               # Data files
├── assets/
│   ├── css/             # Stylesheets
│   ├── js/              # JavaScript
│   └── img/             # Images
├── aboutme.html         # About page
├── projects.html        # Projects page
├── contact.html         # Contact page
├── posts.html           # Posts archive
├── index.html           # Homepage
├── 404.html             # Error page
├── Gemfile              # Ruby dependencies
└── README.md            # Documentation
```

---

**End of Walkthrough**
