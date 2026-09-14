# Cielara documentation

The source for the Cielara product documentation, published with [Mintlify](https://mintlify.com).

## Layout

Pages are MDX files with YAML frontmatter, at the repository root.

| File | Purpose |
|---|---|
| `docs.json` | Navigation, theme, and site config. A page is not live until it is listed here |
| `doc-sources.yaml` | Maps each page to the source paths it documents, for the staleness check |
| `AGENTS.md` | Terminology, style, and structure rules. Read this before writing |
| `.mintignore` | Files excluded from the published site |

The navigation has three groups: Getting Started, Product Features, and Setup & Configuration.

## Local preview

Install the Mintlify CLI:

```bash
npm i -g mint
```

Run it from the repository root, where `docs.json` lives:

```bash
mint dev
```

The preview is at `http://localhost:3000`.

## Publishing

Changes are deployed automatically when they land on the default branch, via the Mintlify GitHub app.

## Staleness check

`.github/workflows/doc-staleness.yml` runs every Monday. It checks out the source repositories listed in `doc-sources.yaml` and compares the last commit date on each mapped path against the last commit date of the page documenting it. A page whose source moved more recently is flagged as possibly stale, and the workflow opens an issue.

The check is only as good as the mapping. **When you add, merge, or delete a page, update `doc-sources.yaml` in the same change**, or the page silently stops being covered.

Trigger a run manually from the Actions tab.

## Writing

Read `AGENTS.md` first. The short version:

- One page per topic. Do not add a how-to guide that parallels a reference page
- Title Case headings, active voice, second person
- Document failure modes, not just the happy path
- Do not invent field names, error strings, or UI details you cannot verify

## Troubleshooting

- Dev server not starting: run `mint update` for the latest CLI
- Page 404s locally: check it is listed in `docs.json` and that you are running from the repository root
