# Peros Skolteknik Hugo Website

This is a Hugo-based static site generator for the Peros Skolteknik website.

## Directory Structure

```
hugo-site/
├── content/           # Markdown/HTML content files for each page
├── layouts/           # Hugo templates
│   ├── _default/      # Default templates
│   │   ├── baseof.html   # Base template with header/footer
│   │   └── single.html    # Single page template
│   ├── partials/      # Reusable template parts
│   │   ├── header.html    # Header with navigation
│   │   └── footer.html    # Footer
│   └── index.html     # Homepage template
├── static/            # Static assets (CSS, JS, images)
│   ├── dom0/          # Bootstrap, jQuery, etc.
│   ├── template/      # Custom CSS and images
│   ├── files/         # Content files and images
│   ├── CNAME          # GitHub Pages CNAME file
│   └── robots.txt     # Robots.txt file
├── public/            # Generated site (created after build)
└── hugo.toml          # Hugo configuration file
```

## Building the Site

To build the site, run:

```bash
cd hugo-site
hugo
```

The generated HTML files will be in the `public/` directory.

## Development Server

To run a local development server with live reload:

```bash
cd hugo-site
hugo server -D
```

Then open http://localhost:1313 in your browser.

## Configuration

### Site Settings

Edit `hugo.toml` to configure:
- `baseURL`: Set to your domain (e.g., "https://www.skolteknik.com/")
- `title`: Site title
- Contact information (phone, email, address)
- Menu items and their order

### Adding/Editing Pages

Content files are in the `content/` directory. Each page has:
- Front matter (YAML/TOML metadata at the top)
- HTML content

Example:
```yaml
---
title: "Page Title"
description: "Page description"
---

<div class="content">
  <!-- Your HTML content here -->
</div>
```

## Deployment

### GitHub Pages

1. Ensure `CNAME` file in `static/` contains your domain
2. Build the site: `hugo`
3. Deploy the `public/` directory to GitHub Pages

### Other Hosting

Upload the contents of the `public/` directory to your web server.

## Important Notes

- The original HTML structure has been preserved
- All static assets (CSS, JS, images) are in the `static/` directory
- Navigation menu is automatically generated from `hugo.toml`
- Update the `baseURL` in `hugo.toml` to match your production domain

## Warnings

When building, you may see warnings about "duplicate menu entry". This is because menu items are defined in `hugo.toml`. You can safely ignore these warnings or remove the `menu:` sections from individual content files' front matter.
