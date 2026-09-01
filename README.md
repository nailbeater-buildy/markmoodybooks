# markmoodybooks.com

The website for author Rev. Mark L. Moody. Plain HTML and CSS, no build step,
hosted on GitHub Pages.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site (one page, anchor-linked sections) |
| `styles.css` | All styling. Every colour and size lives in `:root` at the top. |
| `assets/` | Book covers and photos (JPEG) |
| `CNAME` | Tells GitHub Pages the custom domain |

Edit `index.html` / `styles.css`, commit, push. The live site updates within a
minute or two.

## Hosting: GitHub Pages

1. Repo **Settings -> Pages**.
2. **Source:** "Deploy from a branch", branch `main`, folder `/ (root)`.
3. **Custom domain:** `markmoodybooks.com` (the `CNAME` file sets this too).
4. Tick **Enforce HTTPS** once the certificate is issued (can take a few minutes).

## DNS (Namecheap)

On the domain's **Advanced DNS** tab:

| Type | Host | Value |
| --- | --- | --- |
| A | `@` | `185.199.108.153` |
| A | `@` | `185.199.109.153` |
| A | `@` | `185.199.110.153` |
| A | `@` | `185.199.111.153` |
| CNAME | `www` | `<username>.github.io.` |

Remove any old Carrd / parking records for `@` and `www` first. DNS changes can
take up to a few hours to propagate.

## Contact form: Formspree

The form in `index.html` posts to Formspree (GitHub Pages has no backend). It is
wired to endpoint `https://formspree.io/f/xwlkokga`. On first real submission
Formspree emails a one-time confirmation link to the form owner; click it to
activate. To change the destination address or add spam filtering, log in at
<https://formspree.io>.

## Adding a new book

Each book is one `<article class="book">` block inside `<section id="books">` in
`index.html`. It has two parts: a `<div class="cover">` with the cover image and
a `<div class="book-body">` with the label, title, subtitle, blurb, and links.

1. Save the cover art into `assets/` (e.g. `assets/new-book-title.jpg`).
2. Books run newest first. Copy an existing `<article class="book">` block and
   paste it at the **top** of the list (just under the `<!-- Books run newest
   first -->` comment).
3. Update the image `src`, the label, title, subtitle, blurb, and the two Amazon
   links. Delete the `.book-note` / `.book-fine` lines if the new book has none.

Keep the link pattern: `btn btn-solid` for the primary buy link, plain `btn` for
the secondary one, `btn-quiet` for a soft tertiary link.
