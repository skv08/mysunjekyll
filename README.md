# Sunil's Personal Website

A Jekyll-powered personal website built with the Beautiful Jekyll theme. Features a blog, project portfolio, and contact page.

## Features

- **Blog**: Share articles and tutorials on web development, DevSecOps, and technology
- **Projects Page**: Showcase your work and experiments
- **Contact Page**: Connect with visitors
- **Responsive Design**: Mobile-friendly layout
- **SEO Optimized**: Meta tags, keywords, and sitemap
- **RSS Feed**: Automatic feed generation for blog posts
- **Social Media Integration**: Links to GitHub and other platforms

## Local Development

### Prerequisites

- Ruby (version 2.5 or higher)
- Bundler (`gem install bundler`)

### Setup

1. Clone the repository:
   ```bash
   git clone <your-repo-url>
   cd mysunsite
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Run the local server:
   ```bash
   bundle exec jekyll serve
   ```

4. Visit `http://localhost:4000` in your browser

### Building the Site

To build the site without serving:
```bash
bundle exec jekyll build
```

The built site will be in the `_site` directory.

## Configuration

### Basic Settings

Edit `_config.yml` to customize:

- **Site title and author**: Lines 13-16
- **Navigation menu**: Lines 22-28
- **Social media links**: Lines 52-60
- **Color scheme**: Lines 139-149

### Enable Optional Features

#### Google Analytics

1. Sign up at [Google Analytics](https://analytics.google.com/)
2. Create a property and get your Measurement ID
3. Uncomment and update line 180 in `_config.yml`:
   ```yaml
   gtag: "G-XXXXXXXXXX"
   ```

#### Utterances Comments

1. Enable Issues in your GitHub repository settings
2. Install the [Utterances app](https://github.com/apps/utterances)
3. Uncomment and update lines 220-224 in `_config.yml`:
   ```yaml
   utterances:
     repository: "skv08/your-repo-name"
     issue-term: title
     theme: github-light
     label: blog-comments
   ```

## Creating Content

### Blog Posts

Create new posts in the `_posts` directory with the naming format:
```
YYYY-MM-DD-title-of-post.md
```

Example front matter:
```yaml
---
layout: post
title: "Your Post Title"
subtitle: "Optional subtitle"
date: 2025-12-24 12:00:00 +0530
categories: [category1, category2]
tags: [tag1, tag2, tag3]
---

Your content here...
```

### Pages

Create new pages as `.html` or `.md` files in the root directory. Add them to the navigation menu in `_config.yml`.

## Deployment

### GitHub Pages

1. Push your code to GitHub
2. Go to repository Settings → Pages
3. Select source: `main` branch
4. Your site will be published at `https://username.github.io/repository-name`

### Custom Domain

1. Add a `CNAME` file with your domain name
2. Configure DNS settings with your domain provider
3. Update `url-pretty` in `_config.yml`

## Customization

### Colors

Edit the color variables in `_config.yml` (lines 139-149):
- `page-col`: Page background
- `text-col`: Main text color
- `link-col`: Link color
- `navbar-col`: Navigation bar background
- And more...

### Fonts and Styles

Add custom CSS in `assets/css/` and reference in `_config.yml`:
```yaml
site-css:
  - "/assets/css/custom-styles.css"
```

## Theme

This site uses [Beautiful Jekyll](https://beautifuljekyll.com/) version 6.0.1. For theme documentation and updates, visit the [Beautiful Jekyll repository](https://github.com/daattali/beautiful-jekyll).

## License

This project is open source. The Beautiful Jekyll theme is MIT licensed.

## Contact

- **GitHub**: [@skv08](https://github.com/skv08)
- **Website**: [skv08.github.io](https://skv08.github.io)

## Acknowledgments

- Built with [Jekyll](https://jekyllrb.com/)
- Theme by [Beautiful Jekyll](https://beautifuljekyll.com/)
- Hosted on [GitHub Pages](https://pages.github.com/)
