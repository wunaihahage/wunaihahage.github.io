# 我的电子书库

单文件静态站点，部署在 [GitHub Pages](https://pages.github.com/)，免费 24h 常驻。
仓库：`wunaihahage.github.io`（公共）

## 线上地址

| 页面 | 地址 | 文件 |
|------|------|------|
| 书库首页（导航页） | https://wunaihahage.github.io/ | `index.html` |
| 高性价比人生指南 | https://wunaihahage.github.io/how-to-live-better.html | `how-to-live-better.html` |
| 以日为鉴 · 衰退时代生存指南 | https://wunaihahage.github.io/yi-ri-wei-jian.html | `yi-ri-wei-jian.html` |

打开首页即可看到两张书卡，点击直接跳到对应书。

## 文件结构

```
wunaihahage.github.io/
├── index.html                 导航页（书库首页，根域 / 直接打开）
├── how-to-live-better.html    书①《高性价比人生指南》（608 条建议，可搜索）
├── yi-ri-wei-jian.html        书②《以日为鉴》（15 章长文，可搜索）
├── README.md                  本文件（源码页才看，不上 Pages 渲染）
└── .github/
    └── workflows/
        └── ql-cron.yml        （可选）青龙定时任务框架，与书库无关
```

## 怎么改导航链接

导航页 `index.html` 里两张书卡各是一个 `<a class="card" href="…">`，第 73、80 行：

```html
<a class="card" href="how-to-live-better.html">   <!-- 书① 入口 -->
<a class="card" href="yi-ri-wei-jian.html">       <!-- 书② 入口 -->
```

改法：
- **改跳转目标**：把 `href` 里的文件名改成你实际的书文件路径（相对路径，**不要**加开头的 `/`）。
- **改卡片上的文字**：同一张卡里的 `<h2>` 是书名、`<p class="sub">` 是简介、`.chip` 是标签、`进入阅读 →` 是按钮文字，直接改。
- **加第三本书**：复制一张 `<a class="card" …>…</a>` 整块，把 `href`、`<h2>`、`<p>` 换成新书即可；多一张会自动排到网格下一格。
- 改完 Commit 推上去，Pages 自动重建，线上即生效。

## 怎么删 / 增文件

- 仓库网页里点文件右侧垃圾桶 🗑️ → Commit 即删除（线上随之消失）。
- 新增：Add file → Create new file / Upload files。
- 注意：根域 `wunaihahage.github.io/` **只认 `index.html`**；删掉它首页会 404，但 `*.html` 文件仍可被完整文件名直接访问。

## 换成自定义域名（可选）

默认用 `wunaihahage.github.io`。想用自己的域名：
仓库 **Settings → Pages → Custom domain** 填你的域名，并把该域名 CNAME 指向 `wunaihahage.github.io`（或仓库名），保存后 GitHub 自动签 SSL。

## 注意事项

- 三个页面都是**纯静态单文件**：人生指南靠 Google Fonts（CDN，需联网，离线自动降级字体）；以日为鉴完全离线可开。
- `how-to-live-better.html` 的分享卡片（og）还指原作者 `eternity4719.github.io`；想让卡片也指到自己站，把该文件全文的 `eternity4719.github.io` 替换为 `wunaihahage.github.io`。
- 《以日为鉴》原文版权归作者所有，**仅供个人阅读**；若要对公众开放，请先取得授权。

## 本地快速预览

直接双击任一 `.html` 用浏览器打开即可（单文件，无需服务器）。导航页 `index.html` 相对链接指向同目录，本地打开也能正常跳转。
