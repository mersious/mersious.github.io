# mersious.github.io

Source of my personal site: <https://mersious.github.io>.

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
| Now        | The three things I am building right now           |
| Specimens  | Project cards, `<article class="box">`             |
| Record     | Experience entries                                 |
| Skills     | Technical Skills, aligned mono rows                |
| Margin     | Teaching, open education, degree                   |
| Contact    | Email and profiles                                 |

### Adding a project

Copy one card and change the text:

```html
<article class="box">
  <div class="figtag"><h3>Project name</h3><span class="status live">Deployed</span></div>
  <p>One paragraph: what it does, and the one number or detail that makes it real.</p>
  <div class="tags"><span class="tag">C++</span><span class="tag">ROS 2</span></div>
</article>
```

Add `class="box wide"` to let a card span both columns.

## The colour system

Four roles, defined once as CSS variables at the top of `index.html`. Nothing on
the page uses a colour outside them, so a new section never has to invent a hue.

| Role | Light | Dark | Used for |
| ---- | ----- | ---- | -------- |
| `--paper` / `--ink` | `#f4f1ea` / `#1a1a1a` | `#14130f` / `#eae5d8` | The page and all prose |
| `--accent` (red) | `#c1440e` | `#e2673a` | The pen: figure numbers, marginalia, rules, links |
| `--ok` (green) | `#3c6e47` | `#7fb98a` | It exists and it works |
| `--wip` (amber) | `#9a6f14` | `#d2a03c` | Still moving |
| `--mark` (yellow) | highlighter wash | highlighter wash | One number per paragraph, no more |

Status badges pick their colour from that vocabulary, not from a per-card choice:

- `<span class="status ok">` for `Live`, `Deployed`, `Shipped`
- `<span class="status wip">` for `Prototype`, `In progress`
- `<span class="status">` with no modifier for anything neutral

## House style

**No em dashes.** Commas, colons, parentheses and periods only. This holds for
the page, this README, and commit messages.

## Layout

The measure is `--maxw` (1180px) with a `--gutter` (104px) holding the figure
number. Body text is 16px at 1.6 line-height. If you widen the measure, drop the
type size to match, or the lines get too long to track.

## Local preview

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Deployment

GitHub Pages serves the `main` branch from the repository root. Pushing to
`main` publishes the site.
