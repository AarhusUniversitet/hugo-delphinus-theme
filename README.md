# Hugo Delphinus Theme

A Hugo theme based on Aarhus University's [Delphinus Design System](https://delphinus.au.dk/).

## Features

- Responsive layout with sidebar navigation
- Hierarchical documentation structure with collapsible sections
- Blog/posts section
- Client-side search via [Pagefind](https://pagefind.app/)
- Delphinus Design System CSS/JS loaded from CDN
- Accessible markup with skip-to-content and ARIA labels

## Installation

### As a Git Submodule

```bash
cd your-hugo-site
git submodule add https://github.com/AarhusUniversitet/hugo-delphinus-theme.git themes/delphinus
```

Then set in your `hugo.toml`:

```toml
theme = 'delphinus'
```

### Manual

Download or clone this repo into your site's `themes/delphinus` directory.

## Configuration

Add these parameters to your `hugo.toml`:

```toml
[params]
  description = "Your site description"
  footerSubtitle = "Documentation"
  organization = "Aarhus University"
```

| Parameter | Description |
|-----------|-------------|
| `description` | Shown in the footer and in the HTML meta description |
| `footerSubtitle` | Text displayed next to the site title in the footer |
| `organization` | Organization name shown in the footer |

## Content Structure

The theme expects the following content structure:

```
content/
├── documentation/       # Main docs (rendered in sidebar navigation)
│   ├── _index.md
│   ├── section-1/
│   │   ├── _index.md
│   │   └── page.md
│   └── section-2/
│       ├── _index.md
│       └── page.md
├── posts/               # Blog posts
│   ├── _index.md
│   └── my-post.md
└── search.md            # Search page (layout: single)
```

## Shortcodes

### Button
```markdown
{{</* button url="/link" text="Click here" */>}}
{{</* button url="/link" text="Secondary" type="dimmed" */>}}
```

### Callout
```markdown
{{</* callout type="info" */>}}Info message{{</* /callout */>}}
{{</* callout type="warning" */>}}Warning{{</* /callout */>}}
{{</* callout type="error" */>}}Error{{</* /callout */>}}
{{</* callout type="success" */>}}Success{{</* /callout */>}}
```

## Search (Pagefind)

After building your Hugo site, run Pagefind to index the content:

```bash
hugo --minify
npx pagefind --site public
```

## Requirements

- Hugo >= 0.112.0

## License

MIT — see [LICENSE](LICENSE).
