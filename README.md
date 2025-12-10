# Today I Learned

A collection of concise write-ups on small things I learn day to day across a variety of languages and technologies. Built with Jekyll and hosted on GitHub Pages.

## 🚀 Setup Instructions

### Prerequisites

- Ruby 2.7 or higher
- Bundler (`gem install bundler`)

### Local Development

1. Clone this repository:
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

4. Visit `http://localhost:4000/today-i-learned` in your browser

### Publishing to GitHub Pages

Follow these steps to enable GitHub Pages for this repository:

1. **Push your code to GitHub** (if you haven't already):
   ```bash
   git add .
   git commit -m "Initial Jekyll site setup"
   git push origin main
   ```

2. **Enable GitHub Pages**:
   - Go to your repository on GitHub: https://github.com/doug-skinner/today-i-learned
   - Click on **Settings** (in the repository menu)
   - Click on **Pages** (in the left sidebar under "Code and automation")
   - Under **Build and deployment**:
     - Set **Source** to "GitHub Actions"
   - The GitHub Action will automatically build and deploy your site

3. **Wait for deployment**:
   - Go to the **Actions** tab in your repository
   - You'll see the "Deploy Jekyll site to Pages" workflow running
   - Once it completes (green checkmark), your site is live!

4. **Visit your site**:
   - Your site will be available at: `https://doug-skinner.github.io/today-i-learned/`

## 📝 Adding New TIL Posts

Create a new file in the `_posts` directory with the naming convention: `YYYY-MM-DD-title-with-hyphens.md`

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

### Example

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

## 📂 Repository Structure

```
today-i-learned/
├── _config.yml              # Jekyll configuration
├── _layouts/                # Layout templates
│   ├── default.html        # Base layout
│   └── post.html           # Post layout
├── _posts/                 # Your TIL entries (markdown files)
├── assets/
│   └── css/
│       └── main.css        # Site styles
├── .github/
│   └── workflows/
│       └── jekyll.yml      # GitHub Actions deployment workflow
├── index.html              # Homepage
├── categories.html         # Category browser
├── archive.html            # Full archive
├── Gemfile                 # Ruby dependencies
└── README.md               # This file
```

## 🎨 Customization

### Update Site Information

Edit `_config.yml` to change:
- Site title
- Description
- Your email
- URL and baseurl
- Timezone

### Modify Styles

Edit `assets/css/main.css` to customize:
- Colors (CSS variables in `:root`)
- Fonts
- Layout and spacing
- Responsive breakpoints

### Categories

Categories are automatically generated from your posts' front matter. Just add a `category:` field to any post and it will appear in the categories page.

## 🔧 Troubleshooting

### Site not showing up after deployment

1. Check the Actions tab to see if the workflow completed successfully
2. Make sure GitHub Pages is enabled with source set to "GitHub Actions"
3. Verify the `baseurl` in `_config.yml` matches your repository name

### Local site looks different from deployed site

Make sure your `_config.yml` has the correct `url` and `baseurl` settings for GitHub Pages.

### Styles not loading

Check that `baseurl` in `_config.yml` is set to `/today-i-learned` (with leading slash, no trailing slash).

## 📄 License

This project is open source and available under the MIT License.
