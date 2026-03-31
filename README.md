# 个人网站维护说明（GitHub Pages）

这个仓库目前是一个**纯静态页面**（`index.html`），可以直接用于 GitHub Pages。

---

## 1) GitHub Pages 稳定性说明

当前结构非常简单：
- `index.html`（主页面）
- `.nojekyll`（禁用 Jekyll 处理，减少不必要的构建干扰）

这类结构最稳定，适合长期维护。

> 如果你在 GitHub 仓库里启用了 Pages（`Settings -> Pages`），并选择当前分支发布，通常就能直接访问。

---

## 2) 你以后主要改哪里

你现在只需要改 `index.html` 里靠近底部的配置块：

- `<script id="site-config" type="application/json"> ... </script>`

我已经把高频改动项集中到了这里，默认不会改变页面风格。

---

## 3) 可维护字段说明

在 `site-config` 里你可以改这些：

### 3.1 首页名字与简介
- `name`：首页名字
- `introLine1`：第一行简介
- `introLine2`：第二行简介
- `aboutHtml`：下方介绍（支持 `<br>` 换行）

### 3.2 头像与背景图
- `avatar`：头像地址
- `heroBackground`：首屏背景图地址

说明：
- 为空 `""` 时，页面会继续使用你当前默认图（不会破坏现有效果）。
- 推荐填相对路径，比如 `"assets/avatar.jpg"`。

### 3.3 文章链接
- `article.title`：按钮文字
- `article.url`：文章跳转链接
- `article.sourceName`：来源名称
- `article.sourceUrlText`：显示给访客看的链接文字

### 3.4 画廊图片
- `gallery` 数组里有 3 项：
  - `title`：每张图标题
  - `image`：图片地址

同样地，`image` 为空时会保留你当前默认图。

---

## 4) 更新步骤（最短流程）

1. 打开 `index.html`
2. 找到 `id="site-config"` 的 JSON
3. 只改你想改的字段
4. 保存并提交到 GitHub
5. 等待 Pages 自动更新（通常 1~3 分钟）

---

## 5) 图片替换建议

建议新建目录：

```text
assets/
  avatar.jpg
  hero.jpg
  gallery-1.jpg
  gallery-2.jpg
  gallery-3.jpg
```

然后在 `site-config` 中写：

- `"avatar": "assets/avatar.jpg"`
- `"heroBackground": "assets/hero.jpg"`
- `gallery[i].image` 对应填 `assets/gallery-x.jpg`

---

## 6) 注意事项

- 不要改动页面结构和样式块，除非你要主动改设计。
- 你只改 `site-config` 就可以完成大部分更新。
- 文章链接如果要在新窗口打开，当前按钮已经保留 `target="_blank"`。

