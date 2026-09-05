# mersious.github.io

Source of my personal site — <https://mersious.github.io>.

A single hand-written `index.html`: no framework, no build step, no external
requests except my GitHub avatar. Light and dark themes follow the visitor's
system setting, with a manual toggle stored in `localStorage`.

## Editing

Open `index.html` and edit it. That's the whole workflow.

Sections are marked with HTML comments (`<!-- ===== WORK ===== -->`) so they're
easy to find:

| Section    | What lives there                                  |
| ---------- | ------------------------------------------------- |
| Hero       | Name, one-line pitch, links, availability          |
| Focus      | The three things I'm building right now            |
| Work       | Project cards — add a new `<article class="card proj">` |
| Experience | Timeline entries                                   |
| Toolbox    | Skill rows                                         |
| Beyond     | Teaching, open education, degree                   |
| Contact    | Email and profiles                                 |

### Adding a project

Copy one card and change the text:

```html
<article class="card proj">
  <div class="top-row"><h3>Project name</h3><span class="status live">Deployed</span></div>
  <p>One paragraph: what it does, and the one number or detail that makes it real.</p>
  <div class="tags"><span class="tag">C++</span><span class="tag">ROS 2</span></div>
</article>
```

`status` values used so far: `In progress`, `Deployed`, `Shipped`, `Research`.
Add the class `live` to tint the badge with the accent colour.

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deployment

GitHub Pages serves the `main` branch from the repository root. Pushing to
`main` publishes the site.
