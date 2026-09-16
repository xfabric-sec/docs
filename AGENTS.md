# Documentation project instructions

## About this project

- The Cielara product documentation, built on [Mintlify](https://mintlify.com)
- Pages are MDX files with YAML frontmatter
- Navigation and theming live in `docs.json`. A page is not live until it is listed there
- Use the Mintlify MCP server, `https://mcp.mintlify.com`, to edit content and settings via MCP
- Use the Mintlify docs MCP server, `https://www.mintlify.com/docs/mcp`, to query information about using Mintlify via MCP

## Terminology

- **Cielara**: the product. Not "the platform" or "the tool"
- **Foresight**: the code review engine that reviews pull requests. Reviews are "Foresight reviews", not "Cielara reviews"
- **World Model**: the topology graph. Capitalised, never "world map" or "the graph" on first use
- **Ask Cielara**: the AI assistant. Capitalised in full, never "the chatbot"
- **Antifragility score**: the 0 to 100 quality metric, broken into six **pillars** (Security, Reliability, Performance, Operability, Maintainability, Cost)
- **Findings**: what a review produces. Not "issues", "problems", or "errors"
- **Connections**: integrations with external systems. Not "integrations" or "plugins" in prose
- **Workloads**: services in the topology. Not "apps" or "microservices" unless quoting the UI
- Use **admin** and **user** for the two roles, matching the role chips in the UI

## Style preferences

- Use active voice and second person ("you")
- Keep sentences concise. One idea per sentence
- Use Title Case for headings. Some pages still use sentence case; fix them when you touch them, don't add more
- Bold for UI elements: Click **Settings**
- Code formatting for file names, commands, paths, and code references
- No em-dashes. Use a full stop, a comma, or parentheses
- Document failure modes, not just the happy path. `authentication.mdx` is the model. Show what breaks, what the error says, and what to check first
- Prefer explaining what a feature is for over narrating where its panels sit. Layout prose goes stale the moment the UI moves

## Structure

- **One page per topic.** Do not create a how-to guide that parallels a reference page; the two drift and readers cannot tell which is current. Task steps belong on the page that documents the feature
- A separate page is only justified when it covers genuinely different material, not the same material at a different depth
- When adding, merging, or deleting a page, update `docs.json` in the same change
- The site is versioned. `docs.json` declares one version, `latest`, whose pages sit at the repository root. Add new pages to that version. Do not create a version folder without being asked; see `README.md` for how a version is cut

## Content boundaries

- Do not document feature-flagged or internal-only features that customers cannot reach
- Do not invent UI details, field names, or error strings. If you cannot verify something from source or the running product, leave it out and flag it
- Do not include credentials, internal hostnames, or customer names in examples. Use `example.com` and `acme-inc`
