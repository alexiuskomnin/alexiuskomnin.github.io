# alexiuskomnin.github.io

Personal site & blog of Oleksii Yuvchenko — live at <https://alexiuskomnin.github.io/>.

Built with [Hugo](https://gohugo.io/) and the [PaperMod](https://github.com/adityatelange/hugo-PaperMod) theme. Deployed automatically to GitHub Pages via GitHub Actions on every push to `master`.

## Local development

Requires Hugo extended (`brew install hugo`).

```bash
git clone --recurse-submodules https://github.com/alexiuskomnin/alexiuskomnin.github.io.git
cd alexiuskomnin.github.io
hugo server -D
```

Then open <http://localhost:1313/>. The `-D` flag includes drafts.

## Writing a post

```bash
hugo new content posts/my-post/index.md
```

Each post is a folder (a Hugo "page bundle"); drop images alongside `index.md` and reference them as `![alt](filename.png)`. Set `draft: false` in the front matter when you're ready to publish.

## License

Content (posts, prose, images) © Oleksii Yuvchenko, all rights reserved.
Site source code is available under the MIT License.
