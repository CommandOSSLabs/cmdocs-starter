# My Documentation

Documentation site powered by [cmdocs](https://github.com/CommandOSSLabs/cmdocs).

## Getting Started

Start the development server:

```bash
npx cmdocs dev
```

Open [http://localhost:3000](http://localhost:3000) to view your docs.

## Project Structure

```
.
├── docs.json                # Site configuration (theme, navigation, navbar)
├── index.mdx                # Home page
├── quickstart.mdx           # Quickstart guide
├── guides/
│   ├── writing-content.mdx  # MDX authoring guide
│   └── components.mdx       # UI component reference
└── public/
    ├── favicon.svg
    ├── logo-light.svg       # Navbar logo (light mode)
    └── logo-dark.svg        # Navbar logo (dark mode)
```

## Key Files

- **`docs.json`** — Central configuration for your site: name, theme colors, navigation structure, navbar logo, footer, and SEO settings.
- **MDX files** — Documentation pages written in [MDX](https://mdxjs.com/) (Markdown + JSX components). All [Fumadocs UI](https://fumadocs.dev) components are auto-imported.
- **`public/`** — Static assets served at the root URL. Place images, logos, and favicons here.

## Common Tasks

### Add a new page

1. Create a `.mdx` file with frontmatter:

   ```mdx
   ---
   title: My New Page
   description: A brief description.
   ---

   # My New Page

   Content goes here.
   ```

2. Add the page slug to `docs.json` under the appropriate group:

   ```json
   {
     "group": "Guides",
     "pages": ["guides/writing-content", "guides/components", "guides/my-new-page"]
   }
   ```

### Customize the theme

Edit the `theme` section in `docs.json`:

```json
{
  "theme": {
    "colors": { "primary": "#2563EB" },
    "darkMode": true
  }
}
```

### Configure the navbar logo

The `navbar.logo` field supports three display modes:

```json
// Brand name only (no logo field)
{ "navbar": { "title": "My Docs" } }

// Square icon + brand name
{ "navbar": { "title": "My Docs", "logo": "/icon.svg" } }

// Logo with text baked in (no separate title)
{
  "navbar": {
    "logo": {
      "light": "/logo-light.svg",
      "dark": "/logo-dark.svg",
      "display": "logo-only",
      "width": 120,
      "height": 30
    }
  }
}
```

## Build for Production

```bash
npx cmdocs build
```

## Learn More

- [cmdocs Documentation](https://docs.cmdocs.dev)
- [Fumadocs Components](https://fumadocs.dev/docs/ui/components)
- [GitHub Repository](https://github.com/CommandOSSLabs/cmdocs)
