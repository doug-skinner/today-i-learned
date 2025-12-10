# Contributing to Today I Learned

This guide provides detailed information on how to add posts, customize the site, and publish to GitHub Pages.

## 📝 Adding New TIL Posts

### File Naming Convention

Create a new file in the `_posts` directory with this format:
```
YYYY-MM-DD-title-with-hyphens.md
```

Example: `2025-12-10-biome-replaces-eslint-prettier.md`

### Post Template

```markdown
---
layout: post
title: "Your TIL Title"
date: YYYY-MM-DD
category: CategoryName
tags: [tag1, tag2, tag3]
---

Brief introduction to what you learned.

## The Problem (or Background)

Explain the context or problem that led to this learning.

## The Solution (or Key Learning)

Explain the solution or key concept you learned.

\`\`\`language
// Code example
\`\`\`

## Additional Notes

Any additional context, gotchas, or related information.
```

### Example Post

```markdown
---
layout: post
title: "Array.from() Can Take a Map Function"
date: 2025-01-20
category: JavaScript
tags: [javascript, arrays]
---

I discovered that Array.from() accepts a second parameter—a map function!

## The Old Way

\`\`\`javascript
const numbers = Array.from({length: 5}, (_, i) => i);
// Instead of:
const numbers = Array.from({length: 5}).map((_, i) => i);
\`\`\`

More efficient and cleaner!
```

### Available Categories

Categories are automatically generated from your posts' front matter. Common categories include:
- JavaScript
- Python
- CSS
- Git
- Terminal
- Tooling
- Database

Add any category you'd like—they'll appear automatically on the categories page.

## 🚀 Publishing to GitHub Pages

### Initial Setup

1. **Push your code to GitHub**:
   ```bash
   git add .
   git commit -m "Initial Jekyll site setup"
   git push origin main
   ```

2. **Enable GitHub Pages**:
   - Go to: https://github.com/doug-skinner/today-i-learned/settings/pages
   - Under **Build and deployment**:
     - Set **Source** to **"GitHub Actions"**
   - Save the changes

3. **Wait for deployment**:
   - Go to the **Actions** tab: https://github.com/doug-skinner/today-i-learned/actions
   - Watch the "Deploy Jekyll site to Pages" workflow run
   - Takes about 1-2 minutes

4. **Visit your site**:
   - Live at: https://doug-skinner.github.io/today-i-learned/

### Automatic Deployments

Once set up, every push to the `main` branch automatically triggers a rebuild and deployment. No manual steps needed!

## 💻 Local Development

### Prerequisites

- Ruby 2.7 or higher
- Bundler (`gem install bundler`)

### Setup

1. Clone the repository:
   ```bash
   git clone https://github.com/doug-skinner/today-i-learned.git
   cd today-i-learned
   ```

2. Install dependencies:
   ```bash
   bundle install
   ```

3. Run the site locally:
   ```bash
   bundle exec jekyll serve
   ```

4. Visit: http://localhost:4000/today-i-learned

5. The site will auto-rebuild when you edit files (except `_config.yml`)

## 📂 Repository Structure

```
today-i-learned/
├── _config.yml              # Jekyll configuration
├── _layouts/                # Layout templates
│   ├── default.html        # Base layout with header/footer
│   └── post.html           # Individual post layout
├── _posts/                 # Your TIL entries (markdown files)
│   └── YYYY-MM-DD-title.md
├── assets/
│   └── css/
│       └── main.css        # Site styles
├── .github/
│   └── workflows/
│       └── jekyll.yml      # GitHub Actions deployment workflow
├── index.html              # Homepage (recent posts)
├── categories.html         # Browse posts by category
├── archive.html            # Full chronological archive
├── Gemfile                 # Ruby dependencies
├── README.md               # Quick start guide
└── CONTRIBUTING.md         # This file
```

## 🎨 Customization

### Update Site Information

Edit `_config.yml` to change:
- **title**: Site title
- **description**: Tagline
- **author**: Your name
- **email**: Your email
- **url**: Base URL (https://doug-skinner.github.io)
- **baseurl**: Repo name (/today-i-learned)
- **timezone**: Your timezone

### Modify Styles

Edit `assets/css/main.css` to customize the appearance.

**CSS Variables** (in `:root`):
```css
--primary-color: #2c3e50;      /* Headings, links */
--secondary-color: #3498db;     /* Accents, categories */
--text-color: #333;             /* Body text */
--text-light: #666;             /* Meta info */
--border-color: #e1e4e8;        /* Borders */
--bg-color: #ffffff;            /* Background */
--bg-light: #f6f8fa;            /* Header/footer bg */
--code-bg: #f5f5f5;             /* Code blocks */
```

Change these values to customize your color scheme.

**Other customizations:**
- Fonts
- Layout spacing
- Typography
- Responsive breakpoints

### Modify Layouts

Edit files in `_layouts/`:
- `default.html`: Base template with navigation
- `post.html`: Individual post template

### Add Pages

Create new `.html` or `.md` files in the root directory with front matter:

```markdown
---
layout: default
title: About
---

Your content here...
```

Then add a link in `_layouts/default.html` navigation.

## 🔧 Troubleshooting

### Site not showing up after deployment

1. Check the **Actions** tab for workflow errors
2. Verify GitHub Pages is enabled with source set to **"GitHub Actions"**
3. Confirm `baseurl` in `_config.yml` matches your repository name
4. Wait a few minutes—initial deployment can take time

### Local site looks different from deployed site

- Ensure `_config.yml` has correct `url` and `baseurl` for GitHub Pages
- Check that asset paths use `{{ '/assets/...' | relative_url }}`

### Styles not loading

- Verify `baseurl` is `/today-i-learned` (with leading slash, no trailing slash)
- Clear browser cache
- Check browser console for 404 errors

### Posts not appearing

- Verify filename format: `YYYY-MM-DD-title.md`
- Check front matter has required fields: `layout`, `title`, `date`
- Ensure date isn't in the future
- Rebuild with `bundle exec jekyll serve --force_polling`

### Ruby/Bundler issues

```bash
# Update bundler
gem install bundler

# Clean and reinstall
rm -rf vendor/ .bundle/
bundle install

# Clear Jekyll cache
bundle exec jekyll clean
```

## 📚 Resources

- [Jekyll Documentation](https://jekyllrb.com/docs/)
- [GitHub Pages Documentation](https://docs.github.com/en/pages)
- [Markdown Guide](https://www.markdownguide.org/)
- [Liquid Template Language](https://shopify.github.io/liquid/)

## 🙏 Inspiration

This project is inspired by the [Today I Learned](https://github.com/jbranchaud/til) format popularized by Josh Branchaud and others in the developer community.
