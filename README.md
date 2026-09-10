# ios-hig-design-guide-skill

依据官方设计规范与真实来源，梳理 iOS 界面的组件行为、交互、可访问性和设计要求。

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

## 配置、依赖与使用边界

Python 3 与访问 Apple 官方来源的网络能力；无需独立账号或 API Key。首次同步生成 references 缓存，安装目录须可写或先复制到任务目录。

仅引用实际下载成功的页面；失败时注明资料缺口，不把推断写成 Apple 强制要求。

使用示例：

```text
依据 Apple HIG 检查我的 iOS 设置页面。
```

也可把 [仓库地址](https://github.com/oil-oil/ios-hig-design-guide-skill) 发给 Agent，要求按 README 安装。
