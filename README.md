# ios-hig-design-guide-skill

Open-source agent skill for iOS design specifications based on Apple Human Interface Guidelines (HIG).

## Install

```bash
npx skills add oil-oil/ios-hig-design-guide-skill --skill ios-hig-design-guide
```

Or install directly from path:

```bash
npx skills add https://github.com/oil-oil/ios-hig-design-guide-skill/tree/main/skills/ios-hig-design-guide
```

## What this skill does

- Fetches latest Apple HIG source JSON from official endpoints
- Builds a raw index, full-text dump, and curated iOS-oriented text
- Produces feature-level iOS UI/UX specs with source-path traceability

## Update Apple sources

After installation, run in the skill directory:

```bash
python3 scripts/sync_apple_hig_sources.py --skill-dir .
```

This generates:

- `references/raw/catalog.json`
- `references/apple-hig-ios-raw.md`
- `references/apple-hig-ios-fulltext.md`
- `references/apple-hig-ios-curated.md`

## License

MIT
