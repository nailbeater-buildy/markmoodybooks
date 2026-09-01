# markmoodybooks.com

The website for author Rev. Mark L. Moody. Plain HTML and CSS, no build step,
hosted on GitHub Pages.

## Files

| File | What it is |
| --- | --- |
| `index.html` | The whole site (one page, anchor-linked sections) |
| `styles.css` | All styling |
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

Each book is one `<article class="book">` block in `index.html`. Copy the last
one, update the label, title, description, and Amazon link(s), paste it below
the others. Nothing else needs to change.
