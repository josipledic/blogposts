# blogposts

## format

The blogposts are written in .mdx format and contain meta/frontmatter info in their header: `id`, `title`, `authorName`, `date`, `tags`, `excerpt`, and optionally `description`. When present, `description` is shown under the title and used as the meta description. The first tag is shown as the article's category.

The page renders the title as the only H1, so newer posts start with prose rather than a `# Title` line.

## infographics

Posts can use the figure components the josip.me site provides: `Stats`/`Stat`, `Bars`, `Flow`/`Step`, `Timeline`/`Phase`, `Callout`, `Calc`, `Split`, `Matrix` and `Checklist`, plus GFM tables. They are documented in the site repository's README. A post that uses a component the deployed site does not have yet fails to render, so deploy the site first.

In MDX, avoid a bare `<` or `{` in prose (write "under 5", not "<5") and keep a `Step` or `Phase` body on a single line.

## localized posts

English posts live in the repository root and are served at `/posts/<filename>`. German posts live under `de/` with a German filename, which is also their URL: `de/ki-telefonassistent-zahnarztpraxis.mdx` is served at `/de/posts/ki-telefonassistent-zahnarztpraxis`. Use lowercase German keywords with umlauts written out (`ae`, `oe`, `ue`, `ss`).

A German post names its English original in the frontmatter:

```
id: "ki-telefonassistent-zahnarztpraxis"
translationOf: "ai-for-dentists"
```

`translationOf` is the English filename without `.mdx`. The site uses it for the language switch and the `hreflang` links between the two versions, and it redirects the old `/de/posts/<english-filename>` address to the German one. A German post without `translationOf` is paired with an English post of the same filename, if there is one.

Links between German posts use the German filenames (`/de/posts/<german-filename>`), and the call to action links to the German contact page, `/de/kontakt`.

German posts are written for German-speaking readers rather than translated line by line, so their sources and examples can differ.

## deployment

You have to retrigger the same build on Vercel for the website to pick up the latest blogpost files from here. To preview drafts locally, run the site with `BLOGPOSTS_DIR` pointing at this checkout.
