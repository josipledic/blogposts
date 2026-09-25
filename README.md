# blogposts

## format

The blogposts are written in .mdx format and contain meta/frontmatter info in their header: `id`, `title`, `authorName`, `date`, `tags`, `excerpt`, and optionally `description`. When present, `description` is shown under the title and used as the meta description. The first tag is shown as the article's category.

The page renders the title as the only H1, so newer posts start with prose rather than a `# Title` line.

## infographics

Posts can use the figure components the josip.me site provides: `Stats`/`Stat`, `Bars`, `Flow`/`Step`, `Timeline`/`Phase`, `Callout`, `Calc`, `Split`, `Matrix` and `Checklist`, plus GFM tables. They are documented in the site repository's README. A post that uses a component the deployed site does not have yet fails to render, so deploy the site first.

In MDX, avoid a bare `<` or `{` in prose (write "under 5", not "<5") and keep a `Step` or `Phase` body on a single line.

## localized posts

English posts live in the repository root. German versions use the same filename under `de/` and are served at `/de/posts/<slug>`, with `hreflang` links between the two. German posts are written for German-speaking readers rather than translated line by line, so their sources and examples can differ.

## deployment

You have to retrigger the same build on Vercel for the website to pick up the latest blogpost files from here. To preview drafts locally, run the site with `BLOGPOSTS_DIR` pointing at this checkout.
