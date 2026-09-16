# Cielara documentation

The source for the Cielara product documentation, published with [Mintlify](https://mintlify.com).

## Layout

Pages are MDX files with YAML frontmatter, at the repository root.

| File | Purpose |
|---|---|
| `docs.json` | Navigation, theme, and site config. A page is not live until it is listed here |
| `AGENTS.md` | Terminology, style, and structure rules. Read this before writing |
| `.mintignore` | Files excluded from the published site |

The navigation has three groups: Getting Started, Product Features, and Setup & Configuration.

## Versions

`docs.json` declares a single version, `latest`, under `navigation.versions`. Its pages live at the repository root, so page URLs have no version prefix (`/models`, not `/latest/models`).

To cut a version when the product ships a release that needs its own docs:

1. Copy the current root pages into a folder named for the release being frozen, for example `v1/`.
2. Add a second entry to `navigation.versions` whose page paths point at that folder (`v1/models`, and so on).
3. Leave `latest` at the root and keep `"default": true` on it, so the current docs keep their URLs and stay the landing version.

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

## Writing

Read `AGENTS.md` first. The short version:

- One page per topic. Do not add a how-to guide that parallels a reference page
- Title Case headings, active voice, second person
- Document failure modes, not just the happy path
- Do not invent field names, error strings, or UI details you cannot verify

## Troubleshooting

- Dev server not starting: run `mint update` for the latest CLI
- Page 404s locally: check it is listed in `docs.json` and that you are running from the repository root
