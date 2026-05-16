# Skills Hub Design Spec

## Overview

一个 AI Agent 技能收藏夹，用纯 Markdown（README.md）实现，零部署、零依赖。按四大分类组织 skill 链接，支持搜索（浏览器 Ctrl+F）、快速新增（加一行表格）。

## 目标

- 快速定位需要的 skill，不用翻遍所有已安装的 skills
- 新增 skill 成本最低：加一行表格行
- GitHub 原生渲染，无需部署

## 分类体系

| 分类 | key | 示例 |
|------|-----|------|
| 研发 | dev | frontend-design, react-best-practices, composition-patterns |
| 设计 | design | figma-use, ui-ux-pro-max, design-shotgun |
| 测试 | test | qa, playwright, benchmark, canary |
| 提效 | efficiency | brainstorming, ship, git-commit, investigate |

## 文件结构

```
skills-hub/
├── README.md              # 主目录（总览 + 推荐 + 四分类表格）
└── docs/
    └── superpowers/
        └── specs/
            └── 2026-05-16-skills-hub-design.md  # 本文档
```

## README.md 结构

1. **标题 + 一句话描述**
2. **推荐区**：精选 5-8 个高频 skill，表格展示
3. **四个分类区**：每个分类一个二级标题 + 表格
4. **折叠扩展**：每个分类用 `<details>` 包裹超出 8 条的部分

### 表格列定义

| 列 | 说明 |
|----|------|
| Skill | 名称，链接到 skill 源文件或文档 |
| 简介 | 一句话说明用途 |
| 标签 | 逗号分隔的技术标签 |

### 新增 skill 流程

1. 确定分类（研发/设计/测试/提效）
2. 在对应分类表格中加一行：`| [name](url) | 简介 | 标签 |`
3. 如果分类超过 8 条，把多余的移到 `<details>` 折叠块中

## 扩展策略

- **Phase 1（当前）**：单 README.md，用 `<details>` 折叠控制长度
- **Phase 2（未来）**：如果单文件过长，按分类拆分为 `dev.md`、`design.md`、`test.md`、`efficiency.md`，README 保留总览 + 各分类 top 5 + 详情链接

## 非目标

- 不做部署、不做静态站点
- 不做搜索功能（依赖浏览器 Ctrl+F）
- 不做统计、评分等复杂功能
