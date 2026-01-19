# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Commands

```bash
npm run dev       # Start dev server at localhost:4321
npm run build     # Type-check with astro check, then build to ./dist/
npm run preview   # Preview production build locally
```

## Architecture

This is a personal blog built with Astro 4 and Tailwind CSS.

### Content System
- Blog posts live in `src/content/blog/` as Markdown files
- Content schema defined in `src/content/config.ts` with frontmatter: `title`, `date`, `excerpt`, and optional `artImage`
- Dynamic routes at `/blog/[slug]` generated via `getStaticPaths()` in `src/pages/blog/[...slug].astro`

### Layout Structure
- `Layout.astro`: Base HTML wrapper with Header, Footer, and PostHog analytics
- `BlogPost.astro`: Blog-specific layout extending Layout, handles post rendering and social share buttons

### Key Integrations
- `@astrojs/tailwind` for styling
- `astro-social-share` for social sharing buttons on posts
- PostHog for analytics (configured in `src/components/posthog.astro`)
- Poppins font as the default sans-serif
