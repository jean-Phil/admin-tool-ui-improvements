# payload-console

A rung-one styleguide workspace, founded 2026-11-16T14:05:00.000Z by ui-designer.

## The laws this workspace lives by [TWP-S-4]

- **styleguide.yaml is the manifest** — request, date, rung, derived-from
  citations, chosen tokens. It was written FIRST and the workspace amends
  around it: update == read the manifest + files → re-ground → amend,
  never rebuild.
- **journal.jsonl is append-only** — session opens, operator rulings
  (approvals and rejections), amendments, notes. Entries are births;
  nothing is rewritten or removed.
- **No JS, no config file** at rung one [S-045 (2), (3)]: `theme.source.css`
  is the token surface; the utilities it mints serve `index.html`.

## Building the committed stylesheet [S-045 (2)]

The committed `theme.css` is built dev-time by the CLI at the pinned
paths (house pin 4.3.3):

    bunx @tailwindcss/cli@4.3.3 -i theme.source.css -o theme.css --minify

Run it after touching `theme.source.css` or the classes in `index.html`;
the built sheet is committed beside its source, so the deployed surface links
a static file and never invokes the tool. Inside this house's engine the same
build is one dev line: `bun run build:theme -- <workspace-root>`.
