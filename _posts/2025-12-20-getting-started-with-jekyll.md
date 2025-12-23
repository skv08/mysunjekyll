---
layout: post
title: "Getting Started with Jekyll"
subtitle: "A beginner's guide to building static websites with Jekyll"
date: 2025-12-20 10:30:00 +0530
categories: [tutorial, web-development]
tags: [jekyll, static-site, ruby, github-pages]
---

## Introduction to Jekyll

Jekyll is a simple, blog-aware, static site generator perfect for personal, project, or organization sites. It takes text written in your favorite markup language and uses layouts to create a static website.

### Why Choose Jekyll?

There are several compelling reasons to use Jekyll for your website:

- **Simple**: No databases, comment moderation, or pesky updates to install
- **Static**: Markdown, Liquid, HTML & CSS go in. Static sites come out ready for deployment
- **Blog-aware**: Permalinks, categories, pages, posts, and custom layouts are all first-class citizens
- **Free Hosting**: Deploy to GitHub Pages for free hosting

### Installation

Installing Jekyll is straightforward if you have Ruby installed:

```bash
gem install jekyll bundler
jekyll new my-awesome-site
cd my-awesome-site
bundle exec jekyll serve
```

Your site will be available at `http://localhost:4000`.

### Basic Structure

A basic Jekyll site usually looks something like this:

```
.
├── _config.yml
├── _posts
│   └── 2025-12-20-welcome-to-jekyll.md
├── _layouts
│   └── default.html
├── _includes
│   └── header.html
└── index.html
```

### Creating Your First Post

Posts are stored in the `_posts` directory and follow a naming convention:

```
YEAR-MONTH-DAY-title.md
```

For example: `2025-12-20-my-first-post.md`

### Front Matter

Every post begins with YAML front matter:

```yaml
---
layout: post
title: "My First Post"
date: 2025-12-20 10:00:00 +0530
categories: blog
---
```

### Next Steps

Once you're comfortable with the basics:

1. Explore Jekyll themes
2. Learn about Liquid templating
3. Add plugins to extend functionality
4. Deploy to GitHub Pages

Happy Jekylling!

## Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages](https://pages.github.com/)
- [Jekyll Themes](https://jekyllthemes.io/)
