# 我的电子书库

单文件静态站点，部署在 [GitHub Pages](https://pages.github.com/)，免费 24 小时常驻。
仓库：`wunaihahage.github.io`（公共）

## 线上地址

| 页面 | 地址 | 文件 |
|------|------|------|
| 书库首页（导航页） | https://wunaihahage.github.io/ | `index.html` |
| 高性价比人生指南 | https://wunaihahage.github.io/how-to-live-better.html | `how-to-live-better.html` |
| 以日为鉴 · 衰退时代生存指南 | https://wunaihahage.github.io/yi-ri-wei-jian.html | `yi-ri-wei-jian.html` |
| 价值 · 张磊 | https://wunaihahage.github.io/value.html | `value.html` |
| 国家为什么会失败 | https://wunaihahage.github.io/why-states-fail.html | `why-states-fail.html` |

打开首页能看到四张书卡，点卡片进对应书；每本书顶栏最右侧有「返回书库」按钮。

## 文件结构

```
wunaihahage.github.io/
├── index.html                 导航页（书库首页，根域 / 直接打开）
├── how-to-live-better.html    书① 高性价比人生指南（608 条建议，条目级筛选与搜索）
├── yi-ri-wei-jian.html        书② 以日为鉴（5 篇 15 章，三级目录 + 全文搜索）
├── value.html                 书③ 价值 · 张磊（374 页，按页跳转 + 全文搜索）
├── why-states-fail.html       书④ 国家为什么会失败（776 页，按页跳转 + 全文搜索）
├── README.md                  本文件（只在 GitHub 源码页显示，不影响线上站点）
└── .github/workflows/ql-cron.yml   （可选）青龙定时任务框架，与书库无关
```

## 五个页面共用的功能

- **背景配色（只换底色，文字始终是黑色）**：右下角悬浮面板，8 个色点 = 8 种底色
  （靛蓝 / 青绿 / 琥珀 / 玫红 / 青碧 / 紫罗兰 / 石墨 / 米纸）。点圆点**只换页面底色**，
  正文、标题、侧栏文字都保持黑色，链接仍是原来的蓝色 —— 换色只是为了看着舒服，不改可读性。
- **明暗（深色模式）**：面板上那个圆形月亮按钮单独切换深色底 / 浅色底，和选哪个颜色互不干扰。
  深色底上文字自动转浅色（深底浅字才看得清），这是唯一会变字色的情形。
  点任意一个色点会**自动回到浅色**，保证你点下去就能看到那个颜色本身。
- **不跟随系统深色**：页面不会因为你电脑是深色主题就自己变暗。开局一律浅色，只有你亲手点月亮才会变深。
- **可收缩**：面板右下角的箭头按钮把整块面板收成右下角一个小圆钮，点圆钮再展开；收/展状态会记住。
- **整站同步**：选中的底色与明暗存在浏览器本地，首页切换后进入任意一本书仍是同一套，刷新也不丢。
- **离线可用**：单文件，双击就能在浏览器打开，无需服务器；联网时只有字体走 CDN。

## 怎么改导航链接

导航页 `index.html` 里每本书是一张书卡，形如 `<a class="card" href="…">`：

```html
<a class="card" href="how-to-live-better.html">   <!-- 书① 入口 -->
```

改法：
- **改跳转目标**：改 `href` 里的文件名（相对路径，**不要**加开头的 `/`，Pages 上带斜杠的绝对路径会 404）。
- **改卡片文字**：同一张卡里 `<h2>` 是书名、`<p class="sub">` 是简介、`.chip` 是标签、`进入阅读 →` 是按钮文字，直接改。
- **加第五本书**：整块复制一张 `<a class="card">…</a>`，把 `href`、`<h2>`、`<p>`、`.chip` 换成新书即可，多一张会自动排到网格下一格。
- 改完 Commit 推上去，Pages 自动重建，线上即生效。

书卡封面配色由 `.cover.v1` ~ `.cover.v4` 控制，加新书时再补一条 `.cover.v5{…}` 即可。

## 怎么改「返回书库」按钮

每本书顶栏右侧那个箭头按钮就是返回入口：

```html
<a class="icon-btn" href="index.html" title="返回书库" aria-label="返回书库">…</a>
```

改 `href` 就改返回目标。`index.html`（首页自己）不需要这个按钮。

## 怎么删 / 增文件

- 仓库网页里点文件右侧垃圾桶，Commit 即删除（线上随之消失）。
- 新增：Add file → Create new file / Upload files。
- 注意：根域 `wunaihahage.github.io/` **只认 `index.html`**；删掉它首页会 404，但 `*.html` 仍可按完整文件名访问。

## 换成自定义域名（可选）

仓库 **Settings → Pages → Custom domain** 填域名，并把该域名 CNAME 指向 `wunaihahage.github.io`；保存后 GitHub 自动签发 SSL。

## 注意事项

- 五个页面都是**纯静态单文件**，无后端、无数据库。人生指南联网时字体走 Google Fonts，离线自动降级到系统字体。
- `how-to-live-better.html` 是原作者的离线单文件版，页面里的分享卡片（og:url / twitter:image）仍指向作者站点 `eternity4719.github.io`；纯自用无影响，若想让分享卡片指到自己站，把该文件全文的 `eternity4719.github.io` 替换为 `wunaihahage.github.io`。
- 《以日为鉴》《价值》《国家为什么会失败》均为正式出版物，**仅供个人阅读**；若要公开对公众提供，请先取得授权。
- 《价值》《国家为什么会失败》的 PDF 正文没有可提取的章节标题层，因此这两本用**按原书页码导航 + 全文搜索**（搜索会标注命中所在页码），这是数据本身的限制，不是页面故障。

## 本地快速预览

直接双击任一 `.html` 用浏览器打开即可。导航页 `index.html` 的链接是相对路径，本地打开也能正常跳转。
