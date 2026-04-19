# Prompt Library

A single-skill Claude Code repository that dispatches one of 13 predefined prompt templates from `references/prompts.md`.

The skill is designed for prompt retrieval, not prompt generation. When a user asks for a template by number, title, or natural-language intent, the skill matches the request, labels the match, and returns the original template body unchanged from `references/prompts.md`. When the user has already provided source material and asked for direct help, the skill should not distribute a template and should instead execute the task.

## What this repository contains

- `SKILL.md` — the runtime contract for triggering, matching, output format, and failure handling
- `references/prompts.md` — the single source of truth for all 13 prompt template bodies
- `examples/` — example user requests and expected behavior
- `.github/` — issue and pull request templates for open collaboration

## Behavior contract

This repository intentionally keeps the current skill behavior stable:

1. Read templates from `references/prompts.md`
2. Match by explicit number, title, or keywords
3. Return the matched template body unchanged, wrapped in the documented output format from `SKILL.md`
4. If the user already supplied materials and asked to do the work, do the work directly instead of outputting a template

## Included prompt categories

1. 深度技术图文/公众号大纲拆解与生成
2. 多源RSS资讯聚合与深度提炼
3. AI Agent/自动化工作流架构设计
4. 公众号文章总结（知识库深度脱水）
5. 项目资料提炼（技术开源与项目分析）
6. 视频号内容概括（文案逻辑与二创）
7. 视频教程详细SOP（保姆级复刻）
8. 爆款视频底层拆解（情绪与人设）
9. SRT字幕提取
10. 拍摄剪辑与视听语言分析
11. 代码需求说明书（Spec）生成
12. 研报与市场逻辑拆解
13. 爆款标题仿写生成器

## Installation

Place this repository where Claude Code can access it as a local skill repository.

Example local layout:

```text
prompt-library/
├── SKILL.md
├── references/
│   └── prompts.md
├── examples/
└── .github/
```

If you are maintaining a larger multi-skill repository later, you can move this package into a nested skill directory, but this public version intentionally keeps the current single-skill root layout unchanged.

## Usage

Typical requests:

- `有哪些提示词`
- `给我第 5 个提示词`
- `我想拆解一篇爆款文章`
- `帮我找项目资料提炼那个提示词`

Direct-task requests should bypass template distribution:

- `这是文章内容，帮我直接总结`
- `这是项目 README，直接帮我提炼重点`

## Matching rules

- **By number**: `第 3 个`, `给我第11个提示词`
- **By title**: exact or near-exact title references
- **By keywords**: natural-language intent such as `RSS 聚合`, `爆款标题`, `视频字幕`
- **Ambiguous match**: return the closest 2–3 options
- **No match**: return the full list of 13 titles

## Repository structure

```text
.
├── .github/
│   ├── ISSUE_TEMPLATE/
│   └── pull_request_template.md
├── examples/
├── references/
│   └── prompts.md
├── CHANGELOG.md
├── CONTRIBUTING.md
├── LICENSE
├── README.md
└── SKILL.md
```

## Contribution guidelines

Please read `CONTRIBUTING.md` before editing templates or the index.

The most important maintenance rule is to keep `SKILL.md` and `references/prompts.md` synchronized:

- prompt count must remain consistent
- numbering must stay continuous
- titles must match exactly
- template bodies must remain in `references/prompts.md` as the only source of truth

## License

MIT. See `LICENSE` for details.
