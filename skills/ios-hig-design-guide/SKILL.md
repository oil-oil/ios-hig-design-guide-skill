---
name: ios-hig-design-guide
description: "从 Apple Human Interface Guidelines 官方来源提炼 iOS UI/UX、组件行为、可访问性、交互和功能级设计规范。用户需要有 HIG 依据的 iOS 设计或评审时使用。不用于 Android、普通网页、无界面后端或与 iOS 设计规范无关的 Swift 代码修改。"
---

# iOS HIG Design Guide

Use this skill to produce iOS design recommendations that stay close to official Apple guidance.

## Quick start

1. Sync official sources.
2. Read only relevant sections.
3. Produce a feature-specific spec (not a generic style dump).

Run:

```bash
python3 "<当前 Skill 绝对目录>/scripts/sync_apple_hig_sources.py" --skill-dir "<当前 Skill 绝对目录>"
```

首次同步会生成下列 raw、fulltext、curated 与 catalog 文件，它们不是随包必带资源。文件缺失时先同步，失败则列出缺失项，不宣称已读取。脚本当前会写 Skill 的 references 目录，因此安装目录需要可写；只读安装需复制到任务目录再同步。

## Source of truth

- Full raw index with links and abstracts: `references/apple-hig-ios-raw.md`
- Consolidated text dump of all downloaded pages: `references/apple-hig-ios-fulltext.md`
- Curated text dump for iOS spec writing: `references/apple-hig-ios-curated.md`
- Workflow for selecting relevant HIG pages: `references/ios-design-spec-workflow.md`
- Per-page JSON sources: `references/raw/pages/design/human-interface-guidelines/*.json`
- Crawl metadata and fetch status: `references/raw/catalog.json`

## Workflow

### 1) Sync and verify

- Run sync script before answering "latest" or "current" requests.
- Confirm `download_error` is 0 in `references/raw/catalog.json`.
- If errors exist, report failed paths and continue with successfully downloaded pages.

### 2) Narrow scope

- Start from `/design/human-interface-guidelines/designing-for-ios`.
- Add only sections directly related to the requested feature.
- Prioritize foundational constraints (accessibility, layout, typography, color, writing, privacy).
- Prefer `references/apple-hig-ios-curated.md` for day-to-day use; use full dump only when needed.

### 3) Extract constraints

For each selected page, pull concrete rules into implementable statements:

- When to use component/pattern
- Required states (loading, empty, error, destructive confirmation)
- Accessibility behavior (labels, hints, touch target, dynamic type)
- Localization/layout behavior (RTL, truncation, multiline)
- Platform-specific caveats (iOS-only vs cross-platform)

### 4) Produce deliverable

Default output structure:

1. Feature goal and user scenario
2. Information architecture and screen inventory
3. Interaction and state model
4. Component specification
5. Accessibility and localization checklist
6. Open questions and tradeoffs

## Output style rules

- Cite source page paths for each major rule.
- Translate HIG guidance into actionable product decisions.
- Avoid copying large raw passages.
- Mark inferred recommendations explicitly as inference.

## Maintenance

- Re-run sync script whenever Apple updates HIG content.
- Keep generated raw files in `references/`; do not hand-edit generated outputs.
- Update this SKILL.md only for workflow or quality improvements.
