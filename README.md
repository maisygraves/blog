# b-Log Source Code

The source code for my personal blog. Built with Jekyll, hosted via GitHub Pages, and crafted using custom HTML/CSS and Liquid templates.

## Tech Stack

- Static Site Generator: Jekyll
- Hosting: GitHub Pages
- Templating: Liquid
- Styling: Custom CSS (located in assets/css/)

## Local Development

To run this blog locally and preview changes before pushing to GitHub:

1. Install Ruby version 2.7.0 or higher for your OS
2. Install Jekyll from the terminal
3. Load site directory from GitHub 
4. build static pages to /_static/ and run on local server http://localhost:4000
```
jekyll serve
```

## Content Workflow

**Creating a Post**

1. Add a new Markdown file to the _posts/ folder.
2. Naming Convention: YYYY-MM-DD-title-of-post.md (Crucial for Jekyll to recognize the date).
3. Frontmatter Template:
```
YAML
---
title: "Your Post Title"
category: [note OR project]
link: [GitHub repository]
date: YYYY-MM-DD 
skills: [array of data science skills from Grolemund framework]
tools: [array of tools in tech stack]
---
```

**Updating Layouts**

- HTML Structure: Modify files in _layouts/ (e.g., default.html, post.html).
- Reusable Components: Update navigation or footers in _includes/.
- Global Settings: Change the site title or description in _config.yml.

## Deployment

Since this is hosted on GitHub Pages, deployment is simple:
- Any changes pushed to the main branch are automatically built and deployed by GitHub Actions.
- *Note:* If the site fails to build, check the "Actions" tab in this repository for error logs.

## Project Structure

_data/: Where the site's YAML data files live.

_posts/: Where the blog articles live.

_layouts/: The HTML templates (using Liquid).

_includes/: Reusable HTML snippets.

assets/: Images and CSS files.

_config.yml: Global configuration and variables.

Collections:
    _skills/
    _tools/

Site pages:
    index.html (home page)
    notes.html
    projects.html
    resources.html