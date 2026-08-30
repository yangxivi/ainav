# XIVIAI 免费资源导航站

> 自动同步「免费AI资源日报」，按到期紧迫度分类展示的单页导航站。

## 在线地址

https://www.ixivi.cn

## 特性

- **自动更新**：每日由「免费AI资源日报」自动化任务识别并整理最新资源，写入 `data.json` 后推送到本仓库；站点**实时从 GitHub 仓库读取** `data.json`（jsDelivr 兜底），因此只需把 Cloudflare Pages 项目连成 Git 集成（或部署一次），之后每天推送即自动生效，无需每次重新部署。
- **到期紧迫度分类**：
  - 本周到期（≤7天）
  - 本月到期（≤30天）
  - 本年到期
  - 限时免费
  - 长期免费
- **栅格卡片**：每个分类 4×4 排列，超出 16 个可折叠展开。
- **响应式布局**：适配电脑、平板、手机。
- **动态背景**：内联 SVG 动态背景，无圆角杂志栅格风格。

## 文件说明

| 文件 | 说明 |
|------|------|
| `index.html` | 站点入口，优先从 GitHub 仓库实时拉取 `data.json`（jsDelivr 兜底、本地同源兜底）后渲染 |
| `data.json` | 资源数据，由自动化每日更新 |
| `ai-resources-daily.html` | 开发版备份 |
| `bg.svg` | 动态背景 |
| `favicon.ico` / `logo.jpg` | 站点图标与 Logo |

## 数据字段

```json
{
  "nm": "资源名称",
  "pf": "平台名称",
  "tp": "标签",
  "ic": "图标URL",
  "end": "YYYY-MM-DD | FREE | LIMIT",
  "ds": "简介",
  "get": "领取方式"
}
```

## 自动化

- 自动化任务：免费AI资源日报
- 运行时间：每天 09:00
- 流程：识别资源 → 生成 `data.json` → 推送到本仓库 → 站点实时读取（建议 Cloudflare Pages 项目连成 Git 集成，推送即自动部署）

## 技术栈

- 单文件 HTML + 原生 CSS/JS
- Cloudflare Pages 托管（站点实时读取 GitHub 仓库 `data.json`，无需每次重新部署）
- 无构建步骤

---

由曦微（XIVI）维护
