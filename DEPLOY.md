# 部署"我的电子书库"到 GitHub Pages（免费 24h 常驻）

仓库：`https://github.com/wunaihahage/wunaihahage.github.io`（已建好，公共）

## 要推上去的 3 个文件（一次性拖完）

| 本地文件 | 线上地址 | 说明 |
|---------|---------|------|
| `index.html` | `https://wunaihahage.github.io/` | 导航页（书库首页） |
| `how-to-live-better.html` | `https://wunaihahage.github.io/how-to-live-better.html` | 《高性价比人生指南》 |
| `yi-ri-wei-jian.html` | `https://wunaihahage.github.io/yi-ri-wei-jian.html` | 《以日为鉴 · 衰退时代生存指南》 |

## 部署步骤（Web 端拖文件，30 秒）

1. 打开仓库页：https://github.com/wunaihahage/wunaihahage.github.io
2. 点 **Add file → Upload files**，把上面 3 个文件**一起**拖进虚线框
3. 写个 commit 说明（比如 `init 书库`）→ **Commit changes**
4. 等 1~2 分钟，Pages 自动构建
5. 浏览器开 `https://wunaihahage.github.io/`，看到书库首页即成功

## 验证

- 首页：「我的电子书库」，两张书卡
- 点「高性价比人生指南」→ 跳到 `how-to-live-better.html`，显示 608 条建议
- 点「以日为鉴」→ 跳到 `yi-ri-wei-jian.html`，显示 15 章长文

## 已知限制

| 限制 | 值 | 你这次 |
|------|-----|-------|
| 仓库大小 | 1 GB | 总 1.8 MB，远未到 |
| 单文件 | 100 MB | 最大 `yi-ri-wei-jian.html` 649 KB |
| 带宽 | 100 GB/月（软限） | 个人阅读碰不到 |
| 自定义域名 | 支持，免费 SSL | 暂用默认 `wunaihahage.github.io` |

## 后续维护

- 改哪本书：网页直接编辑对应 `.html`，Commit 即生效
- 或 Git 客户端：`git add *.html && git commit -m "update" && git push`

## 版权提示

- `how-to-live-better.html` 来自原作者 `eternity4719`，保留原站 og 域名；若你要把分享卡片也指到自己站，把全文 `eternity4719.github.io` 替换成 `wunaihahage.github.io` 即可
- `yi-ri-wei-jian.html` 原文（分析师 Boden，2025 年春）版权归作者，**仅供个人阅读**，不要公开发布到公共仓库；如果要公开发布，需先获得授权

## 关于之前搭的 `ql-cron.yml`

`.github/workflows/ql-cron.yml` 和 `scripts/` 是这个仓库早前搭的青龙 cron 框架，**跟书库部署互不干扰**。可以一起推（公共仓库 Actions 免费无限），也可以先只推 3 个 html，cron 那套后面再决定。

